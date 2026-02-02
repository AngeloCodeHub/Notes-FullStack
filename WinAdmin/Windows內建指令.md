
- [如何藉由輸入指令來執行控制台工具 - Microsoft 支援服務](https://support.microsoft.com/zh-tw/topic/%E5%A6%82%E4%BD%95%E8%97%89%E7%94%B1%E8%BC%B8%E5%85%A5%E6%8C%87%E4%BB%A4%E4%BE%86%E5%9F%B7%E8%A1%8C%E6%8E%A7%E5%88%B6%E5%8F%B0%E5%B7%A5%E5%85%B7-bce95b4d-e8c2-1cd0-ee0d-027679d520a6)
- GUI
  ```PowerShell
  sysdm.cpl # 系統內容
  appwiz.cpl # 程式和功能
  Firewall.cpl # 防火牆
  compmgmt.msc # 電腦管理
  lusrmgr.msc # 本機使用者與群組
  Netplwiz.exe # 本機使用者管理
  services.msc # 服務管理
  certmgr.msc # 憑證管理
  diskmgmt.msc # 磁碟管理
  eventvwr.msc # 事件檢視器（也有exe可省略msc）
  gpedit.msc # 本機群組原則編輯器
  secpol.msc # 本機安全性原則
  taskschd.msc # 工作排程器
  devmgmt.msc # 裝置管理員
  desk.cpl # Windows11 電腦設定
  powercfg.cpl # 電源管理
  mstsc.exe # Windows RDP
  ```
- cmd指令（none GUI）
  ```PowerShell
  powercfg.exe # 電源管理
  schtasks # Windows 排程管理，取代 at
  ```
