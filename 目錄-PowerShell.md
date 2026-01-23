
- Windows 設定檔與模組位置
  ```PowerShell
  $profile | select-object *
  ```

## 系統管理－應用

- [檔案系統管理](WinAdmin/檔案系統管理.md)
- [Win Service 操作](WinAdmin/WinService操作.md)
- [Win環境變數](WinAdmin/Win環境變數.md)
- [Remote-Desktop-Protocol](WinAdmin/Remote-Desktop-Protocol.md)
- [Registry](WinAdmin/Registry.md)

## 插件

- [Oh My Posh](https://ohmyposh.dev/)
- [posh-git: A PowerShell environment for Git](https://github.com/dahlbyk/posh-git)
- [ZLocation: ZLocation is the new Jump-Location](https://github.com/vors/ZLocation)
- [gsudo Documentation](https://gerardog.github.io/gsudo/)
- [Terminal-Icons: A PowerShell module to show file and folder icons in the terminal](https://github.com/devblackops/Terminal-Icons)

## 雜記

- 在Windows與Linux使用PowerShell應該釐清各作業系統的內建指令與PowerShell cmd-let指令.
  Windows與Linux內建指令還是必須要學，然後使用 PowerShell 整合棄用Bash.
  但務求操作步驟一致而不用重新學習.
- PowerShell Markdown
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

- [PowerShell Documentation - PowerShell | Microsoft Learn](https://learn.microsoft.com/en-us/powershell/)
- [圖書：30天挑戰精通 Powershell](https://webpacx.ksml.edu.tw/bookDetail/1775845)
- [Windows 終端機推薦 — Windows Terminal 美化。將 Terminal 改造成你喜歡的樣子！😍 | by Molly Chi | Medium](https://molly1024.medium.com/windows-%E7%B5%82%E7%AB%AF%E6%A9%9F%E6%8E%A8%E8%96%A6-windows-terminal-%E7%BE%8E%E5%8C%96-%E5%B0%87-terminal-%E6%94%B9%E9%80%A0%E6%88%90%E4%BD%A0%E5%96%9C%E6%AD%A1%E7%9A%84%E6%A8%A3%E5%AD%90-9f6835951837)
- [如何打造一個華麗又實用的 PowerShell 命令輸入環境 | The Will Will Web](https://blog.miniasp.com/post/2021/11/24/PowerShell-prompt-with-Oh-My-Posh-and-Windows-Terminal)

## Windows PowerShell 5.1

- 相關位置
  ```PowerShell
  C:\Windows\System32\WindowsPowerShell
  C:\Program Files\WindowsPowerShell
  C:\Users\user\OneDrive\文件\WindowsPowerShell
  ```
- 插件
  [MScholtes/PS2EXE: Module to compile powershell scripts to executables](https://github.com/MScholtes/PS2EXE)
