# Paper 一下

研究生論文閱讀筆記網站。目前收錄兩篇閱讀筆記，新增內容規則位於根目錄 AGENTS.md。

## 預覽

在專案根目錄執行 `python -m http.server 8000`，開啟 http://localhost:8000/ 。

## 發布

將本資料夾的檔案上傳到公開 GitHub Repository，讓 index.html 與 AGENTS.md 位於儲存庫根目錄，再設定 GitHub Pages。公開網址與 Repository 連結待發布後補入。

## 新增第二篇的測試

已依 AGENTS.md 新增 Denoising Diffusion Probabilistic Models（NeurIPS 2020），slug 為 `ddpm`。整理稿位於 `notes/ddpm.md`，網頁位於 `papers/ddpm.html`。首頁保留第一篇並新增第二篇卡片；兩篇共用既有版型與 style.css。實際檢查方式與結果見 CHECKS.md。

## 資料與 AI 協助

第一篇依使用者提供的 Generative Quantitative Ultrasound Imaging.pdf 全文整理。ChatGPT 協助筆記、來源頁碼核對與網站開發，個人心得標為待補。PDF 第 1 頁標示 2026 年投稿日期，正式出版資訊與公開來源連結待確認。

第二篇依使用者提供的 DDPM 全文（arXiv:2006.11239v2，含附錄共 25 頁）整理。ChatGPT 協助技術摘要、數據與頁碼核對、網頁新增；作者結論與 AI 解讀分開標明。未提供的資訊標為待確認，個人心得標為待補，沒有重新訓練或重現論文結果。

原始 PDF 留在整理流程，本專案僅包含整理稿與來源連結。尚未完成 GitHub 公開部署，公開網址與 Repository 連結待補。網站每次新增內容都依根目錄規則檢查。
