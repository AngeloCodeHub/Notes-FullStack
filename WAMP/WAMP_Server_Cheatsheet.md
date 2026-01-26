# WAMP Server Cheatsheet

### [Wampserver下載站](https://wampserver.aviatechno.net/)

### [Sourceforge.net](https://sourceforge.net/projects/wampserver/)

一些小工具使用MySQL installer（ex.MysqlShell）

- Server封包說明
網際網路→路由器→防火牆→OS→Server（DB、Web、Cache）→PHP→Application（WordPress）
越左邊能做的就由左邊處理

---

### WAMP

- wampmanager mysql改port只能3301-3309，可改設定檔
- wamp裡wampmanager能改的盡量使用wampmanager去改，不能改的才使用設定檔
- VHOST同個port有順序問題
- wamp在Windows服務
wampapache64（apache服務），wampmysqld64（mysql服務），wampmariadb64
TrayMenu結束後服務會關閉，如在生產環境中可設定為自動啟動
- VirtualHost的name與domain的關係，要如何在wamp設定domain
apache沒有設定Virtual host就不能訪問wp網址，可是wamp server name不能設定網址
VirtualHost如果有相同的port則已文件最上為主
- {INSTALL_DIR}：wamp本機安裝變數
- [WAMP Virtual Host](http://forum.wampserver.com/read.php?2,127757)
