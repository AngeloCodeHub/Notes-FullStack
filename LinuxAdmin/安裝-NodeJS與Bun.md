
## Node.JS（Linux安裝 or Docker）

1. Linux 使用 nvm
   [nvm-sh/nvm: Node Version Manager](https://github.com/nvm-sh/nvm)
   注意：執行安裝腳本後需重啟 shell 使路徑生效
2. 列出線上可用的的 lts.
   `nvm ls-remote --lts`
3. 安裝
   `nvm install 24.13.0`
4. 確認安裝
   ```Bash
   nvm ls
   node -v
   ```

## Bun（Linux安裝 or Docker）

[Installation - Bun](https://bun.com/docs/installation)

1. 安裝 unzip：`sudo apt install unzip`
2. `curl -fsSL https://bun.com/install | bash`
3. 重啟 Shell
