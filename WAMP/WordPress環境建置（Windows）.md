
1. WAMP已經設定好前提下
2. 下載與安裝WP-Cli
[WP-Cli官方說明檔](https://make.wordpress.org/cli/handbook/guides/installing/#installing-on-windows)
3. 安裝WordPress
    
    ```powershell
    # wp-cli注意權限問題，自行創建資料夾，php.ini memory limit不能限太小
    wp core download --locale=zh_TW
    wp config create --dbname=wordpress --dbuser=root --dbpass=Egbf7983 --locale=zh_TW
    ```
    
4. 安裝SSL憑證

---

### 注意事項

- 瀏覽器要能執行php時必須經過Apache處理，否則php會被當成一般檔案不會執行
- IIS伺服器綁定的本機Server網卡與Wordpress網址不一樣時(作Nat時)，需使用dns或hosts將網址綁定本機網卡
wordpress與IIS綁定的網卡ip要分開思考
- Composer路徑
C:\ProgramData\ComposerSetup\bin
C:\Users\AngeloHu\AppData\Roaming\Composer
- 當使用link，開啟VSCODE要從WordPress根目錄開啟，不然WordPress函式會顯示錯誤訊息
- WP的資料庫修改網站設定（option），網站搬家要改siteurl與homeurl不然會讀不到CSS
