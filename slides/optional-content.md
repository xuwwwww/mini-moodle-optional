# Optional 簡報文字

## 1 方法

標題：Optional AI agent 方法

使用者決定需求、審閱成果。Codex agent 查來源、列問題、寫規格和 UML。

課程說明與五張 Story → Agent 草稿與待決問題 → 人決定五項範圍與歧義 → Agent 修訂 R1～R5 與 UML → 人審閱

共同範圍：登入、建課、課碼加入、公告、留言

## 2 實際跑出的成果

標題：兩次人工審閱

| 11 月 3 日 | 11 月 6 日 |
| --- | --- |
| 「五項照建議」 | 「我看過UML以及需求了 沒問題」 |
| 決定共同範圍、帳號、課碼、公告修改、教師權限 | 接受 R1～R5 需求規格與兩張 UML |

Agent 產出：需求草稿、正式規格、類別圖、課碼加入循序圖、執行紀錄

AI 錯誤：執行紀錄把整理稿稱為「完整文字輸出」。核對後更正，逐字對話另行處理。

## 3 和另外兩組比較

標題：三種方法怎麼決定需求

| Waterfall + AI | Agile + AI | Optional |
| --- | --- | --- |
| 三人問卷 → 決定表 → SRS | 討論 → Story／AC → Sprint | Agent 列歧義 → 人決定 → 規格／UML |
| RA、QA、SD 審查 PR，SRS v1.0 待簽核 | PO 與組員安排、測試及驗收 | 使用者兩次審閱 |
| AI 漏掉教師查看課碼的位置 | AI 原型顯示 UTC，後改台灣時間 | AI 誤稱已保存完整對話 |

時間：Waterfall 有逐項估計，Agile 尚待補，Optional 目前只量到補正 3 分 52 秒。

資料：Waterfall 決定表、SRS、AI log 和 PR #1～2，Agile 組報告及 AI log，Optional 本地規格與審閱紀錄。詳細連結見 `report/optional-section.md`。
