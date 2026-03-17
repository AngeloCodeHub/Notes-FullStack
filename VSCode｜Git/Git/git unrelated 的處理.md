
- 如果一個分支有unrelated當rebase會強制重新合併
  ```PowerShell
  git rebase -i 300590623504d2d10452ee222bc6ae152a981181 -X theirs
  ```
- gitignore 路徑要用Linux反斜線
- rebase 使用要小心
- 從 learn分支一個準備寫的小程式步驟
  1. 複製 Ref-Code
  2. Commit
  3. 有修改的檔案複製到 Ref-Code
  4. 合併 Ref-Code
