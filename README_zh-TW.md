# ThoughtTrace Pro 

[![Version](https://img.shields.io/badge/version-2.8.0-blue.svg)]()
[![License](https://img.shields.io/badge/license-MIT-green.svg)]()

> *Read this in [English](README.md)*

**ThoughtTrace Pro** 是一個基於瀏覽器的寫作行為取證框架，專為區分「人類原創認知」與「AI 輔助搬運」而設計。

與傳統基於 NLP 的 AI 檢測工具（只看最終文本）不同，ThoughtTrace 專注於分析寫作過程中的**行為生物特徵（Behavioral Biometrics）**。

# 解決痛點
現有的 AI 檢測工具在面對「人肉抄寫 AI」或「深度洗稿」時往往失效，且容易產生偽陽性（False Positives），誤殺原創作者。

# 核心技術：行為取證
ThoughtTrace 透過監控擊鍵動力學（Keystroke Dynamics）、上下文切換和輸入熵，生成完整的**會話審計軌跡（Audit Trail）**。我們不審查文字內容，我們審查文字是「如何」被產生的。

# 核心演算法
*   **專屬基準線校準 (Baseline Calibration)：** 在寫作開始前建立個人的擊鍵指紋（CV值），消除不同硬體設備帶來的誤差。
*   **同步覆蓋率 (Sync Coverage)：** 動態比對 DOM 文本長度與實際有效按鍵數，精準攔截外部剪貼簿注入（大段貼上）。
*   **認知熵分析 (Cognitive Entropy)：** 分析按鍵延遲的變異係數 (CV)。真實的人類思考會產生非線性的節奏抖動；而看著 AI 抄寫則會呈現機械化、勻速的輸入特徵。
*   **焦點流失追蹤 (Focus Loss Tracking)：** 監控視窗切換與失焦事件，有效防範對著外部 AI 畫面進行「洗稿」的行為。

##  快速開始
本專案為零依賴的 Local-first 原型（Vanilla JS）。
1. Clone 本專案。
2. 在任何現代瀏覽器中直接開啟 `index.html`。
3. 完成初始校準（Calibration）即可解鎖安全編輯器。

##  隱私與安全
**100% 本地端運算。** ThoughtTrace Pro 僅依賴瀏覽器的 `localStorage` 進行狀態管理。用戶的擊鍵特徵與文本內容**絕對不會**被傳送至雲端伺服器。

##  審計報告
系統可一鍵導出 **PDF 行為審計報告**。報告內含行為轉向時間軸（例如先出現 `[大規模貼上]`，隨後出現 `[人類原創修復]`），為教育工作者提供完整的行為上下文，而非單一死板的評分。
