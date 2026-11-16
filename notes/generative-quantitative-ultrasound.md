# Generative Quantitative Ultrasound Imaging from B-Mode Ultrasound: Added Diagnostic Value in Characterizing Breast Lesions

作者：Nasrin Sheibani-Asl、Laurentius O. Osapoetra、Gregory J. Czarnota、Ali Sadeghi-Naini

年份：2026（稿件提交年，正式出版資訊待確認）

標籤：超音波、QUS、cGAN、乳房病灶

資料性質：AI 輔助閱讀筆記，依使用者提供全文整理。

## 研究問題與動機

作者關心的是，在推論時無法取得原始射頻（RF）資料的情況下，能否從 B-mode 超音波影像估計定量超音波（QUS）參數圖，並保留乳房病灶良惡性分類所需的資訊。研究也比較合成 QUS 與直接使用 B-mode 的分類表現。依據為 PDF 第 1–3 頁，摘要與 Introduction。

白話整理：用有 RF 與 B-mode 配對的資料訓練生成模型，部署時輸入 B-mode 與病灶遮罩，產生 QUS 圖供後續分析。推論輸入仍包含遮罩，訓練參考圖則由 RF 建立。依據為 PDF 第 4、10 頁。

## 研究資料與方法

- 院內資料來自 192 位病人，共 697 組配對 RF／B-mode 影像，包含 95 位良性及 97 位惡性病灶患者。以病人為單位分成訓練 125 位、驗證 29 位、測試 38 位。依據為第 II-A 節，PDF 第 3 頁。
- 生成器輸入為 B-mode 與病灶遮罩兩個通道，輸出為 ASD、AAC、MBF、SS、SI 五種 QUS 參數圖。此篇的輸出參數為光譜與散射體相關參數。依據為第 II-C、II-D 節，PDF 第 4 頁。
- 比較三種 cGAN 生成器：基本 U-Net、雙解碼器 U-Net，以及 RF 特徵引導的雙解碼器 U-Net。雙解碼器分別產生 ASD／AAC 與 MBF／SS／SI。依據為第 II-D 節，PDF 第 4 頁。
- 第三種模型利用另行訓練、凍結的 B-mode-to-RF 模型，從 B-mode 抽取多尺度特徵，注入 QUS 生成器。三種架構使用相同 PatchGAN 判別器與訓練策略。依據為 PDF 第 4–5 頁。
- 以 Inception-v3 評估良惡性分類，其第一個卷積層改為接收五個 QUS 通道。外部資料使用 BUSI 與 Dataset B，兩者只有 B-mode 與病灶標記，缺少對應 RF。依據為第 II-A、II-E 節及 Discussion，PDF 第 3、5、10 頁。

## 主要結果

以下數值均為作者報告的測試結果。Table 2 與 Table 3 的分類結果以 2,000 次 bootstrap 的平均值與標準差呈現。

| 資料與比較 | 測試 AUC（平均 ± 標準差） | 來源 |
| --- | --- | --- |
| 院內：原始 QUS → 合成 QUS | 0.94 ± 0.02 → 0.94 ± 0.02 | Table 2，PDF 第 9 頁 |
| BUSI：B-mode → 合成 QUS | 0.93 ± 0.03 → 0.99 ± 0.002 | Table 3，PDF 第 9 頁 |
| Dataset B：B-mode → 合成 QUS | 0.79 ± 0.09 → 0.94 ± 0.05 | Table 3，PDF 第 9 頁 |

院內測試中，原始與合成 QUS 的 AUC 相同，但準確率分別為 90.0 ± 3.0% 與 88.0 ± 3.0%，特異度為 91.0 ± 3.0% 與 85.0 ± 4.0%。這些差異應與 AUC 一起閱讀。依據為 Table 2，PDF 第 9 頁。

重建方面，作者指出 RF 特徵引導模型在大多數參數上表現較佳。以 MBF 為例，MAE 為 3.1 ± 1.1%、SSIM 為 0.98 ± 0.01。SI 的部分誤差指標則與雙解碼器相近。依據為 Table 1 與 Results，PDF 第 7 頁。

## 研究限制

- 作者明列的限制：生成器訓練資料來自單一超音波系統，需要更多中心、設備與掃描協定的資料驗證。依據為 Discussion，PDF 第 10 頁。
- 外部 BUSI 與 Dataset B 沒有配對 RF，無法直接用 RF-derived QUS 檢驗外部合成圖的重建準確性。外部結果主要評估下游分類效用。依據為 Discussion，PDF 第 10 頁。
- 推論流程需要 B-mode 與病灶遮罩。應在理解使用情境時一併考量遮罩取得方式。前句為方法原文，後句為 AI 整理時提出的閱讀提醒。依據為 PDF 第 4、10 頁。

## 我的閱讀心得與待確認問題

待補。使用者尚未提供個人閱讀心得或問題。本頁的技術摘要與來源核對由 AI 協助整理。

## 論文來源

完整標題：Generative Quantitative Ultrasound Imaging from B-Mode Ultrasound: Added Diagnostic Value in Characterizing Breast Lesions

作者：Nasrin Sheibani-Asl、Laurentius O. Osapoetra、Gregory J. Czarnota、Ali Sadeghi-Naini

整理依據：使用者提供的 Generative Quantitative Ultrasound Imaging.pdf，共 11 頁。PDF 第 1 頁標示稿件於 2026 年 7 月 27 日提交；正式出版年份、期刊卷期與本篇 DOI 待確認。

公開來源連結待補。此頁保留章節、表格及 PDF 頁碼供回查，公開網站僅呈現整理稿。

本頁由 ChatGPT 根據上傳全文協助擷取、摘要與表格核對。整理日期為 2026 年 11 月 16 日。

