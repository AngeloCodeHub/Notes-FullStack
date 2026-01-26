
- Windows 設定檔與模組位置
  ```PowerShell
  $profile | select-object *
  ```

## 系統管理－應用

- [檔案系統管理](WinAdmin/檔案系統管理.md)
- [Win Service 操作](WinAdmin/WinService操作.md)
- [Win環境變數](WinAdmin/Win環境變數.md)
- [Registry](WinAdmin/Registry.md)
- [Remote-Desktop-Protocol](WinAdmin/Remote-Desktop-Protocol.md)

## 雜記

- 修改開機啟動應用程式
  desk.cpl→應用程式→啟動
- PowerShell PSReadLine歷史紀錄
  ```PowerShell
  C:\Users\user\AppData\Roaming\Microsoft\Windows\PowerShell\PSReadLine\ConsoleHost_history.txt
  ```
- [windows运行命令大全 - 知乎](https://zhuanlan.zhihu.com/p/135297234)
- [使用指令管理 Microsoft Windows Server :: 2011 iT 邦幫忙鐵人賽](https://ithelp.ithome.com.tw/users/20005121/ironman/332)
- 在Windows與Linux使用PowerShell應該釐清各作業系統的內建指令與PowerShell cmd-let指令.
  Windows與Linux內建指令還是必須要學，然後使用 PowerShell 整合棄用Bash.
  但務求操作步驟一致而不用重新學習.
- keyword：PowerShell Markdown
- [about_Providers - PowerShell | Microsoft Learn](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_providers?view=powershell-7.5)
- [Powershell Array](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_arrays)
- [.NET Console Class](https://learn.microsoft.com/en-us/dotnet/api/system.console)
- [Chat-Win + R 與 PowerShell 呼叫差異](https://copilot.microsoft.com/shares/XCd2WLQS9D5NbSLkrDfYo)
- 使用者設定檔位置
  `C:\Users\user\OneDrive\文件\PowerShell`
- [keeapss script直接提取密碼](https://www.perplexity.ai/search/keepassshi-yi-tao-lao-pai-mi-m-DUpsG3XqQnKgoHSpGn2dKg)
- [Chat-Powershell與chcp修改編碼、ps搭配 "git ls-files" 移植具有版控的工作空間](https://www.perplexity.ai/search/wo-yao-jiang-yi-ge-ju-you-git-32gmrlh2SLa4By_JRxi5fg#2)
- [Chat-PowerShell指令提示過長問題](https://www.perplexity.ai/search/wo-jing-chang-shi-yong-powersh-3c5konELQTeYSlo0VkEY5w)

## References

- [Windows commands | Microsoft Learn](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/windows-commands)
- [PowerShell Documentation - PowerShell | Microsoft Learn](https://learn.microsoft.com/en-us/powershell/)
- [Windows Server Management documentation | Microsoft Learn](https://learn.microsoft.com/en-us/windows-server/administration/manage-windows-server)
- [圖書：30天挑戰精通 Powershell](https://webpacx.ksml.edu.tw/bookDetail/1775845)

## Windows PowerShell 5.1

- 相關位置
  ```PowerShell
  C:\Windows\System32\WindowsPowerShell
  C:\Program Files\WindowsPowerShell
  C:\Users\user\OneDrive\文件\WindowsPowerShell
  ```
- 插件
  [MScholtes/PS2EXE: Module to compile powershell scripts to executables](https://github.com/MScholtes/PS2EXE)
