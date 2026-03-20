# Supabase self-hosting全攻略

## Ubuntu Linux

1. [[Hyper-V]]
2. 安裝 Ubuntu Linux  
   [Ubuntu Server tutorial - Ubuntu Server documentation](https://ubuntu.com/server/docs/tutorial/)
3. apt update；apt upgrade
4. [安裝 Docker](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository)
5. [Supabase Self-Hosting Guid](https://supabase.com/docs/guides/self-hosting/docker)  
   [Self-hosting 原始碼](https://github.com/supabase/supabase/tree/master/docker)  
   使用 ghgrab下載覆蓋  
   ```PowerShell
   ghgrab --cwd --no-folder `
   https://github.com/supabase/supabase/tree/master/docker
   ```
6. env設定，使用官方工具更改
7. Docker compose設定  
   避開Windows 8000 port 號
8. 設定 Apache 反向代理
9. 安裝必要 VSCode Extensions

## Update

1. 停用Supabase  
   ```PowerShell
   docker compose down
   ```
2. sudo apt update
3. 升級 Supabase
   記事：升級後DB無法啟動，需 reset.sh

## Notes

- kong-entrypoint.sh 在 linux檔案權限要更改否則 kong 啟動不了
