# Windows Remote Desktop 教學

- [RDP檔案參數](https://www.donkz.nl/overview-rdp-file-settings/)

- [How to Use PowerShell to Enable Remote Desktop on Windows 10, 11](https://www.anyviewer.com/how-to/powershell-enable-remote-desktop-0427.html)

- [How to Disable Remote Desktop on Windows 11](https://www.groovypost.com/howto/disable-remote-desktop-on-windows-11/)

- [官方文件 - 使用 Powershell 修改 Port Number](https://learn.microsoft.com/en-us/windows-server/remote/remote-desktop-services/remotepc/change-listening-port?tabs=powershell)

- [官方文件 - RDP 檔支援的參數](https://learn.microsoft.com/en-us/azure/virtual-desktop/rdp-properties)

- [GPEDIT - 遠端桌面連線使用者斷線後，如何定時自動登出(WinServer 2019示範)](https://eheima.com/3524/rds-auto-signout)

- [什麼是網路層級驗證？](https://applen1.pixnet.net/blog/post/33281117)

- [Command Line 下直接連線 RDP 的方法](https://dotblogs.com.tw/dean/2013/07/22/111858)

## 修改 Port 號

1. regedit 指令開啟 registry 編輯器

2. 找出以下reg值：
	```Powersehll
	HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\TerminalServer\WinStations\RDP-Tcp
	```
3. 將 PortNumber 的key值，修改十進位值,改成自己的 Port 號

## 登入安全性

事件檢視器(eventvwr.msc )=>Windows紀錄=>安全性=>尋找事件代碼4624，4625
