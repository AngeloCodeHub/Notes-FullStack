# NSSM Usage

- [nssm 官網教學](https://nssm.cc/)
- [介紹好用工具：優異的 nssm 服務管理員 (Non-Sucking Service Manager)](https://blog.miniasp.com/post/2021/09/15/Useful-tools-the-Non-Sucking-Service-Manager)
- [我為何建立 Servy——NSSM/WinSW 的現代開源替代品](https://codelove.tw/@tony/post/an2p0a)

## 部署 Next.JS App

1. 安裝服務，跳出nssm Gui，此例為"NextJSApp"
   ```PowerShell
   nssm install <servicename>
   ```
2. 填上相關參數
   - PATH：C:\Program Files\nodejs\node.exe
   - Startup directory：C:\WWW\DEV-HeroUIApp
   - Arguments：C:\WWW\DEV-HeroUIApp\node_modules\next\dist\bin\next start
1. 可以直接在 Windows Services 停用或調整該服務

## PowerShell｜SC｜net

- PowerShell 相關命令
  ```PowerShell
  Get-Service
  ```

## 補充

- service name與display name不一樣，Windows GUI只能看到display
