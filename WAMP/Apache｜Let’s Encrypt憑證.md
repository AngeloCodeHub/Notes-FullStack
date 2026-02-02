
[Let’s Encrypt](https://letsencrypt.org/)

[mod_md官方使用說明](https://github.com/icing/mod_md?tab=readme-ov-file#monitoring)

[Apache Module mod_md](https://httpd.apache.org/docs/2.4/mod/mod_md.html)

1. 確保外部可訪問80 Port http://example.com
2. 啟用mod_ssl、mod_watchdog、mod_md模組
3. 關閉 httpd.conf 的ServerAdmin指令並 include conf/extra/httpd-ssl.conf
4. 在 httpd-ssl.conf 設定
    
    ```php
    Listen 443
    # MDomain會自動判斷網域，只指定domain會無法啟動
    MDomain www.example.com
    ServerAdmin myemail@example.com
    MDCertificateAgreement accepted
    
    <VirtualHost *:443>
      # 下面一行根據情況修改
      DocumentRoot "D:/WorkSpace/Vanilla/dist"
      ServerName www.example.com
      ServerAdmin myemail@example.com
      ErrorLog "${SRVROOT}/logs/error.log"
      TransferLog "${SRVROOT}/logs/access.log"
    
      # 下面一行根據情況修改
      <Directory "D:/WorkSpace/Vanilla/dist/">
        Options +Indexes +Includes +FollowSymLinks +MultiViews
        AllowOverride All
        Require all granted
      </Directory>
    
    SSLEngine on
    </VirtualHost>
    ```
    
5. 取得認證大約須半小時

## 憑證展期

1. 確認 root 網域（example.com）80 port可訪問
2. 開啟Windows防火牆與路由器 80 port
3. 將以下code加入vhost.conf
    
    ```php
    <VirtualHost *:80>
      DocumentRoot "C:/wamp64/bin/apache/apache2.4.62.1/htdocs"
      ServerName example.com
      ErrorLog "${SRVROOT}/logs/error.log"
      TransferLog "${SRVROOT}/logs/access.log"
    
      <Directory "C:/wamp64/bin/apache/apache2.4.62.1/htdocs/">
        Options +Indexes +Includes +FollowSymLinks +MultiViews
        AllowOverride All
        Require all granted
      </Directory>
    </VirtualHost>
    ```
    
4. 測試 [http://example.com](http://example.com) 是否可訪問
5. 重啟apache服務
6. 檢查”/apache2.4.62.1/md/domains” 自身網域憑證是否下載成功
7. 瀏覽器造訪網站查看憑證，憑證有效時還是跳不安全需將瀏覽器重啟
8. 重新開啟windows防火牆、路由器防火牆、關閉vhost

---

- virtual host基於name base與ip base（但都基於固定檔案而非另一個web server）
- vhost的servername（name base）也就是FQDN，客戶端以網址訪問時會在header紀錄
name base的應用是基於相同網域不同主機
- servername是真正名稱，可以另起alias
- next.js另開web server如要經過apache有兩種方式
[靜態輸出](https://nextjs.org/docs/app/building-your-application/deploying/static-exports)（純HTML+CSS+Javascript）、reverse proxy
- 疑問：apache子頁可使用中文嗎?
A：只要是相同domain都可