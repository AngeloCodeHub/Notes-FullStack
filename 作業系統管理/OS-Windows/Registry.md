
- [登錄檔備份—為了避免後面把他玩壞的補救措施 - iT 邦幫忙::一起幫忙解決難題，拯救 IT 人的一天](https://ithelp.ithome.com.tw/articles/10262906)
- [Windows registry for advanced users - Windows Server | Microsoft Learn](https://learn.microsoft.com/en-us/troubleshoot/windows-server/performance/windows-registry-advanced-users)
- [Chat-列印Registry與修改](https://www.perplexity.ai/search/powershellli-ru-he-lie-yin-chu-LfYpCV6kTOqGVndVTSMf.Q)
- [about_Providers - PowerShell | Microsoft Learn](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_providers?view=powershell-7.5)
- Windows內建指令：`reg`
- GUI指令：`regedit`
- Windows檔案總管
  ```PowerShell
  電腦\HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Advanced
  
  HideFileExt
  ShowSuperHidden
  ```
- 開機啟動項目控制
  ```PowerShell
  # 64bit
  HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Run\
  # 32bit
  HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Run\
  ```
- 環境變數
  ```PowerShell
  # user
  HKCU\Environment
  # global
  HKLM\SYSTEM\CurrentControlSet\Control\Session Manager\Environment
  ```
- Windows RDP
  ```PowerShell
HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\TerminalServer\WinStations\RDP-Tcp
  ```
- currentuser registry
  ```PowerShell
  HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList
  ```
- registry 最高權限執行程式
  ```PowerShell
  電腦\HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers
  
  D:\\Game\\AuditionHT\\Audition.exe"="~ WINXPSP3"
  C:\\Users\\Public\\Desktop\\工作管理員.exe"="~ RUNASADMIN
  D:\\Game\\AsureAPK\\Droid4XLauncher.exe"="~ RUNASADMIN
  ```
- 桌面圖示
  [Enable Icons Auto Arrange on Desktop in Windows 10](https://winaero.com/enable-auto-arrange-desktop-windows-10/)
- 使用registry修改SSHd的預設殼層為Powershell7
  ```PowerShell
  New-ItemProperty -Path "HKLM:\SOFTWARE\OpenSSH" -Name DefaultShell -Value "C:\Program Files\PowerShell\7\pwsh.exe" -PropertyType String -Force
  ```
