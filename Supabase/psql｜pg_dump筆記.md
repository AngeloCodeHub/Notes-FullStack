## Help

### 互動式

- 顯示sql命令：`\h`
- 顯示殼層命令：`\?`

## 記事

- psql會讀取系統環境變數，可在 Scirpt預先加入環境變數而不用使用 pwsh-dotenv
  ```PowerShell
  $env:PGHOST="localhost"
  $env:PGDATABASE="postgres"
  $env:PGPORT="54322"
  $env:PGUSER="postgres"
  & "C:\Program Files\PostgreSQL\18\bin\psql.exe"
  ```
- [PostgreSQL: Documentation: 17: 32.15. Environment Variables](https://www.postgresql.org/docs/17/libpq-envars.html)
