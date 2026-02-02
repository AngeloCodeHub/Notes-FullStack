# RouterOS7

### 雜七雜八
- [pppoe keepalive timeout意義](https://help.mikrotik.com/docs/spaces/ROS/pages/2031625/PPPoE#PPPoE-Accessconcentrator)
  設定為10秒，在10秒內沒有封包傳送則判定為斷開
- [routeros入门到精通74e.pdf](http://www.irouteros.com/download.php)
- 7版外線ros本身ping policy要mangle導流，否則會ping不到，6版可以
- 禁止使用mac登入，tools/mac server地方設定
  
- ros reset
  斷電→按住→reset插電→USR閃爍放開（要放開不能一直按著否則會失敗）
- file backup方式回復也會將原本mac覆蓋到新機器，盡量使用script方式
- cli問號幫助改成F1，目錄結構改成反斜線表示
- 設定routing rule後mangle就不用設定routing mark，官方不建議兩種同時使用
  mangle有更高的優先權
- [ROS v7 differences in IP/Route](https://help.mikrotik.com/docs/pages/viewpage.action?pageId=127369252)
- [routing rule lookup](https://help.mikrotik.com/docs/display/ROS/Policy+Routing)參數與lookup-only-in-table意義是lookup當查找不到路由會回到main
- routing rule只能使用遮罩切割ip，無法指定ip範圍
- VRF︰讓routeros本身功能可以指定那各路由出去
client如果在policy routing不能連ros本身須使用vrf
- V7的ntp client變得更強
- ros7預設只有main（不是使用mangle指定方式）才能winbox連入，7版本機output prerouting在mangle要明確定義，output不用指定介面
區網要連接ros問題：只能跑在預設路由（也就是在mangle不能指定任何prerouting，包括main），才能連接ros
解決方式：指定mangle prerouting des排除ros區網ip
概念：可防止區網惡意連接ros

---

### Routeros備份與回復操作步驟（順序）

1. 本機設定成可以通就好，其他次要功能與防火牆上線再設定（避免擋到自己）
2. 確認客戶機能上網與自己能連線管理
3. 實體界面設定(int list、bonding、IP)
4. ip route、mangle、nat
5. 客戶機ARP列表
6. IP Address List
7. system

---

### 名詞解釋與功能

- NAT PMP(NAT Port Mapping Protocol)
- [VRF︰Virtual Routing and Forwarding](https://help.mikrotik.com/docs/pages/viewpage.action?pageId=328206)
- [FIB (Forwarding Information Base)](https://help.mikrotik.com/docs/display/ROS/IP+Routing)

---

### 7版route設定方式

預設routing/tables main無法更改無法刪除

1. routing/tables
設定路由表
2. ip/route list
指定路由
3. ip/firewall/mangle
標記路由

---

### 區網mac安全

1. interface list設定與區分界面
2. ip neighbors設定可dicovery的界面（根據list）
3. tool mac server限制可使用mac的界面

---

Winbox

WBX只備份所有位址（可設定不匯出列表站台密碼），適合用來備份

CDB儲存只適合在同個機器（可隨意切換），位址會即時生效

技巧：不同機器可使用wbx（總）匯入然後根據機器做設定，wbx有重複不會入而會累加