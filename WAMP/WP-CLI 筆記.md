## [WordPress CLI download](https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar)
- 放到node.js根目錄以全域使用
- 創建 wp.ps1 執行檔
    ```batch
    $phpPath = 'c:\wamp64\bin\php\php**Version**\php.exe'
    $wpCliPath = 'C:\Program Files\nodejs\wp-cli.phar'
    & $phpPath $wpCliPath @Args
    ```
-   WP-CLI help
    ```powershell
    wp help
    ```
- 版本與更新

  ~~~Powershell
  wp cli version
  wp cli check-update
  wp cli update
  ~~~

- 創建WordPress Instance

  ~~~Powershell
  wp core download --locale=zh_TW;
  wp config create --dbname=wordpress --dbuser=root --dbpass=1234 --locale=zh_TW
  ~~~

- 佈景主題

  ~~~Powershell
  # 查看所有已安裝的佈景主題
  wp theme list
  # 刪除布景主題
  wp theme delete twentytwentytwo
  # 安裝佈景主題（使用slug作為代號）
  wp theme install astra
  ~~~

## 參考

- [WP-CLI handbook](https://make.wordpress.org/cli/handbook/)
- [WP-CLI 指令集](https://developer.wordpress.org/cli/commands/)
