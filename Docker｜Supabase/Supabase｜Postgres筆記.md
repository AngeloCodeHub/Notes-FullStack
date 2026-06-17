
## FAQ

- [x] supabase-cli config 指定id會自動link嗎?  
      A：會，當db pull會自動連結
- [ ] supabase/seed.sql 是作什麼用?
- [x] [publishable key與 anon key與 service_role key](https://supabase.com/docs/guides/api/api-keys)  
      service role key 是不能公開的
- [ ] self-hosting需要安裝 Deno嗎?

## Notes

- cli db pull是拉一份migration

## 開發環境與工具

- Supabase-CLI
- psql、pgdump
- Pgadmin
- [PostgreSQL - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-ossdata.vscode-pgsql)  
  說明：連接 Posgres資料庫，直截編寫sql並執行
- [MySQL – Open VSX Registry](https://open-vsx.org/extension/cweijan/vscode-mysql-client2)
- [Supabase - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=Supabase.vscode-supabase-extension)  
  整合 Copilot
- [[LSP筆記]]：Postgres Language Server
- [1000+ PostgreSQL EXTENSIONs](https://gist.github.com/joelonsql/e5aa27f8cc9bd22b8999b7de8aee9d47)

## 教學

- [Learn Postgres - YouTube](https://www.youtube.com/playlist?list=PL5S4mPUpp4Ote6F9ScnXevuOyCnvzahRV)
- [PostgreSQL Course for Beginners](https://www.freecodecamp.org/news/posgresql-course-for-beginners)
- [PostgreSQL: The world's most advanced open source database](https://www.postgresql.org/)
- [PostgreSQL 正體中文使用手冊](https://docs.postgresql.tw/)
- [三十天，PG與我 :: 2022 iThome 鐵人賽](https://ithelp.ithome.com.tw/users/20114934/ironman/4984)
- [資料庫新手入門--以PostgreSQL為例 :: 2022 iThome 鐵人賽](https://ithelp.ithome.com.tw/users/20129430/ironman/5469)
- [Introduction to the course - Intro to Postgres - Database School](https://databaseschool.com/series/intro-to-postgres/videos/203)
- [SQL 教程|极客教程](https://geek-docs.com/sql/sql-top-tutorials/1000100_sql_index.html)
- [Postgres vs. MySQL - DEV Community](https://dev.to/outerbase/postgres-vs-mysql-14cp)
- [讓資料庫查詢飛起來！用 AI 自動最佳化 PostgreSQL 效能的開源神器 | RepoInside | RepoInside](https://repoinside.com/mayfer/dbpill)

## References

- [Chat－Postgres架構](https://chatgpt.com/c/6968192e-3708-8320-bc49-1db678babb35)
- [Chat－Authentication user欄位釋疑](https://chatgpt.com/c/6958b4bf-f3f0-8323-9800-954726d5d6cb)
- [Chat－self-hosting Supabase cli](https://gemini.google.com/app/688abebe237ac1f3)
- [Chat－Next.js與supabase代理模式建置](https://chatgpt.com/c/6940bf9c-ab94-8324-b7db-f3217fbad471)
- [Chat－Supabase 學習路線圖](https://chatgpt.com/c/692f81a5-1d2c-8328-9f97-29fa982d6786)
- [Chat－Supabase public資料庫與table設計+多租戶](https://chatgpt.com/c/6949c1fb-ee70-8323-8de8-c841e62cf07f)
- [Chat－自架時使用 cli方式](https://gemini.google.com/app/688abebe237ac1f3)
- [Chat－postgres rest與anon key](https://gemini.google.com/app/c2038d40f41ab581)
- [Chat－Supabase RLS vs MySQL 權限機制](https://gemini.google.com/app/09f71fbcff2501c7)
- [Chat－Supabase API 產生與規則解析](https://gemini.google.com/app/1e145ec4e106c51d)
- [PostgREST Documentation — PostgREST 14 documentation](https://docs.postgrest.org/)
- [Neon Serverless Postgres — Ship faster](https://neon.com/)
- [Supabase Full Course 2025 | Become a Supabase Pro in 1.5 Hours](https://www.youtube.com/watch?v=kyphLGnSz6Q)
- [Azure Database for PostgreSQL documentation landing page | Microsoft Learn](https://learn.microsoft.com/en-us/azure/postgresql/)
- [bcrypt.js](https://github.com/dcodeIO/bcrypt.js)
- [Prisma | Instant Postgres plus an ORM for simpler db workflows](https://www.prisma.io/)
- [PostgreSQL 角色權限 Roles and Privileges | PJCHENder I/O](https://pjchender.dev/database/psql-roles-privilege/)
- [pgcli](https://www.pgcli.com/)
- [我獨自開發 - Supabase 打造全端應用 :: 2025 iThome 鐵人賽](https://ithelp.ithome.com.tw/users/20147822/ironman/8754)

## References－Postgres.Org

- [PostgreSQL: Documentation: 17: SQL Commands](https://www.postgresql.org/docs/17/sql-commands.html)
- [PostgreSQL: Documentation: 17: Appendix C. SQL Key Words](https://www.postgresql.org/docs/17/sql-keywords-appendix.html)
- [PostgreSQL: Documentation: 17: Part II. The SQL Language](https://www.postgresql.org/docs/17/sql.html)
- [PostgreSQL: Documentation: 17: CREATE POLICY](https://www.postgresql.org/docs/17/sql-createpolicy.html)
- [PostgreSQL: Documentation: 17: 5.9. Row Security Policies](https://www.postgresql.org/docs/17/ddl-rowsecurity.html)


## Postgres Javascript SDK

- [porsager/postgres: Postgres.js - The Fastest full featured PostgreSQL client for Node.js, Deno, Bun and CloudFlare](https://github.com/porsager/postgres)
- [node-postgres](https://node-postgres.com/)

## Community

- [Supabase－reddit](https://www.reddit.com/r/Supabase/)

## Supabase Next.JS 練習套件

- [官方 Demo](https://supabase.com/docs/guides/getting-started/tutorials/with-nextjs?queryGroups=database-method&database-method=dashboard)
- [Next.JS Starter Template](https://vercel.com/templates/authentication/supabase)  
  Shadcn
- 基礎套件
  ```PowerShell
  create-next-app -e with-supabase
  ```

