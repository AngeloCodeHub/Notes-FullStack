# Bonding原理與應用

- [第 3 堂課 - LACP 與 bonding/team 及 IPv6 簡易設定](https://dic.vbird.tw/linux_server/unit03.php)
- [Linux Bonding](https://www.lijyyh.com/2011/11/0-balance-rr-l-round-robin-salve-salve.html)
- [routeros bonding 官方文件](https://help.mikrotik.com/docs/spaces/ROS/pages/8323193/Bonding)
- [MikroTik RouterOS/ROS配置Bonding（链路聚合）将多个物理接口组合为一个逻辑接口，实现更高的带宽、链路冗余以及负载均衡等功能](https://www.roszj.com/2461.html)
- [Linux网络：Bond的七种模式详解与配置参考](https://blog.csdn.net/Tassel_YUE/article/details/140817071)
- [Linux下双网卡绑定七种模式 多网卡的7种bond模式原理](https://support.huawei.com/enterprise/zh/knowledge/EKB1001172264)
- [Bond 7种模式解释、举例如何配置：有列出switch是否要設置](https://blog.csdn.net/hezuijiudexiaobai/article/details/131216840)
- [LACP static和LACP有什麼差別](https://ithelp.ithome.com.tw/questions/10216069)
- [LAG与LACP的区别](https://jimizhou.com/lag-lacp)
- [Linux下双网卡绑定七种模式 多网卡的7种bond模式原理](https://support.huawei.com/enterprise/zh/knowledge/EKB1001172264)
- [在什么情况的组网下会使用LACP的Passive模式](https://zhiliao.h3c.com/questions/dispcont/256066)

---

- balance rr在switch需要設定LAG（靜態）  
  案例：沒有設定Switch LAG時直接使用RouterOS balance rr會造成封包會發向所有未綁定mac的機器
- LACP 單一session並不會合併頻寬（依session作負載平衡），session的定義
- 小組模式：LACP與static group（靜態小組）差異  
  LAG不涉及protocol  
  LACP是基於自動協調LAG（LACP是基於LAG的實現）
- [MIS之IT基礎建設(6)Hyper-v主機規劃(二)網路卡(NIC Teaming)](https://ithelp.ithome.com.tw/articles/10157336)
- [MLAG vs. Stacking vs. LACP](https://community.fs.com/article/mlag-vs-stacking-vs-lacp.html)
- [Understanding Link Aggregation and LACP](https://community.fs.com/article/understanding-link-aggregation-control-protocol.html)
static LAG設定較簡單，static group（靜態小組）
dynamic LAG，如LACP
- [Master NIC Teaming with PowerShell and GUI](https://adamtheautomator.com/nic-teaming/)
- [How to Configure NIC Teaming on Windows Server 2019/2016 and Windows 10](https://woshub.com/configure-nic-teaming-windows/)
- 模式：交換器獨立（switch independency）
適用trunk不同交換器

---

## Windows Server NIC Teaming設定

### LAG（static）設定步驟

1. 介面設定：duplex-full，速率，双工、模式
2. GUI→端口→鍊路聚合→端口配置
選擇要聚合的端口（lag也可只從windows設定而不需要端口聚合，如要在switch之間則一定要設定）
3. Windows Server
儀表板→NIC小組→新增小組
mode：靜態小組、負載平衡模式：動態

### LACP設定步驟

1. 介面設定：duplex-full，速率，双工、模式
可不設定trunk，trunk使用於switch 對接與多個vlan使用
[Windows Server 2012 NIC Teaming實作LACP極速傳送效能](https://dotblogs.com.tw/swater111/2013/09/06/116546)
2. CLI模式進介面設定channel group（會自動生成agg）
    
    ```bash
    channel-group 2 mode active
    ```
    
3. windows server teaming
儀表板→NIC小組→新增小組
mode：LACP、負載平衡模式：動態
4. 查看channel group
    
    ```bash
    show channel-group 2
    ```