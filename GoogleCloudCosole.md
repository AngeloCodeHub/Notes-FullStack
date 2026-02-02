## 20251025 todo bug fix
- [x]  鳳山同 ip 不同 port 問題
- [x] Google Sheet 鳳山楠梓 要寫入的資料表不一樣，要修正成不用改程式
## node-google-spreadsheet 雜記
- row set assign 會直接覆蓋資料
- Sheet 沒有資料回傳是空字串而不是 null
- sheet.getrows（）回傳陣列，首行固定那一行不會列入 length
- 疑問：row 的 api query 是每一行，如果太多行 google 會 limit
  A：只能用 cell 方式
- 為什麼 google console 看不到 api 使用?

## references
- [Google Sheets API  |  Google for Developers](https://developers.google.com/workspace/sheets)
- [Google Drive  |  Google for Developers](https://developers.google.com/workspace/drive)
- [Apps Script  |  Google for Developers](https://developers.google.com/apps-script)
- [Usage limits  |  Google Sheets  |  Google for Developers](https://developers.google.com/workspace/sheets/api/limits)
  每分鐘 300 次 request
- [theoephraim/node-google-spreadsheet: Google Sheets API wrapper for Javascript / Typescript](https://github.com/theoephraim/node-google-spreadsheet)
- [GCP Sheet API Console](https://console.cloud.google.com/apis/api/sheets.googleapis.com/metrics)
- [googleapis/google-auth-library-nodejs: 🔑 Google Auth Library for Node.js](https://github.com/googleapis/google-auth-library-nodejs)
- [googleapis/google-api-nodejs-client: Google's officially supported Node.js client library for accessing Google APIs. Support for authorization and authentication with OAuth 2.0, API Keys and JWT (Service Tokens) is included.](https://github.com/googleapis/google-api-nodejs-client)
- [googleapis/nodejs-local-auth: A standalone library for receiving Google OAuth tokens](https://github.com/googleapis/nodejs-local-auth)
## GCP
- 每個頁面主體都是一個 project
- 依專案選擇產品
- 選擇專案
  導覽選單→Cloud總覽→歡迎使用→選擇專案
- 關閉 project
  產品→帳單→動作→停用計費功能
  產品→IAM→設定→關閉→30天後自動刪除
