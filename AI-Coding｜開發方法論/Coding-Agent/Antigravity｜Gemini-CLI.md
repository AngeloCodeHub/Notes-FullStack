# 本篇以Antigravity為主

[[Gemini-CLI｜Code Assist]]

## FAQ

- next.js skills是放.agent(s)，AGY會查看 .agent(s)嗎?  
  A：經測試agy不會讀 agent(s)

## 記事

- Skills不用手動連接，也可明確指定
- MCP不用手動連接，Agent會自動判斷. 也可明確指定（使用@符號）.  
  格式為：`@mcp:lucide-svg:電腦`
- MCP Servers一律放在全域  
  `C:\Users\user\.gemini\antigravity\mcp_config.json`
- 新增mcp server、Skills、workflow需要重啟.
- AGY與cli新增mcp servers的方式有時不同，以supabase為例，agy要到mcp store新增，cli依照supabase官方文件新增
- 設定分為 VSCode與agy兩種設定模式
- Workflows就是在VSCode可重複使用的prompts
- 新增 rules 會跳出視窗讓你選active mode
- agy的user rules在 `~\.gemini\GEMINI.md`，不是在 `~\.antigravity`
- 工件（Artifacts）：工件是代理程式為實現更豐富對話體驗所產生的文件。
- F1 命令已經整合WSL
- [Working with Google Antigravity in WSL | by Dazbo (Darren Lester) | Google Cloud - Community | Nov, 2025 | Medium](https://medium.com/google-cloud/working-with-google-antigravity-in-wsl-944c96c949f3)
- Agent指令位置－專案目錄  
  資料交換格式：markdown  
  ```Text
  .agent/
		├── rules/
		├── skills/
	 	└── workflows/
  ```
- Agent指令位置－全域家目錄  
  ```Text
  # rules，此檔案與 Gemini-CLI 共用
  C:\Users\user\.gemini\GEMINI.md
  # workflows
  C:\Users\user\.gemini\antigravity\global_workflows\XXX.md
  ```

## Antigravity Agent

### Core Components

- Reasoning model
- Tools
- Artifacts
- Knowledge

### Customizations

- Agent Modes / Settings
- MCP
- Rules / Workflows

### Agent設定

- 快速設定：右下角（Antigravity Setting）
- 進階設定：進入快速設定 Advanced Setting


## 教學

- [ZhangYu-zjut/awesome-Antigravity](https://github.com/ZhangYu-zjut/awesome-Antigravity?tab=readme-ov-file)
- [Antigravity Rules & Workflows 實戰：讓 AI 自動遵循開發規範](https://memo.jimmyliao.net/p/antigravity-rules-and-workflows-ai)
- [【凱文大叔】手把手教你 Antigravity 設定與應用：規則（Rules）＋神技能（Skills）＋自動化（Workflows）打造最強AI 超能力！ - YouTube](https://www.youtube.com/watch?v=e-WNdM4JO2U)
