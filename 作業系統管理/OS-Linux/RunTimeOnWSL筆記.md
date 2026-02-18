# 放在 WSL 的程式測試與筆記

## 程式（試著從Windows移除）

- PowerShell
- Git｜GitHub-CLI  
- Node.js｜Bun｜Deno
- OpenCode
- GitHub Copilot
- Curl  
  Ubuntu內建的curl建議不要升級

## 工作區

prettier使用AGY無法使用

- learn-nextjs

## Limitation

- Git 移除後，純 Windows 使用vscode會沒有git。
- 工具與專案最好在同一個作業系統，官方不建議跨作業系統處理檔案。  
  [Working across file systems | Microsoft Learn](https://learn.microsoft.com/en-us/windows/wsl/filesystems#file-storage-and-performance-across-file-systems)  
  個人實測 Learn-ElectronJS，run dev 時真的很慢，而且跑不起來

## 結論

- 所有工具還是要兩套，確保專案與工具都在同一個作業系統  
  除了 VSCode 系列
