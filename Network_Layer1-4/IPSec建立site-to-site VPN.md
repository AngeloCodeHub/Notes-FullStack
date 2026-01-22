# IPSec建立site-to-site VPN

- IPSec site-to-site IKEv1
- 未看—[Easy IPSEC Site-To-Site VPN Guide, MikroTik ROSv7](https://www.youtube.com/watch?v=uVag_e475zc)
- [VPN在RouterOS有多種實現方式](https://help.mikrotik.com/docs/display/ROS/Virtual+Private+Networks)
- [RouterOS IPSec官方文件](https://help.mikrotik.com/docs/display/ROS/IPsec)
- 兩台router之間建立連線一定要是main
- site-to-site預設使用ike v1
- 採坑︰winbox ip/nat設定標籤中Extra展開與未展開設定是不一樣的要注意
設定時因為認為展開不做設定就是不生效導致nat失敗（展開代表已經生效）
- 採坑：在windows設定L2TP/IPsec始終無法連線，將設定檔刪掉重新設定便可以連線ROS VPN
RouterOS IPSec設定更改後，windows vpn最好刪掉重新設定
- 採坑：連線鳳山套用了site-to-site（使用同樣ip連入），目前無法找出規律（疑似在peer）
- Site-to-Site IPSec是雙向對等（兩邊都要設定）
- 紀錄：在ROS有#字的是有順序
- 紀錄：當l2tp ip-pool指定與lan同網段可以與在ros的ip直接通訊如192.168.77.254，但沒有在ros的則不能

---

### 關於IP Pool

- 提供ROS的服務（DHCP、L2TP、PPPoe…）動態取得ip的服務
- ip-pool是一個虛擬ip池，取得成功後會動態產生一個虛擬介面（根據服務）
- ip-pool是不受local ip/arp設定的mac限制，並與Local Lan無關
- ip-pool在ros被視為外部ip，如果與場內重複該怎設定路由？
- ip-pool要與場內相通必須設定nat
- l2tp的profile local address可設定任何一個ip（只被當作與ros本身一個溝通ip），與實體local Lan ip arp都無關
- 若取得的ip pool與場內ip不同網段要另外設nat mangle導流
要導流ip pool的mark routing不能指定local原生介面（ETH、bonding）

---

## site-to-site設定步驟

1. ipsec/profiles 建立配置文件（ike的步驟一，Phase1）
DH Group︰越小安全性越小但效能越好，選modp1024
Encryption Algorithm︰aes-128
dpd-interval︰peer死掉的偵測時間（300s）
enc-algorithm︰peer的加密演算法
其他預設值
2. ipsec/proposal（ike的步驟二，Phase2）
enc-algorithms - 給sa（security associations）使用的演算法
3. ipsec/peers
依照文件可以設定兩台router要設定雙向，peer也就是類似客戶端，可使用網域
4. ipsec identities
5. ipsec policy(控制要被加密的網段)
6. 對等的site做上述五步驟同樣設定
雙向都要完成才成功建立IPsec Security Association
7. 增加兩個站的nat規則

---

### 知識科普補充

- site-to-site要使用tunnel mode，client-to-site是使用trasport mode
- RouterOS IPsec Policy是使用設定的順序，不是使用Priority優先等級
- IPsec是一個協定套件，包含以下協定
Authentication Header (AH)
Encapsulating Security Payload (ESP)
Internet Key Exchange (IKE)
- IKE又分為Phase1和Phase2
Phase1主要是認證（athenticate）對方，Phase1會透過Diffie-Hellman建立一組key，這組key是用來為Phase2的資訊進行加密
Phase2則是真正建立IPsec VPN通道
- [IPsec與OSI七層關係圖](https://zh.wikipedia.org/wiki/File:Internetprotocolsecurity.JPG)
- Diffie-Hellman Groups
Diffie-Hellman (DH) key exchange protocol
- ike協定
[歸屬於IPsec協定族，用以建立安全關聯（Security association，SA）](https://zh.wikipedia.org/zh-tw/%E7%B6%B2%E9%9A%9B%E7%B6%B2%E8%B7%AF%E9%87%91%E9%91%B0%E4%BA%A4%E6%8F%9B)
[網路安全關聯與金鑰管理協定](https://zh.wikipedia.org/zh-tw/%E7%B6%B2%E8%B7%AF%E5%AE%89%E5%85%A8%E9%97%9C%E8%81%AF%E8%88%87%E9%87%91%E9%91%B0%E7%AE%A1%E7%90%86%E5%8D%94%E5%AE%9A)
[IPSec VPN之IKE协议详解](https://cshihong.github.io/2019/04/03/IPSec-VPN%E4%B9%8BIKE%E5%8D%8F%E8%AE%AE%E8%AF%A6%E8%A7%A3/)
- [IPSec wiki](https://zh.wikipedia.org/zh-tw/IPsec)
- Windows與Android內建VPN Client協定
Windows：IKEv2、安全通訊端通道通訊協定(SSTP)、L2TP/IPsec(使用憑證)、L2TP/IPsec(使用預先共用金鑰)、點對點通道通訊協定(PPTP)
Android：IKEv2/IPSec MSCHAPv2、IKEv2/IPSec PSK、IKEv2/IPSec RSA
- RouterOS Log Topic可於loggin設定
- 記事：clear memory log，logging action memory lines改成1在改成要流的行數

---

### 架設L2TP/IPsec讓Windows內建VPN存取公司網路資源

- L2TP負責連線，IPsec負責資料加密

### 步驟

1. 設定ip-pool
2. 新增一組給L2TP使用的profile
3. 新增secrets設定帳號密碼，Service指定l2tp並指定剛剛設定的profile
4. L2TP Server設定
protocol：L2TPv2
Defaul profile：指定剛剛設定的profile
Athentication：mschap2
USE IPSec：設定為required並設定金鑰
此時ip/IPSec的peer與identity會動態新增l2tp server
5. IPSec Default Profile：打勾3des、modp1024其他全部取消
6. IPSec Default Proposals：sha1、aes-128cbc打勾，其他全部取消