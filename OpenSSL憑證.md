
- [OpenSSL](https://openssl.org/)
- git for windows有內建
- [如何使用 OpenSSL 建立開發測試用途的自簽憑證 (Self-Signed Certificate) | The Will Will Web](https://blog.miniasp.com/post/2019/02/25/Creating-Self-signed-Certificate-using-OpenSSL)
- 產生私密金鑰 （server.key）與憑證檔案 （server.crt）
  ```PowerShell
  openssl req -x509 -new -nodes -sha256 -utf8 -days 365 -newkey rsa:2048 -keyout server.key -out server.crt -config D:\ssl.conf
  
  openssl pkcs12 -export -in d:\server.crt -inkey d:\server.key -out d:\server.pfx
  ```
- Windows相關指令
  ```PowerShell
  certutil.exe
  certmgr.msc
  WMIC.exe
  ```
