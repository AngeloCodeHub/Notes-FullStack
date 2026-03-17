# Windows 軟體管理

有些套件Conda、Git已經內建，搭配Conda管理  
[[Anaconda環境建置]]  
[[軟體套件管理彙總]]

## 雜記

- 查看軟體與scoop本身updatable：scoop status
- [Chocolatey Software | Community](https://community.chocolatey.org/)
- [Browse the winget repository - winstall](https://winstall.app/)
- [winget.run | Finding winget packages made simple.](https://winget.run/)
- [比Wget、Curl更强大的下载工具！ - 知乎](https://zhuanlan.zhihu.com/p/668749016)
- [aria2](https://aria2.github.io/)

## Scoop

- [Scoop](https://scoop.sh/)
- Scoop本體安裝位置  
  `C:\Users\user\scoop\shims\scoop.ps1`
- 全域的軟體安裝位置  
  `C:\ProgramData\scoop`

## winget套件管理

- 全域位置  
  `C:\Program Files\WinGet\Packages`
- [microsoft/winget-cli](https://github.com/microsoft/winget-cli)
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
