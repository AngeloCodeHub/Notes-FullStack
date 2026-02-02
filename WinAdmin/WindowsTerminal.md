# Windows Terminal

WinTerminal管理Shell（PowerShell、BASH）.Shell管理CLI程式指令

## 插件

- [Home | Oh My Posh](https://ohmyposh.dev/) 客製化Shell
- [posh-git: A PowerShell environment for Git](https://github.com/dahlbyk/posh-git)
- [gsudo Documentation](https://gerardog.github.io/gsudo/)
- [ZLocation: ZLocation is the new Jump-Location](https://github.com/vors/ZLocation)
- [Terminal-Icons: A PowerShell module to show file and folder icons in the terminal](https://github.com/devblackops/Terminal-Icons)

## Shortcut

- 新增TAB：CTRL+SHIFT+T
  一個TAB可以有多Pane
- 右側新增 PANE：ALT+SHIFT++
- CTRL+SHIFT+PageUP：向上捲動
- 切換 markmode：CTRL+SHIFT+M
- 開啟設定檔（GUI）：CTRL+,
- 開啟設定檔（setting.json）：CTRL+SHIFT+,
- 在原本TAB開啟另一個PANE

## CTRL+SHIFT+P 命令

- 交換窗格（Pane）：Pane之間切換

## 雜記

- 多Pane之間不能拖拉大小

## 指令用法

- `wt sp`：在目前的 TAB 新增分割視窗（shortcut：ALT+SHIFT++）

## 設定

- System 預設設定檔：CTRL+ALT+，
  ```PowerShell
  C:\Program Files\WindowsApps\Microsoft.WindowsTerminal_1.23.13503.0_x64__8wekyb3d8bbwe\defaults.json
  ```
- 使用者設定檔路徑
  ```PowerShell
C:\Users\user\AppData\Local\Packages\Microsoft.WindowsTerminal_8wekyb3d8bbwe\LocalState\settings.json
  ```
- 使用GUI設定快速鍵
  設定→動作

## References

- [An overview on Windows Terminal | Microsoft Learn](https://learn.microsoft.com/en-us/windows/terminal/)
- [Terminal我只推薦Windows Terminal - HackMD](https://hackmd.io/@stephenchouchou/BJX5LD61d)
- [Windows 終端機推薦 — Windows Terminal 美化。將 Terminal 改造成你喜歡的樣子！😍 | by Molly Chi | Medium](https://molly1024.medium.com/windows-%E7%B5%82%E7%AB%AF%E6%A9%9F%E6%8E%A8%E8%96%A6-windows-terminal-%E7%BE%8E%E5%8C%96-%E5%B0%87-terminal-%E6%94%B9%E9%80%A0%E6%88%90%E4%BD%A0%E5%96%9C%E6%AD%A1%E7%9A%84%E6%A8%A3%E5%AD%90-9f6835951837)
- [如何打造一個華麗又實用的 PowerShell 命令輸入環境 | The Will Will Web](https://blog.miniasp.com/post/2021/11/24/PowerShell-prompt-with-Oh-My-Posh-and-Windows-Terminal)
- [Making Windows Terminal awesome with GitHub Copilot CLI - Microsoft for Developers](https://developer.microsoft.com/blog/making-windows-terminal-awesome-with-github-copilot-cli)

