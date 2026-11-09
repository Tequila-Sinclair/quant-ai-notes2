# CLAUDE.md - Quant & AI Lab Notes 專案開發規範

## 1. 專案目的與架構
本專案是一個輕量級的個人知識庫與筆記網站，採用 HTML / Tailwind CSS (透過 CDN) 建立，專門用來展示量化交易與 AI 開發筆記。
目標是讓 AI 能夠在不破壞整體設計風格的情況下，快速新增、修改或擴充頁面與文章。

## 2. 網頁整體風格與 UI 規範
- **設計風格**：簡約現代風（Modern Dark / Clean Tech），類似 Vercel 或 Tailwind 官方文件的精緻感。
- **色彩搭配**：
  - 背景色：深色模式 (`bg-slate-955` / `bg-gray-900`) 或極簡白灰 (`bg-slate-50`)。
  - 主色調：科技藍/靛色 (`text-indigo-400`, `bg-indigo-600`) 作為亮點。
- **字體與排版**：使用無襯線字體，行高充足 (`leading-relaxed`)，程式碼區塊必須有語法高亮與精美的深色背景。

## 3. 頁面結構與檔案命名
- `index.html`：首頁，包含專案介紹、文章列表（Card 形式）與分類導覽。
- `posts/` 資料夾：存放所有詳細文章的 HTML 頁面。
  - 命名規則：以英文短橫線命名，例如 `smart-money-concepts-intro.html`、`vibe-coding-workflow.html`。
- `assets/` 資料夾：存放圖片、自訂 CSS 或共用 JS。

## 4. 新增文章與內容時要遵守的格式
每當新增一篇教學或筆記時，必須包含以下結構：
1. **導覽列 (Navbar)**：保持全站一致，包含 Logo 與返回首頁按鈕。
2. **文章標題區**：清晰的大標題 (`<h1>`)、發布日期與標籤 (`<span class="px-2 py-1 bg-indigo-500/10 text-indigo-400 text-xs rounded-full">`)。
3. **內容本文**：善用 `<h2>`、`<h3>`、條列式清單 (`<ul>`) 與程式碼區塊 (`<pre><code>`)。
4. **頁尾 (Footer)**：包含版權宣告與返回頂部按鈕。

## 5. AI 修改與新增規則
- 當使用者要求「新增一篇關於 X 的文章」時，AI 必須：
  1. 在 `posts/` 建立對應的 HTML 檔案，並完全沿用現有的 Tailwind CSS 樣式與排版框架。
  2. 同時更新 `index.html` 的文章列表，將新文章以 Card 形式補在最前面，確保使用者點擊得到。
- 嚴禁擅自更改全站的核心設計系統（如主色調、字體大小規範），除非使用者明確要求。