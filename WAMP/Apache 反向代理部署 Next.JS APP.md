# 標題

1. [Apache Virtual Host documentation - Apache HTTP Server Version 2.4](https://httpd.apache.org/docs/2.4/vhosts/)
2. 事前準備
   實體路徑與網址分開思考
   Next.JS與webpack兩者都可使用static export直接build檔案交由檔案系統直接掛載處理，以下介紹兩種方式
2. 啟用 Apache 模組
   proxy_module modules/mod_proxy.so
   proxy_http_module modules/mod_proxy_http.so
   proxy_wstunnel_module modules/mod_proxy_wstunnel.so
3. <http://localhost> 為首頁放置WordPress官網
4. 重要：網址映射要一致（基底要一致），<http://localhost/app> 代理 <http://localhost:3000/app>
5. [反向代理apache不會觸發webpack HMR須配置websocket](https://docs.google.com/document/d/1CANLVV-K_gKw4Ei038Q7VjOEQF5otU86bmsU2grODy4?usp=drive_fs)

    Wamp新增一個vhost

    ```conf
    <VirtualHost *:80>
    ServerName test
    DocumentRoot "d:/workspace/wordpress"
    <Directory  "d:/workspace/wordpress/">
      Options +Indexes +Includes +FollowSymLinks +MultiViews
      AllowOverride All
      Require local
    </Directory>
    # ProxyPreserveHost On 指令確保將原始主機標頭傳遞到後端伺服器。
    ProxyPreserveHost on
    # ProxyPass 指令將 /app 位置的所有請求代理到 http://localhost:3000/app
    ProxyPass "/app" "http://localhost:3000/app"
    # ProxyPassReverse 指令修改來自後端伺服器的 HTTP 回應標頭，以確保重定向和其他鏈接常工作。
    ProxyPassReverse "/app" "http://localhost:3000/app"
    <Location /app/_next/webpack-hmr>
      RewriteEngine On
      RewriteCond %{QUERY_STRING} transport=websocket [NC]
      RewriteCond %{HTTP:Upgrade} websocket [NC]
      RewriteCond %{HTTP:Connection} upgrade [NC]
      RewriteRule /(.*) ws://localhost:3000/app/_next/webpack-hmr/$1 [P,L]
      ProxyPass ws://localhost:3000/app/_next/webpack-hmr retry=0 timeout=30
      ProxyPassReverse ws://localhost:3000/app/_next/webpack-hmr
     </Location>
    </VirtualHost>
    ```

5. Next.JS設定app為basepath

    反向代理到此步驟就可以，如要代理靜態網站繼續步驟五
    可以使用 Location 指令來更精細地控制代理規則。

    next.config.ts

    ```typescript
    /** @type {import('next').NextConfig} */
    const nextConfig: import("next").NextConfig = 
    // 網址基底
    {basePath: '/app',};
    export default nextConfig;
    ```

6. 重啟Apache
7. webpack config（static靜態匯出的方法）

    ```ts
    // 實體檔案
    devServer: {static: './dist/app'},
    // 網址
    output: { publicPath: '/app', },
    ```

    index.html，main.js前加app基底

    ```html
    <body>
      <!-- webpack專用 -->
      <script src="./app/main.js"></script>
    </body>
    ```

---

## 參考

- [webpack **DevServer**](https://webpack.js.org/configuration/dev-server/)
- [Next.JS **basePath**](https://nextjs.org/docs/app/api-reference/next-config-js/basePath)
- [Reverse Proxy Guide](https://httpd.apache.org/docs/2.4/howto/reverse_proxy.html)
- [Apache Module mod_proxy](https://httpd.apache.org/docs/current/en/mod/mod_proxy.html#request-bodies)
- [Apache Module mod_proxy_http](https://httpd.apache.org/docs/2.4/en/mod/mod_proxy_http.html)
- [影片：Setup Apache as a Reverse Proxy](https://www.youtube.com/watch?v=VEr-Gp86teY)

### 待測試與思考

- 相同網址問題：主網頁apache設定/app如果在wordpress也開一個頁面/app會發生什麼事?
- apache reverse proxy /app憑證是否會繼承主網頁
A：會
- [proxy、redirect、rewrite in Next.JS](https://blog.logrocket.com/how-to-use-proxy-next-js/)（網址處理）
- [Apache反向代理的類型](https://www.cnblogs.com/68xi/p/16230089.html)
- html的 base 標籤
- [iframe與reverse proxy應用與差異](https://docs.google.com/document/d/1z-Ip_U80avz4RbwMv4mqGvX5s8fXeAMX2SsH2R7Dyo0?usp=drive_fs)
- apache代理寫法可使用RegEX

Proxy正反向代理要與客戶端與webserver方向思考
[apache正向代理设置](https://blog.csdn.net/guohun01/article/details/132042193)