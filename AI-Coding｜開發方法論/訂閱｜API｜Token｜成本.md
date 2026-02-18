
## FAQ

- 訂閱制 session與messages 與 API Token差別?  
  A：  
  session就是一個連續的對話，會感知Context  
  message則是一次對問答會對話，不限於session
- 模型廠商本身訂閱制的 System Prompt有沒有算在內?
- 訂閱 Claude pro但計費週期還沒到齊.升級至max，計費週期會怎麼計算?  
  A：週期不重新計算，而是收取差額
- 使用OpenRouter api與直接呼叫原廠API會比較划算嗎?

## 記事

- 可控：Token、Context、Tools、MCP、Skills、Prompt
- 控制 API還是得學習
- Claude Usage limits control how much you can interact with Claude over a specific time period.（包括不同的Chat）
- Claude length limits就是 context window（single chat），為200K tokens
- 不同的任務交給不同的 **工具** 與 **模型**
- [GitHub Copilot 官方Plan比較](https://docs.github.com/en/copilot/get-started/plans-for-github-copilot)
- [GitHub Copilot 訂閱頁面](https://github.com/settings/billing/licensing)
- 使用 API可提供批量處理，可靈活降低 token 成本，但須更高技術使用

## References

- [Understanding usage and length limits | Claude Help Center](https://support.claude.com/en/articles/11647753-understanding-usage-and-length-limits)
- [Using Claude Code with your Pro or Max plan | Claude Help Center](https://support.claude.com/en/articles/11145838-using-claude-code-with-your-pro-or-max-plan)
- [Usage limit best practices | Claude Help Center](https://support.claude.com/en/articles/9797557-usage-limit-best-practices)
- [AI 的 CP 值？](https://www.facebook.com/1403951219/posts/10242969827847365)  
  有多少事情是 agent 現在做得到，工具做不到如CLI、PowerShell、IDE.有助於降低 Token
- [AI Cost Comparison — Monthly Subscription vs. LLM Model API Pricing](https://aiproductivitysecrets.com/guides/comparison/)
- [API vs Subscription? : r/ClaudeAI](https://www.reddit.com/r/ClaudeAI/comments/1bbk5en/api_vs_subscription/)
- [LLM subscriptions vs. APIs value for money](https://www.asad.pw/llm-subscriptions-vs-apis-value-for-money/)
- [Claude Pricing Explained: Subscription Plans & API Costs | IntuitionLabs](https://intuitionlabs.ai/articles/claude-pricing-plans-api-costs)
