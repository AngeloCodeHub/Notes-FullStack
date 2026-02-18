
- [Chat－Postgres資料庫備份](https://www.perplexity.ai/search/ru-he-bei-fen-supabasezi-liao-jftOPoh6T1Olj3vBM_m8bA)

## Supabase Cli

- 備份
  ```PowerShell
  supabase db dump --db-url "postgresql://postgres:postgres@127.0.0.1:54322/postgres" -f schema.sql
  
  supabase db dump --db-url "postgresql://postgres:postgres@127.0.0.1:54322/postgres" -f data.sql --use-copy --data-only
  ```
- restore  
  使用 Supabase Studio SQL Editor貼上

## pg_dump

- 備份
  ```PowerShell
  $pg_dump = "C:\Program Files\PostgreSQL\18\bin\pg_dump.exe"
  & $pg_dump "postgresql://postgres:postgres@127.0.0.1:54322/postgres" `
	  --schema=public `
	  -f public_backup.sql
  ```
- restore
  ```PowerShell
  $env:PGHOST = "localhost"
  $env:PGDATABASE = "postgres"
  $env:PGPORT = "54322"
  $env:PGUSER = "postgres"
  & "C:\Program Files\PostgreSQL\18\bin\psql.exe" -f "public_backup.sql"
  ```

## pg_restore

- pg_restore 是一個用於從 [pg_dump](https://www.postgresql.org/docs/17/app-pgdump.html "pg_dump") 建立的非純文字格式歸檔檔案中還原 PostgreSQL 資料庫的實用程式
