<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" class="logo" width="120"/>

# Vim 與 Neovim（nvim）比較與異同

## 共同點

- **操作方式和基本概念相同**：兩者都採用 modal editing（模式化編輯），使用者需要切換普通模式、插入模式及命令模式進行文本操作。
- **高度可自訂**：兩者都可以藉由設定檔與插件進行各種高度自訂，並支援類似的基礎語法（Vimscript）。
- **大多數 Vim 插件可直接沿用**：Neovim 盡量與 Vim 向下相容，大部分 Vim 插件亦可直接運作於 Neovim[^1_1][^1_2][^1_3]。


## 不同點

### 架構與開發模式

- **社群驅動**：Vim 主要由創作者與少數維護者開發，Neovim 是由社群驅動，開發活躍，維護與功能改進迅速[^1_4][^1_1]。
- **易於維護與擴充**：Neovim 將核心功能模組化，使維護和新增功能更容易，這也帶來了更快的開發迭代[^1_3][^1_1]。


### 性能與擴展性

| 項目 | Vim | Neovim |
| :-- | :-- | :-- |
| 任務處理 | 單執行緒（非同步支援有限） | 支援非同步、可在背景執行任務，不阻塞介面[^1_5][^1_3] |
| 外部插件語言 | 主要使用 Vimscript | 原生支援 Lua 和多語言擴展，效率更高[^1_5][^1_2][^1_4] |
| 執行效率 | 傳統設計，對大型專案有瓶頸 | 多執行緒處理、更快反應，適合大型專案[^1_4] |

### 插件與生態

- **插件架構**：Neovim 插件可異步運行，不會拖慢主編輯器；Vim 插件多為同步，容易造成軟體卡頓[^1_3][^1_5]。
- **現代化插件生態**：越來越多的新型強大插件優先支援 Neovim，有些已僅以 Lua 撰寫，無法在 Vim 上運行[^1_2][^1_3]。


### 配置與檔案結構

- **配置檔位置**：
Vim 使用 `~/.vimrc`，Neovim 採用 XDG 標準，如 `~/.config/nvim/init.vim` 或 `~/.config/nvim/init.lua`[^1_6]。
- **資料夾架構**：Neovim 在配置與插件管理上更有彈性，且符合現代 Linux 應用標準[^1_6]。


### 其他功能

- **內建終端機**：Neovim 內建終端模組，能在編輯器內直接運行 shell；Vim 需另安裝插件[^1_3]。
- **GUI 支援**：Neovim 的設計利於開發多樣化 GUI 前端（如 Oni、Goneovim），較易集成於其他應用或嵌入系統[^1_3][^1_7]。
- **語言伺服器協定（LSP）**：Neovim 原生支援 LSP，自動補全、語法檢查、碼跳轉效能遠勝 Vim[^1_5][^1_2][^1_3]。


### 穩定度與成熟度

- **穩定性**：Vim 更著重穩定與可靠性，Neovim 則偏重新功能與開發活躍[^1_8]。
- **預設配置**：Neovim 預設體驗佳，Vim 須更多自行設定[^1_9]。


## 適用情境建議

- **Vim**：若你需在伺服器、低規環境，且重視穩定與兼容傳統 UNIX 工具，Vim 是好選擇。
- **Neovim**：若你要求高度現代化、效能、插件生態活躍、希望享有最新語言工具與開發環境，Neovim 將會更好[^1_3][^1_2][^1_4]。

總結來說，**Neovim 基於 Vim 再發展，針對現代開發需求大量優化效能、可擴展性與現代功能**，而 Vim 則保有傳統穩定性、適用於各種老舊或特殊環境。選擇何者取決於你的需求與使用場景。

<div style="text-align: center">⁂</div>

[^1_1]: https://www.baeldung.com/linux/vim-vs-neovim

[^1_2]: https://www.siddharta.me/vim-vs-neovim.html

[^1_3]: https://stack.tools/blog/neovim-vs-vim

[^1_4]: https://sysadminxpert.com/difference-between-vim-and-neovim/

[^1_5]: https://www.namehero.com/blog/neovim-vs-vim-whats-the-difference/

[^1_6]: https://www.ubuntumint.com/vim-vs-neovim/

[^1_7]: https://vi.stackexchange.com/questions/25783/what-are-the-major-differences-between-vim-and-neovim

[^1_8]: https://www.youtube.com/watch?v=qQvFC0wRiRE

[^1_9]: https://www.reddit.com/r/vim/comments/hwl9k1/whats_the_difference_between_vim_and_neovim_and/

[^1_10]: https://vi.stackexchange.com/questions/34/what-is-neovim-and-how-is-it-different-from-vim

[^1_11]: https://dev.to/kurealnum/why-you-should-ditch-vscode-and-use-neovim-instead-436o

[^1_12]: https://www.youtube.com/shorts/AsoaYO_TDKw

[^1_13]: https://www.youtube.com/watch?v=pnOQ_45-W_E

[^1_14]: http://neovim.io/doc/user/vim_diff.html

