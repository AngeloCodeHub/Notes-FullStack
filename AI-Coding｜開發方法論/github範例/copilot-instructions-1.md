# Copilot 指南

## 建構、測試與檢查
- **開發伺服器**：`pnpm dev`（Next.js 16 App Router，預設 http://localhost:3000）。
- **正式建置**：`pnpm build` 產生 `.next`，搭配 `pnpm start` 驗證生產模式。
- **靜態匯出**：`pnpm build && pnpm exec next export`，輸出目錄可在 `next.config.ts` 調整。
- **ESLint**：`pnpm lint`；針對單檔可執行 `pnpm lint -- --file src/app/page.tsx`，自動修正使用 `pnpm lint:fix`。
- **單檔測試**：目前尚未導入測試框架；若未來加入 Vitest/Playwright，請於此節補充完整與單檔指令。

## 高層架構
- **App Router**：`src/app` 為 RSC 入口，`layout.tsx` 載入 Geist 字體與 `@/styles/shadcn.css` 全域樣式並設定 `lang="zh-tw"`；互動畫面需在檔案首行加入 `"use client"`，維持外層為 Server Component。
- **UI 元件層次**：`src/components/ui` 存放 shadcn/ui 風格元件（CVA + `cn()` 處理 variants），共用/頁面專用元件放在 `src/components`。
- **樣式系統**：Tailwind CSS 4 + `tw-animate-css`，整體設計令於 `src/styles/shadcn.css`（語義化 CSS 變數、`@theme inline`、dark variant）；`heroui.css` 供 HeroUI 額外樣式。
- **工具與別名**：`src/lib/utils.ts` 提供 `cn()`；`tsconfig.json` 宣告 `@/* -> ./src/*`，請避免多層相對路徑。
- **Workspace 範圍**：單一 pnpm workspace；`Ref-Code/`、`_example/` 為學習資料，`dist/`、`out/`、`.next/` 為產出，皆在 `tsconfig` exclude。

## 關鍵慣例
- **語言與註解**：Markdown、程式註解採繁體中文；程式碼命名維持英文。
- **樣式合併**：所有 `className` 經 `cn()`（內部為 `clsx` + `tailwind-merge`）處理，並以 CVA pattern 管理 variants/sizes。
- **Server vs Client**：預設 RSC；需要 hooks 或瀏覽器 API 時才加入 `"use client"`，並盡量侷限在葉節點。
- **表單策略**：使用 `react-hook-form` + `zod` schema 進行驗證，錯誤訊息沿用 shadcn 元件確保一致 UX。
- **字體與主題**：`next/font` 載入 Geist Sans/Mono，搭配 `shadcn.css` 的 CSS 變數與 `.dark` variant 切換主題。
- **依賴管理**：統一使用 `pnpm add` / `pnpm add -D`，提交前確認 `pnpm-lock.yaml` 同步。

---
若需要協助設定與本專案相關的 MCP Server（例如 Playwright 端對端測試或 Supabase 服務），請告訴我以便協助配置。
