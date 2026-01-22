# Powershell互動式terminal腳本
  
  > 使用 Powershell 寫一個 Powershell 互動式純 terminal Script

## 規格說明

- OS：Windows 11
- Powershell版本：7 or later
- 純 terminal 互動，不開啟任何 GUI

## 程式說明（基礎互動）

    > 寫一個互動式腳本，有三個光棒可做選擇並且可複選，內容字串為以下陣列
    > ["Hello World!","Hello Powershell!","Hello Terminal!"]
    > 被選擇到的選項則 write-host 出選擇到的選項字串

## 程式說明（進階）

    > 在基礎互動只實現 Write-out String，現在要進階到多選的 terminal 互動來 stop-process.
    > 首先檢查 process的name $options = @("Perplexity", "LINE", "Poe") 是否running，是的話
    > 就在選擇項列出並可複選，選擇完畢後按 enter鍵 stop-process選中的process
