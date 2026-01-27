# Javascript 套件管理（npm｜Bun｜pnpm｜deno）

- [nvm-windows: A node.js version management utility for Windows. Ironically written in Go.](https://github.com/coreybutler/nvm-windows)
- [npm/node-semver: npm語義化版本管理](https://github.com/npm/node-semver#versions)

## 紀錄

- 使用 Bun 安裝@react/type在next.js build會跳類型錯誤，next.js最好還是使用npm或是pnpm

## Windows

- nvm windows本體安裝位置，安裝時需要提高權限
  `C:\Users\user\AppData\Local\nvm`
- nvm windows，node安裝位置（包含全域npm套件）
  `C:\Users\user\AppData\Local\nvm\版本`
- nvm node.js 連結（Windows）
  `C:\nvm4w\nodejs`
- Bun套件路徑（Windows），執行檔
  `c:\Users\user\.bun`
- pnpm 全域套件位置
  `C:\Users\user\AppData\Local\pnpm\global\5`
- Bun全域套件位於家目錄（包含Packages.json）
- repo裡corepack升級pnpm
  ```PowerShell
  corepack use pnpm@10.25.0
  ```
