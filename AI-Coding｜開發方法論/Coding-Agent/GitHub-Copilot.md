# GitHub Copilot 學習筆記

	包含 VSCode GitHub Copilot Chat extension、GitHub Copilot CLI

## ToDo

- [ ] Setting：github.copilot、chat

## FAQ

- [ ] 代理交接的方法
- [ ] 設定instructions位置  
      A：setting→chat.instructionsFilesLocations
- [ ] 使用者全域的 copilot-instruction.md放在哪裡
- [ ] Background 與Could、Local Agent  
      A：Background Agent 就是 Copilot Cli  
      [2025年11月（版本1.107） --- November 2025 (version 1.107)](https://code.visualstudio.com/updates/v1_107#_continue-tasks-in-background-or-cloud-agents)
- [ ] 可自訂聊天參與者嗎（@）  
      [Chat Participant API | Visual Studio Code Extension API](https://code.visualstudio.com/api/extension-guides/ai/chat)
- [ ] copilot-instructions.md 檔案，如果 user與workspace都有會疊加嗎?  
      A：是的，工作區層級的指示通常用於專案特定的規範，而使用者層級的指示則用於個人偏好的編碼風格。
- [ ] 如何禁止 Agent 讀取 ref-Code 內容  
      A：在 instructions 告訴他

## GitHub Copilot 目錄結構

資料交換格式：markdown

- 全域Tools  
  `C:\Users\user\AppData\Roaming\Code\User\prompts`
- Plugins 安裝目錄  
  `C:\Users\user\AppData\Roaming\Code\agentPlugins`
- `.github/copilot-instructions.md`  
  此檔案適用所有 Chat 的 intruction，Copilot 會自動帶入
- `.github/instructions/`
- `.github/agents/*.agent.md`：Custom Agent
- `.github/prompts/`
- `.github/skills/`
- `C:\Users\user\AppData\Roaming\Code\User\prompts\*.instructions.md`  
  全域 instructions
- copilot設定檔  
  `C:\Users\user\.copilot\config.json`
- 全域 Skills（Linux）  
  `~/.copilot/skills`  
  `~/.agents/skills`
- 全域MCP  
  `C:\Users\user\AppData\Roaming\Code\User\mcp`

## 通用

- [在處理複雜任務時，您可以將子任務委派給子代理程式。子代理程式是獨立的 AI 代理，它執行特定的工作，例如研究某個主題、分析程式碼或審查更改，並將結果報告給主代理。由於每個子代理程式都在其自身的上下文視窗中運行，因此不會幹擾您的主對話。 VS Code 還可以並行運行多個子代理，從而加快多步驟任務的處理速度。](https://code.visualstudio.com/docs/copilot/agents/subagents)
- 插件  
  Plugins extend Copilot CLI with additional skills, agents, hooks, MCP servers,and LSP servers. They can be installed from plugin marketplaces, GitHub repositories, repository subdirectories, or direct git URLs.
- Copilot-CLI 內建兩個插件市場  
    ◆ copilot-plugins (GitHub: github/copilot-plugins)  
    ◆ awesome-copilot (GitHub: github/awesome-copilot)

## VSCode

- 查看已經載入的 instructions，Chat view右鍵→Diagnostics
- [全域使用者 instructions](https://code.visualstudio.com/docs/copilot/customization/custom-instructions#_instructions-file-locations)
- Background agents非常適合委派無需立即互動的任務。  
  They use Git worktrees to isolate file changes from your main workspace and prevent conflicts.
- Ask與Plan mode也是一個Agent，只是在調用Tools上不同
- [**自訂代理程式**](https://code.visualstudio.com/docs/copilot/customization/custom-agents)  
  可讓您為代理程式定義不同的角色，每個角色都有自己的指令、可用工具、語言模型，並且可以選擇將任務轉交給其他代理程式。內建的 Plan 代理專門用於建立功能實現計劃。它僅擁有唯讀工具的存取權限，用於執行深入的研究和分析，並將概述詳細的實作方案，而不會修改程式碼庫。
- inline chat不會考慮 agent的上下文
- [Manage chat sessions－匯出Chat](https://code.visualstudio.com/docs/copilot/chat/chat-sessions#_save-and-export-chat-sessions)
- inline suggestions，VS Code 會分析編輯器中目前開啟的檔案和已開啟的文件
- [Copilot Prompt 3S 原則](https://www.youtube.com/watch?v=Mb5iThLRgfE)
- CTRL+ALT+SHIFT+L：快速聊天
- [Context（#-mention）](https://code.visualstudio.com/docs/copilot/chat/copilot-chat-context)  
  使用Agent時，Agent會根據您的提示自主決定是否需要將活動檔案新增至聊天上下文，ask 則自動在編輯器活動檔案自動加入  
  也可調用某 agent的部分內容
- （#-mention）與（@-mention）差異  
  （#-mention）：新增上下文或調取 tools，可包含檔案、skills...  
  （@-mention）：新增聊天參與者，處理特定領域的請求  
  可以在單一聊天請求中包含多個上下文，但一次只能有一個聊天參與者處於活動狀態。
- 反斜線 `/` 就等於 chat 快捷指令
- instruction：coding preferences and standards
- 使用Agent時，Agent會自主決定使用哪些工具來執行特定任務。如果您想在聊天提示中明確提及某個工具，可以使用 # 提及。輸入 `#` 後面接著工具名稱和可選參數
- VS Code supports three types of tools
  1. built-in tools
  2. Model Context Protocol (MCP) tools
  3. extension tools.
- [How AI works in VS Code -- 擴充Tools](https://code.visualstudio.com/docs/copilot/core-concepts#_tools)
  1. MCP
  2. Skills
  3. Hooks
- 查看可用工具：chat view→選擇Agent模式→設定工具小圖示  
  可自訂 Agent 所使用的工具
- [Customization](https://code.visualstudio.com/docs/copilot/customization/overview#_customization-options)  
  自訂 Chat 五個方法，可單獨使用與混合使用  
  節省 Token  
  讓工作最佳化
- 設定 Chat：開啟 VSCode 設定→`@feature:chat` 
- 常用指令
  `#web`：Fetch 網頁以獲取最新資訊
- **上下文限制。** 當對話時間過長時，模型將無法存取先前的上下文。如果回應品質開始下降，請開始新的會話，並為目前任務提供新的上下文。

## Copilot-CLI

## 重要章節

- [模型適用性比較](https://docs.github.com/en/copilot/reference/ai-models/model-comparison)
- [Customization](https://code.visualstudio.com/docs/copilot/customization/overview#_customization-options)
- [Best practices for using GitHub Copilot - GitHub Docs](https://docs.github.com/en/copilot/get-started/best-practices)
- [GitHub Copilot in VS Code cheat sheet](https://code.visualstudio.com/docs/copilot/reference/copilot-vscode-features)

## 其他資源

- [GitHub Copilot 總文件 - GitHub Docs](https://docs.github.com/en/copilot)
- [github/awesome-copilot: Community-contributed instructions, prompts, and configurations to help you make the most of GitHub Copilot.](https://github.com/github/awesome-copilot)
- [GitHub AI（產品頁） · AI built into every step of your workflow](https://github.com/features/ai)
- [doggy8088/github-copilot-configs: Will 保哥整理的最佳 GitHub Copilot 設定](https://github.com/doggy8088/github-copilot-configs)
- [How to write better prompts for GitHub Copilot](https://github.blog/developer-skills/github/how-to-write-better-prompts-for-github-copilot/)
- [Using GitHub Copilot in your IDE: Tips, tricks, and best practices](https://github.blog/developer-skills/github/how-to-use-github-copilot-in-your-ide-tips-tricks-and-best-practices/)
- [Generating Synthetic Datasets with GitHub Copilot](https://www.youtube.com/watch?v=4kwX1CUT43Q)
- [How to Use GitHub Copilot to Become a Happier and More Productive Developer](https://www.freecodecamp.org/news/developer-productivity-with-github-copilot)
- [GitHub Copilot Fundamentals Part 1 of 2 - Training | Microsoft Learn](https://learn.microsoft.com/en-us/training/paths/copilot/)
- [copilot-sdk: Multi-platform SDK for integrating GitHub Copilot Agent into apps and services](https://github.com/github/copilot-sdk?fbclid=IwY2xjawPYietleHRuA2FlbQIxMQBicmlkETFlYTgzdU4wbFJRM0hsVmcyc3J0YwZhcHBfaWQQMjIyMDM5MTc4ODIwMDg5MgABHrRj7gj6NYv5sIEGrEQuqLUHkztg9PKNDGog_mEVWXGemvB5twaAqTJUwML3_aem_4psBS293JQEzm8IAAhSHGQ)
- [完全掌握 GitHub Copilot 提示工程的核心原理 - YouTube](https://www.youtube.com/watch?v=Mb5iThLRgfE)
- [在終端機中利用 GitHub Copilot CLI 驅動代理工作流程 - YouTube](https://www.youtube.com/watch?v=0XCosNsVb8I)
- [Github Copilot 聊天視窗指令整理-黑暗執行緒](https://blog.darkthread.net/blog/copilot-chat-cheatsheet/)
- [Copilot coding agent now supports AGENTS.md custom instructions - GitHub Changelog](https://github.blog/changelog/2025-08-28-copilot-coding-agent-now-supports-agents-md-custom-instructions/)
- [What I've Learned About GitHub Copilot Agent Mode - DEV Community](https://dev.to/anchildress1/what-ive-learned-about-github-copilot-agent-mode-4co2)
- [Copilot－instructions search results](https://github.com/search?q=copilot-instructions.md&type=repositories)
- [課程研究－掌握 AI 驅動的終端機：GitHub Copilot CLI 深度實戰 - 多奇教育訓練](https://learn.duotify.com/courses/copilot-cli)
- [課程研究－GitHub Copilot AI 程式碼編輯工具應用實務班](https://www.tiandiren.tw/product/c1456)

## 最佳實作

- 設定提示檔案、設定指示
- 程式碼生成方式：自動程式碼建議、註解方式
- 聊天範圍選定：CTRL+I
- edit：多個檔案產生程式碼
- 使用註解方式給予程式碼建議（等於inline chat）
  ghost text、inline chat、chat pannel
- 盡量使用內建的prompt而不要重新創造，如fix、doc、explain
- 善用chat上下文（互動式回饋）
- 要給予copilot回饋（它才會正確學習），按贊
- 規格要清楚
- 英文的精準度還是高上許多，所以在寫規格的時候還是以英文為主會比較好。
- 寫扣之前先把該做的事情拆解成簡單的步驟，那麼 copilot 可以大幅度的減少你查詢語法的時間，以及語法的錯誤。只要規格會寫對，那麼你不會語法也沒關係。
- 語法交給 copilot ，但架構還是要交給人
