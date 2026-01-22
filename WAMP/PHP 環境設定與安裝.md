# PHP 環境設定與安裝

- APCU
功能：快取
[PHP說明文件](https://www.php.net/manual/en/book.apcu.php)、[GITHUB官網](https://github.com/krakjoe/apcu)
- gd
[PHP說明文件](https://www.php.net/manual/en/book.image.php)
功能：圖片處理，elementor會使用
- Memcached PHP Client
功能：快取
[GitHub官網](https://github.com/php-memcached-dev/php-memcached?tab=readme-ov-file)、[PECL下載頁](https://pecl.php.net/package/memcached)、[PHP說明文件](https://www.php.net/manual/en/book.memcached.php)
安裝方法：php_memcached.dll放入phpext，libhashkit.dll、libmemcached.dll放入apache\bin
- Memcached Server
[GitHub官方原始碼（沒有windows，需使用第三方編譯製作）](https://github.com/memcached/memcached)
[nono第三方編譯 for Windows](https://github.com/nono303/memcached)
安裝方法
    
    ```powershell
    nssm-2.25.0    
    須提高權限使用，不須加入環境變數
    nssm-2.25.0.exe install memcached C:\memcached\memcached-avx.exe
    nssm-2.25.0.exe set memcached AppParameters "-vv -m 2048 -I 1024m"
    nssm-2.25.0.exe set memcached AppDirectory C:\memcached
    nssm-2.25.0.exe set memcached AppExit Default Restart
    nssm-2.25.0.exe set memcached AppNoConsole 1
    nssm-2.25.0.exe set memcached AppPriority ABOVE_NORMAL_PRIORITY_CLASS
    nssm-2.25.0.exe set memcached AppStderr C:\memcached\logs\memcached.log
    nssm-2.25.0.exe set memcached AppStopMethodSkip 6
    nssm-2.25.0.exe set memcached AppTimestampLog 1
    nssm-2.25.0.exe set memcached DisplayName memcached
    nssm-2.25.0.exe set memcached ObjectName LocalSystem
    nssm-2.25.0.exe set memcached Start SERVICE_AUTO_START
    nssm-2.25.0.exe set memcached Type SERVICE_WIN32_OWN_PROCESS
    移除
    nssm-2.25.0.exe remove memcached
    ```
    
    其他第三方編譯DLL for PHP
    [memcached-windows](https://github.com/jefyt/memcached-windows)、[php_memcached_dll](https://github.com/lifenglsf/php_memcached_dll)、[win-memcached](https://github.com/X-Lucifer/win-memcached)
    
- Redis Server
[Redis for Windows](https://github.com/tporadowski/redis)、[redis-windows](https://github.com/redis-windows/redis-windows)、[https://redis.io](https://redis.io/)
- Redis PHP client
[PECL下載頁](https://pecl.php.net/package/redis)、[GitHub官網](https://github.com/phpredis/phpredis)
- ImageMagick Server、imagick Client
[PHP說明文件](https://www.php.net/manual/en/book.imagick.php)、[ImageMagick官網](https://imagemagick.org/script/download.php)、[imagick PECL下載](https://pecl.php.net/package/imagick)、[imagick官方網頁](https://phpimagick.com/)
- [igbinary](https://github.com/igbinary/igbinary)**、**[PECL下載頁](https://pecl.php.net/package/igbinary)、[PHP說明文件](https://www.php.net/manual/en/book.igbinary.php)
- [exif（Exchangeable image information）](https://www.php.net/manual/en/book.exif.php)
- [OPcache](https://www.php.net/manual/en/book.opcache.php)