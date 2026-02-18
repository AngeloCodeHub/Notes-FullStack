
## 記事

- 只支援 Gemini模型
- 預設會讀取作業系統的環境變數，也可以自訂環境變數（.env）路徑（全域或是專案目錄）
  ```Text
  ~\.gemini\.env
  .\.gemini\.env
  ```
- [谷歌免费AI神器来了！Gemini CLI保姆级教程：任务管理、编程、MCP全搞定🔥 解决认证失败！100万Token超长上下文！](https://www.youtube.com/watch?v=OFvujFZJ-9k)
- [保哥帶你聽 EP05｜快速上手 Gemini CLI 開發工具 - YouTube](https://www.youtube.com/watch?v=0YVUkrqBJPg)
- [Chat－Gemini.md放置位置](https://gemini.google.com/share/cd0a1a1fa3db)
- [Build, debug & deploy with AI | Gemini CLI](https://geminicli.com/)
- [Quotas and limits  |  Gemini Code Assist  |  Google for Developers](https://developers.google.com/gemini-code-assist/resources/quotas)
- 指令位置－專案目錄  
  資料交換格式：toml  
  ```Text
  .gemini/
		├── commands/
		└── skills/
  ```
- extensions
  ```Text
  C:\Users\user\.gemini\extensions
  ```
- 設定檔（全域）：`C:\Users\user\.gemini\settings.json`
  也可在專案目錄，則是 .gemini前面改成專案目錄  
  MCP Server也是設定在這裡
- Skill目錄，可以是.agent與.gemini
  [Agent Skills | Gemini CLI](https://geminicli.com/docs/cli/skills/#skill-discovery-tiers)
- Extensions是包括prompts, MCP servers, custom commands, themes, hooks, sub-agents, and agent skills

## FAQ

- 在 IDE內整合Gemini-CLI有什麼優勢?
  [IDE integration | Gemini CLI](https://geminicli.com/docs/ide-integration/)
