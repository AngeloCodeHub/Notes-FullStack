# Supabase self-hosting全攻略

## WSL

1. WSL 新增一個ubuntu image－[[WSL2]]
2. 升級 ubuntu 套件
3. [安裝 Docker](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository)
4. [安裝 Supabase](https://supabase.com/docs/guides/self-hosting/docker)或直接專案啟動
   docker-compose.yml 處理
   .env檔案處理
   [supabase/docker at master · supabase/supabase](https://github.com/supabase/supabase/tree/master/docker)
5. Git 升級
   [First time git setup](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)
6. [[安裝-Git與GitHub-Cli]]
7. 安裝必要 VSCode Extensions

## Windows Ubuntu VM（Production）

1. [[Hyper-V]]
2. 虛擬機安裝 Ubuntu Linux
   [Ubuntu Server tutorial - Ubuntu Server documentation](https://ubuntu.com/server/docs/tutorial/)
3. 安裝 Docker
4. Git Clone supabase專案
5. 複製 .env
6. 設定 Apache 反向代理

### ToDo

- [ ] 如何升級以及刪除 docker image

### note

> - 使用檔案總管或是 VSCode 開啟 ubuntu的supabase資料夾都會自動啟動wsl
> - self-hosting的套件要與 dev cli 齊版
> - 專案資料夾不能位於 Windows NTFS檔案系統，要位於 WSL 內部純Linux路徑
> - 第一次啟動就會把 .env 資料寫進去，後來在改的話就無法啟動，需reset


