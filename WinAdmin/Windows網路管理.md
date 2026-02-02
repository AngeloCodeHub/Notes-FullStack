
- Firewall GUI
  ```PowerShell
  firewall.cpl
  ```
- [Windows Firewall Overview | Microsoft Learn](https://learn.microsoft.com/en-us/windows/security/operating-system-security/network-security/windows-firewall/)
- [喇賽 netsh （網路服務殼層） - iT 邦幫忙::一起幫忙解決難題，拯救 IT 人的一天](https://ithelp.ithome.com.tw/articles/10080784)
- Windows netsh
  ```PowerShell
  netsh advfirewall
  netsh advfirewall firewall show rule name=all
  ```
- PowerShell網路相關cmdlet
  ```PowerShell
  Get-NetFirewallRule
  Get-NetFirewallProfile
  get-netConnectionProfile
  Enable-NetAdapterBinding
  ```
- [Network shell (netsh) | Microsoft Learn](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/netsh)
- net use
  ```PowerShell
  net use x: \\dc1\ClientVHD /user:username password
  ```
- 關閉ping回應
  核心網路功能(群組)=>核心網路診斷 - ICMP 回應要求 (ICMPv4-In)
- [如何透過 netsh 指令快速切換 Windows 網路設定 | The Will Will Web](https://blog.miniasp.com/post/2008/11/17/Using-Netsh-Command-Line-Utility-to-switch-TCP-IP-settings)
- 解決 Active Directory預設使用IPv6導致無法通訊，開機時重啟IPv6通訊協定
  ```PowerShell
  Start-Sleep -Seconds 30
  Disable-NetAdapterBinding -Name "乙太網路" -ComponentID ms_tcpip6
  Start-Sleep -Seconds 5
  Enable-NetAdapterBinding -Name "乙太網路" -ComponentID ms_tcpip6
  ```
