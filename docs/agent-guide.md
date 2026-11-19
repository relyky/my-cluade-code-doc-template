# Agent Guide：文件結構與變更流程

本檔由 `CLAUDE.md` 指引在變更前閱讀。內容是 AI 與人類共用的文件結構、**變更模式**與撰寫規則。

## 文件結構

```text
docs/
  agent-guide.md             # 本檔：文件結構與變更流程
  glossary.md                # 術語表：專案用語、縮寫與中英對照
  roadmap.md                 # 總進程與未來方向
  reference/                 # 外部資源參照
  operations/                # 部署、正式環境資料庫操作、重啟服務等影響線上的操作
  architecture/
    overview.md              # 系統全貌與技術棧（現況）
    adr/                     # ADR 架構決策（為何選 A 而不選 B）
      001-<decision1>.md
      002-<decision2>.md
  changes/                   # 進行中的變更
    <進行中階段的變更文件>
  changes-archive/           # 完成後歸檔
    stage001-<subject>/      # 新需求模式：目錄名串接主題，內用固定檔名
      proposal.md            # user story
      tech-stack.md          # （選用）技術選型，有多種選項時才需要此檔說明。
      spec.md                # （選用）以 BDD 格式撰寫，需求難以用一段話清晰描述角色責任時才需要此檔說明。
      design.md
      tasks.md
    stage002/                # 議題／後記模式：目錄只用編號，檔名帶主題
      <subject1>-plan.md
      <subject1>-tasks.md
      <subject2>-record.md
src/
CLAUDE.md
```

核心分工：`overview.md` 只寫「現在用 A」並連結 ADR；ADR 寫「為什麼選 A 而不選 B」。理由只存在一處。

## 變更模式有三種

文件量隨變更規模伸縮。動手前先在 `changes/` 建立對應文件。

| **變更模式** | 適用情境 | 文件 |
|---|---|---|
| 新需求 | 跨多個模組、引入新依賴或技術選型、改動資料模型或對外介面 | `proposal.md`、`tech-stack.md`（選用）、`spec.md`（選用）、`design.md`、`tasks.md` |
| 議題 | 單一模組內的問題、小需求、測試後返工 | `<subject>-plan.md`、`<subject>-tasks.md` |
| 後記 | 事後記錄，小到不需要計畫 | `<subject>-record.md`（改了什麼、為什麼、影響範圍） |

- `tech-stack.md` 只記錄本次新增或變動的項目，不複製 overview 的總表。
- 執行中範圍擴大，就停下來告知並升級到上一級模式，補齊文件後再繼續。
- `changes/` 同一時間只放一個活動階段；同階段多個議題一律加 `<subject>-` 前綴。
- 每完成一項任務就更新 `tasks.md` 的勾選狀態。

## 撰寫規則

**ADR**：檔名 `NNN-<decision>.md`，頂部標註 `已通過` / `已取代`。已通過的 ADR 不修改；要推翻就新增一份並標註「取代 ADR-NNN」，舊的狀態改為 `已取代`（唯一允許的修改）。

**同步**：變更技術選型時，同時更新 `overview.md` 並檢查 ADR 是否要新增。實作與文件不一致時，先更新文件並說明原因。

**reference**：每條外部資源附一行用途說明；只寫取得權限的流程，不寫帳密或金鑰。

**glossary**：收錄專案專屬的用語、縮寫與領域詞彙，不收錄通用技術名詞。
- 每條一行定義；有對應的程式碼識別字、資料表或英文名稱時一併標註，避免文件與程式碼用不同詞指同一件事。
- 格式：`**術語**（English / 別名）：一句話定義。→ 相關文件連結`
- 其他文件首次出現專案專屬術語時，連結到 glossary，不重新定義。
- 變更中新增或改名了術語，在同一個提交更新 glossary；術語被淘汰時標註「已停用」並指向取代詞，不直接刪除。

## 歸檔

歸檔前確認：任務已完成或標註延後、ADR 與 overview 已同步、必要時已更新 roadmap。

| 模式 | 歸檔位置 |
|---|---|
| 新需求 | `changes-archive/stageNNN-<subject>/`，固定檔名 |
| 議題、後記 | `changes-archive/stageNNN/`，主題前綴檔名 |

編號接續上一個 stage。同階段若同時有新需求與議題，分開歸檔，不混放。
