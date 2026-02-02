# VHD Server架設

利用Windows檔案分享VHD虛擬磁碟給客戶端使用

## 背景

- 某些程式只能明確在本機磁碟運行
- Google Chrome無法透過網路磁碟執行（閃退）
- Electron.JS需加 no-sandbox才能在網路磁碟運行

## 疑問

- [ ] 當VHD被其他機器掛載時該如何強制卸載

## 參考文件

- [Chat-架設iSCSI](https://www.perplexity.ai/search/windows-serverjia-she-iscsigei-h16y_sKHTrSUo78nMlxRKA)

## 記事

- WinServer安裝iSCSI目標伺服器時會同時安裝檔案伺服器
- Perplexity提供把VHDX檔案直接設定為唯讀是不可行，VHDX會壞掉需重建
- iSCSI掛載無法設定為唯讀，改用直接掛載VHD

## 步驟

1. 新建一個VHD並掛載存入程式
2. 部署到Server（C槽）
3. 開網路共用（讀取/寫入）
4. NTFS權限
5. VHD檔案屬性設為唯讀
6. 單機Script掛載
