# 方法與筆記

## 步驟

1. 把要 import 的 repo add，這邊是本地磁碟路徑當成 remote
2. add 至本地 repo 實體路徑把他命名為 importer
```Bash
git remote add importer C:/Users/user/WorkSpace/nextjs-dashboard
```
3. 檢查是否有正確 add
```Bash
git config -l --local

remote.importer.url=C:/Users/user/WorkSpace/nextjs-dashboard
remote.importer.fetch=+refs/heads/*:refs/remotes/importer/*
```
4. 此時 git 顯示 importer 屬於 remote，要切換到對應的 branch，使成為原repo分支
   可進行merge
```Bash
git checkout -b importer importer/main
```
5. 開啟編輯器或是直接下只領，移除步驟2 add 的 remote，此時可把分支推送到原本 repo remote
```Bash
git config edit --local
   
git config unset remote.importer.url
git config unset remote.importer.fetch
```
6. 此時兩個分支互相獨立，沒有共同 ancestor，要 merge 要加
   --allow-unrelated-histories 參數

## FAQ

## References

- 
