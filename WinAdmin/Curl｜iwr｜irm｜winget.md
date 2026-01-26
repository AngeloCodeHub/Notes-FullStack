## winget套件管理

- [WinGet | Microsoft Learn --- WinGet | Microsoft Learn](https://learn.microsoft.com/en-us/windows/package-manager/)
- 使用者 Windows Store應用程式路徑與winget安裝的程式路徑
  ```PowerShell
  # Windows Store
  C:\Users\user\AppData\Local\Microsoft\WindowsApps
  
  # Winget
  C:\Users\user\AppData\Local\Microsoft\WinGet\Packages
  ```
- 設定（開啟編輯器）
  ```PowerShell
  # C:\Users\user\AppData\Local\Packages\Microsoft.DesktopAppInstaller_8wekyb3d8bbwe\LocalState\settings.json
  
  winget settings
  ```
- 套件詳細資訊
  ```PowerShell
  winget show PuTTY.PuTTY
  ```
- install命令
  ```PowerShell
  winget install --scope machine --id Microsoft.VisualStudioCode -i
  winget install --scope machine --id Git.Git -i
  winget install --scope machine --id DominikReichl.KeePass -i
  winget install --scope machine --id Daum.PotPlayer -i
  winget install --scope machine --id Rufus.Rufus -i -l "D:\Program Files\Rufus"
  winget install --scope machine --id PuTTY.PuTTY -i
  winget install --scope machine --id Microsoft.OpenSSH.Beta -i
  
  choco install LINE --dir "D:\Program Files\LineMesenger"
  
  $File= "https://xtupdate.xq.com.tw/tradedas/installer/daqctyap/tw/ctyapsetup.exe"
  iwr $File -OutFile ctyapsetup.exe
  ```

## 雜記

- [Chocolatey Software | Community](https://community.chocolatey.org/)
- [Browse the winget repository - winstall](https://winstall.app/)
- [winget.run | Finding winget packages made simple.](https://winget.run/)
- [比Wget、Curl更强大的下载工具！ - 知乎](https://zhuanlan.zhihu.com/p/668749016)
- [aria2](https://aria2.github.io/)
- [Invoke-RestMethod (Microsoft.PowerShell.Utility) - PowerShell | Microsoft Learn](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/invoke-restmethod)
- curl windows內建在 windows/system32，不能更改
  使用 winget安裝新版無法使用，因為系統環境變數 system32在前
- [如何在任意主機查詢對外的 IP 地址 | The Will Will Web](https://blog.miniasp.com/post/2024/08/19/How-to-query-the-external-IP-address-on-any-host?fbclid=IwY2xjawExcTBleHRuA2FlbQIxMQABHTvo6LdU41Qu2Qi1QuFR8hGP51yNglDTGbBYEXRT96QVAnEOJ0TGbAgk1w_aem_OkzyVUPkVreruF12paFxBA&sfnsn=mo)
- [後知後覺新發現 - 原來 Windows 已內建 curl (附常用語法範例)-黑暗執行緒](https://blog.darkthread.net/blog/win-builtin-curl/)
- [Everything curl - everything curl](https://everything.curl.dev/)
- [curl](https://curl.se/)
- [Chat-windows11 Curl](https://www.perplexity.ai/search/wo-xiang-yao-geng-xin-windows1-5utSB53XTlGiHM8d8ixGqA#1)
- [Linux Curl Command 指令與基本操作入門教學 | TechBridge 技術共筆部落格](https://blog.techbridge.cc/2019/02/01/linux-curl-command-tutorial/)
- [網站封鎖 curl 的原因與繞過](https://gemini.google.com/app/b80bf21397094c6e)
- [http 發布並取得差異。 這篇文章將整理 http（超文本傳輸… | by Po-Ching Liu | Medium --- http Post 和 Get 差異. 本篇文章將整理 http (Hypertext Transfer… | by Po-Ching Liu | Medium](https://totoroliu.medium.com/http-post-%E5%92%8C-get-%E5%B7%AE%E7%95%B0-928829d29914)
- [Change reuqest method 甚麼是 HTTP Method？ - iT 邦幫忙::一起幫忙解決難題，拯救 IT 人的一天](https://ithelp.ithome.com.tw/articles/10250980)
- [Main HTTP methods 🧑‍💻🧑‍💻 #https... - Mbah Francis Ifeanyi | Facebook](https://www.facebook.com/100012372696048/posts/2332283827194018)

## cURL雜記
