- [講某個檔案在某個commit移到其他commit](https://www.perplexity.ai/search/wo-shi-yong-git-revert-to-mou-VSQRxtvkTxuIhYfEIVLGRA)
- revert 是在回滾到某個commit並解決衝突後創造出另一個commit而不破壞歷史commit，reset是強制回滾歷史commit被丟棄
- 在GitHub 上的改變文件 fetch回來後，vscode執行揀選，並強制 push即可合併
- [git status顯示unicode問題](https://www.perplexity.ai/search/zuo-ye-xi-tong-windows11-shi-y-OfDl134mTa2RfPT5J1rzOQ)
  ![git問題](http://www.xn--djroe106hl2fyz1bszc.online/Git%E5%95%8F%E9%A1%8C-001.png)
- 子目錄也能放 .gitignore 檔案
- [First time git setup](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)
- 當設定檔 symlink=false，經過git處理後只會回復符號連結本身，要改成true
  當改成 true 經過git處理要回復需要最高權限
- [Chat－將某 commit 塞進某 Commit（重建基底）](https://gemini.google.com/app/b1a1eac33fabb3a6)
- 檔案在加入 ignore 之前就 commit 存在的，會 ignore無效，需使用
  ```shellscript
  git rm env.json --cached
  ```
- git add . 與--all，差別 . 只會把當前folder與子folder add進，-all則會是整個專案
- [解决不同系统换行符号导致的Git同步问题 - 经验分享 - Obsidian 中文论坛](https://forum-zh.obsidian.md/t/topic/43203/1)
- 基本流程
working Directory→暫存區(Staging Aera)→commit→repository→push→GitHub
- VSCODE重訂基底有衝突時，目前變更（基底），來源變更（working dir）
- 觀念：在stage裡的檔案表示與索引（index）的檔案是一致的並準備commit的檔案
	已commit與已加入stage都稱為已被索引
- Git checkout會切換到指定的分支，但如果後面接的是檔名或路徑，Git 則不會切換分支，而是把檔案從 .git 目錄裡拉一份到目前的工作目錄。
- [git與github連結(使用ssh)](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/about-ssh)，使用https協定需用token忽略兩階段驗證
- git reset回復到某個版本，有mixed、soft、hard模式
- git與svn處理更名和移動的方式不一樣，svn需使用內建指令，否則log會斷掉
- git remote add：新增遠端節點
- git fetch XXXX：不會改變modified
- [Git 時光機回復版本的 2 種方法 reset & checkout](https://www.maxlist.xyz/2020/05/03/git-reset-checkout/)
- [Git: 讓你的代碼回到過去，git reset 與 git revert 的用處](https://roykwokcode.medium.com/%E8%AE%93%E4%BD%A0%E7%9A%84%E4%BB%A3%E7%A2%BC%E5%9B%9E%E5%88%B0%E9%81%8E%E5%8E%BB-git-reset-%E8%88%87-git-revert-%E7%9A%84%E7%94%A8%E8%99%95-6ba4b7545690)
- [How can I download a specific folder from a GitHub repo?](https://github.community/t/how-can-i-download-a-specific-folder-from-a-github-repo/278/1)
- clone".git"，不clone檔案內容
	```Powershell
	git clone --filter=blob:none --no-checkout git@github.com:photonstorm/phaser3-examples.git ./
	```

### 原型儲存庫（也是一種備份方法）

```Powershell
# 建立原型儲存庫
git init --bare NewRepository.git

# 一般儲存庫轉換為原型儲存庫
git clone --bare my_project myproject.git
```

### Git Repo 封存備份

```Powershell
# 整個 repo 壓縮備份（不含 commit）
git archive main --format=zip --output=../repbck.zip
# 可選擇備份某個分支
git archive head --format=zip --output=../repbck.zip

# 儲存庫匯出一份可供還原的快照（包含完整的 commit）
git bundle create ../repo.bundle main
# 還原快照
git clone repo.bundle repo -b main
```

### 使用案例

- 撤銷所有還沒有stage但已經track的檔案，主要是hard參數，reset有三個重要模式參數
	reset是重要指令，要熟記
	```Powershell
    git reset head^ --hard
    # 捨棄最近一次commit，回到上一次
    git reset head^
    # 修改最近一次commit註解訊息
    git commit --amend -m "新的註解訊息"
    # 不修改訊息
    git commit --amend --no-edit
	```

- 撤銷（刪除）未追蹤的檔案
    
    ```powershell
    # 撤銷（刪除）未追蹤的檔案，f：force、d：untracked檔案
    git clean -fd
    # x參數會清空gitignord檔案與目錄
    git clean -fdx
    ```
    

- 顯示資訊
    
    ```powershell
    git log
    # 查看commit做了哪些事
    git log --stat
    git status
    git log -n 5 --stat
    ```
    
- 回復所有改變過的檔案（未stage）
    
    ```powershell
    git restore .
    git checkout .
    ```
    
- project移除git版控
    
    ```powershell
    remove-item -Recurse -Force .\.git\
    ```
    
- 將某些檔案回滾到某狀態，checkout指令是分支指令，單個檔案也是使用checkout
    
    ```powershell
    # 範例：將index.html回滾到某次commit狀態，
    git checkout 7bbde60 index.html
    ```
    
- clone一個github到本地
    
    ```powershell
    # 範例：clone pixi專案至當前目錄PixiExample，後面加depth為commit的深淺
    git clone https://github.com/pixijs/examples.git ./PixiExample --depth 1
    ```
    
- 設定檔
    
    ```powershell
    # 查看config設定檔 全域repo
    git config --global -l
    git config -l
    
    # 處理LF與CRLF。注意要加 set，沒加 set會多加一行同樣的 key設定值
    # 當出現 error: wrong number of arguments, should be 2
    # 表示 core.autocrlf true 要放在第二個參數（--global之後）
    git config set --global core.autocrlf true
    
    # 查看各設定檔的層級，init 一個 repo會從上層複製過來
    git config --list --show-origin
    
    # 遠端有修改過Commit 在pull時強制覆蓋
    git config pull.rebase true
    ```
    
- 移除分支（參數-d移除已經合併，-D移除未合併）
    
    ```powershell
    git branch -d branch_name
    git branch -D branch_name
    ```
    
- 取出其他分支合併特定檔案，路徑如果是bitbash要使用反斜線
    
    ```powershell
    git checkout "源分支" "檔名相對路徑1" "檔名相對路徑2"
    ```
    
- 重建基底，rebase
    
    ```powershell
    # 互動式選取重建基底的範圍
    git rebase -i 000xxx
    
    # rebase失敗，撤銷重建基底工作
    git rebase --abort
    ```
    

---

### help

```powershell
git help
# 列出全部command
git help -a
# git觀念與原理
git help -g
# 以網頁開出help（較詳盡）
git help commit
git commit --help
# 終端機列出可用參數
git 指令 -h
```

### 學習資源

- [30天精通Git版本控管 :: 2013 iT 邦幫忙鐵人賽](https://ithelp.ithome.com.tw/users/20004901/ironman/525)
- [Will 保哥：30 天精通 Git 版本控管（網頁版）](https://doggy8088.github.io/Learn-Git-in-30-days/)
- [【Git】從零開始學習 Git - 30 天的學習筆記 :: 2021 iThome 鐵人賽](https://ithelp.ithome.com.tw/users/20141010/ironman/4499)
- [高見龍：為你自己學 Git](https://gitbook.tw/)
- [Git Flow 介紹與 GitHub Flow 介紹入門教學筆記 | 學習筆記 - KD's Tech Blog 技術部落格 | KD Chang 張凱迪](https://tech.kdchang.net/2024/12/04/learning-notes-git-flow-github-flow-intro-tutorial/)
- [文章：Git 與 Github 版本控制基本指令與操作入門教學](https://blog.techbridge.cc/2018/01/17/learning-programming-and-coding-with-python-git-and-github-tutorial/)
- [Gemini 對話](https://gemini.google.com/app/db6f955a27eacc99)
- [適合初學者的簡單 Git 教程](https://nulab.com/zh-tw/learn/software-development/git-tutorial/)
- [學會 Git，加入全球最大同性交友網站！](https://kopu.chat/coding/#git)
- [Git & GitHub 教學手冊 - W3HexSchool](https://w3c.hexschool.com/git/7ca21e02)
- [鐵人賽：不熟 Git 嗎？好巧我也是，不如我們一起來學吧！](https://ithelp.ithome.com.tw/users/20162483/ironman/6374)
- [Will 保哥：30 天精通 Git 版本控管（GitHub 版）](https://github.com/doggy8088/Learn-Git-in-30-days)
- [Will 保哥：YT Git版本控管視訊](https://www.youtube.com/watch?v=E_Nd0anNI6M&list=PL_dAxk7-NoFvcn8NRVgvwX1aLh_LrGpG0)

### 官方使用手冊

- [Git Cheat Sheet](https://git-scm.com/cheat-sheet)
- [Git - Reference](https://git-scm.com/docs)
- [Git - git-clone Documentation](https://git-scm.com/docs/git-clone)
- [Git - git-remote Documentation](https://git-scm.com/docs/git-remote)
- [Git - git-fetch Documentation](https://git-scm.com/docs/git-fetch)
- [Git - git-diff Documentation](https://git-scm.com/docs/git-diff)
