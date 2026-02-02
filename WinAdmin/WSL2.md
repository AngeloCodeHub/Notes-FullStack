## 記事

- 更名（使用registry）
  `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Lxss`
- [本機Localhost可直接Nat訪問 WSL]([Accessing network applications with WSL | Microsoft Learn](https://learn.microsoft.com/en-us/windows/wsl/networking))
- Windows訪問 WSL方法與路徑
  `\\wsl.localhost\Ubuntu-01`
- Ubuntu 在 wsl 只有2G多
- 安裝：【虛擬機器平台】【Windows子系統Linux版】兩個元件都要勾選
- [Advanced settings configuration in WSL | 設定檔文件](https://learn.microsoft.com/en-us/windows/wsl/wsl-config)
- （.wslconfig）預設是不存在，可自行新增，官方建議使用 GUI（wsl settings），在開始功能表
- [Chat－WSL全域設定](https://www.perplexity.ai/search/ru-he-diao-zheng-windows-wsl-h-KhDaVkaqQcWhXkF_JiMfiA)
- WSL distributions 是僅適用 wsl的linux發行版，與自行安裝的linux不同

## 常用命令

* `wsl -l -v`：列出所有 WSL 發行版及其版本。
* `wsl --update`：更新 WSL。
* `wsl --install Ubuntu-24.04 --location d:\WSL-VM --name 名稱`
* `wsl --list --online`：列出可用的 WSL 發行版。
* `wsl -d Ubuntu`：啟動指定的 WSL 發行版（例如 Ubuntu）。
* `wsl --terminate Ubuntu`：
  關閉指定的 WSL 發行版（例如 Ubuntu）。
* `wsl --set-default Ubuntu`：將 Ubuntu 設為預設 WSL 發行版。
* `wsl --unregister Ubuntu`：取消註冊 Ubuntu 發行版並刪除資料。
  安裝 Ubuntu 24.04 發行版並指定安裝位置。
* `wsl --export Ubuntu-24.04 D:\WSL-VM\Ubuntu-24.04.tar`：
  將 Ubuntu 24.04 發行版導出為 tar 檔案。
* 安裝 Linux發行版並指定路徑與名稱
  `wsl --install Ubuntu-24.04 --name Supabase --location D:\WSL-VM\Supabase`

## 參考

- [Set up Node.js on WSL 2 | Microsoft Learn](https://learn.microsoft.com/en-us/windows/dev-environment/javascript/nodejs-on-wsl)
- [Windows Subsystem for Linux Documentation | Microsoft Learn](https://learn.microsoft.com/en-us/windows/wsl/)
- [Ubuntu 上安裝 Node.js 最完整指南｜三大方法比較、步驟與常見問題全解析 - オープンソースの力を活用する方法～Ubuntuの世界へようこそ～](https://www.linux.digibeatrix.com/zh/development-environment-setup/ubuntu-nodejs-install-guide/)

## WSL 不適合 Production

- [ChatGPT](https://chatgpt.com/share/694289aa-4460-8006-a11a-95cf5c14ba05)
- [Microsoft Copilot: Your AI companion](https://copilot.microsoft.com/chats/qD6ss2PyPkhXJVubpzR2v)
