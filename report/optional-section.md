# Optional AI agent 方法

本組由使用者負責需求決定與審閱，Codex agent 負責規劃、核對來源、整理需求與繪製 UML。題目沿用 Mini Moodle。這次需求分析選用五項功能：登入、建立課程、課碼加入、課程公告和留言板。

## 方法與實際執行

Agent 先對照課程說明、團隊討論及 Jira 的 MM-1、MM-2、MM-9、MM-3、MM-4，寫出需求草稿並列出範圍、帳號來源、課碼格式、公告修改和教師權限五項決定。使用者於 11 月 3 日回覆「五項照建議」。Agent 隨後完成 R1～R5 的需求規格，以及類別圖和學生以課碼加入課程的循序圖。使用者於 11 月 6 日回覆「我看過UML以及需求了 沒問題」。

每輪由 agent 安排查證與修訂。人的決定記在 `review-01.md` 和 `review-02.md`，agent 計畫及產出記在 `runs/`。`dialogue-excerpts.md` 只擷取已確認的決定與之後的工作，保留原話，沒有改寫成新的問答。

## 審查發現

Agent 在執行紀錄中把整理後的文件寫成「完整文字輸出」，但當時沒有保存逐字對話。11 月 6 日核對時發現這個錯誤，改正執行紀錄，並將原句與更正寫入 `evidence.md`。使用者於 11 月 8 日確認含此例的報告與簡報。

## 三種方法對照

| 方法 | 需求如何產生 | AI 做了什麼 | 人在哪裡決定 | 本次可查的成果 |
| --- | --- | --- | --- | --- |
| Waterfall + AI | 三名組員填問卷，RA 統計並寫需求決定表，再寫 SRS | Claude 起草問卷、決定表及部分 SRS | RA 處理分歧，QA、SD 審查 PR，SRS v1.0 另需三人簽核 | 決定表、SRS 0.1 草稿、已合併 PR #1 和 #2 |
| Agile + AI | 討論功能後寫 User Story 和驗收條件，放入 Jira 與 Sprint | ChatGPT、Codex 協助起草 Story、架構和程式 | PO 與組員安排、測試及驗收 | Jira Story、Sprint 規劃、Agile 報告和 AI 使用紀錄 |
| Optional AI agent 方法 | Agent 對照同一產品的五項功能，先列歧義，再依人的決定寫規格和 UML | Codex 規劃查證、草擬 R1～R5、繪製兩張 UML 並核對來源 | 使用者先決定五項問題，再審閱規格與 UML | `requirements.md`、`uml/system.md`、兩次審閱與執行紀錄 |

三組審查時發現的問題也不同。Waterfall 的 AI 草稿漏了教師在哪裡看到課碼，RA 補成 FR-3.10。Agile 原型把 SQLite 的 UTC 時間直接顯示，雙角色測試後改成台灣時間。Optional 的錯誤是把摘要稱為完整對話，核對紀錄時發現並更正。

Waterfall 的 AI log 有逐項估計節省時間。Agile 的 log 仍寫「節省時間：待補」。Optional 的前兩輪沒有計時，11 月 6 日核對與補正實測 3 分 52 秒。三組目前沒有同一套計時方式，這份報告先列各自的原始紀錄。

## 目前結論

Waterfall 先形成問卷、決定表，再寫 SRS。Agile 以 Story、Sprint 和 PO 驗收安排工作。Optional 讓 agent 先整理問題與規格，人在兩個關卡決定範圍和接受內容。本次 Optional 已完成需求規格與 UML 的人工審閱。

## 資料來源

- Optional：`requirements.md`、`uml/system.md`、`review-01.md`、`review-02.md`、`evidence.md`、`ai-usage-log.md`
- Waterfall：[需求決定表](https://github.com/mini-moodle-team/mini-moodle-waterfall/blob/main/docs/elicitation-notes/decision-table.md)、[SRS](https://github.com/mini-moodle-team/mini-moodle-waterfall/blob/main/docs/SRS.md)、[AI log](https://github.com/mini-moodle-team/mini-moodle-waterfall/blob/main/ai-log/ai-usage-log.md)、[PR #1](https://github.com/mini-moodle-team/mini-moodle-waterfall/pull/1)、[PR #2](https://github.com/mini-moodle-team/mini-moodle-waterfall/pull/2)，2026-11-07 讀取，main 為 `718c52a`
- Agile：[組內報告](https://docs.google.com/document/d/14W_qP29W5IL-ErVO-190tiXsAs65BA5NthSxm8NNClY/edit)、[AI 使用紀錄](https://docs.google.com/document/d/1JoyqKFxSaQmwbQu4PTqCaLCPSeeif8-lTp-UIGWvDMY/edit)、[簡報](https://www.canva.com/design/DAHY1lB0_SU/YVPQwBtRq-GxUyffu8fIxw/edit)，2026-11-07 讀取
