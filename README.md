# my-cluade-code-doc-template
記錄 AI 規格驅動開發（SDD）的文件結構。

## 目的

本 repo 只提供文件範本，不含程式碼。`CLAUDE.md` 與 `docs/` 是範本內容，供其他專案複製套用；本 README 只說明範本本身，不屬於範本。

## 目錄結構

```
CLAUDE.md           # 針對 Claude Opus 5.5 撰寫，只記錄模型無法從程式碼推得的專案資訊。
docs/
  agent-guide.md    # AI agent 行動指引。
```

## 理論基礎

參考相關理論，不表示非得用上。
- SDD：Spec-Driven Development，規格驅動開發。先寫規格，再依規格實作與驗證。
- DDD：Domain-Driven Design，領域驅動設計。以業務領域為核心的軟體開發方法論。
- ADR：Architecture Decision Record，架構決策記錄。以短文件記錄架構決策的背景、考慮過的選項與選擇理由。
- User Story：使用者故事。軟體工程與敏捷開發中，從「使用者角度」簡短描述功能與價值的需求表達方式。樣板：「As a (role), I want (function) so that (business value)」。
- TDD：Test-Driven Development，測試驅動開發。開發循環為「紅燈 → 綠燈 → 重構」。
- BDD：Behavior-Driven Development，行為驅動開發。以協作為核心的敏捷軟體開發方法，規格以「Given-When-Then」格式撰寫。
- CRC cards：Class-Responsibility-Collaborator cards，類別-職責-合作者卡片。用於物件導向分析與設計（OOAD）的視覺化與腦力激盪工具。團隊為系統中每個重要類別建立一張實體索引卡或數位白板卡片，在寫程式前快速梳理物件分工與互動。

## 典範文件檔名與用途

vibe coding 過程常用來控制開發的文件檔名參考清冊。「本範本」欄打 ✔ 表示本範本採用，空白僅供參考。

**Agent 指令**

| 檔名 | 用途 | 本範本 | 常見來源 |
|---|---|---|---|
| `CLAUDE.md` | 專案層級 AI 指令，每次對話載入 | ✔ | Claude Code |
| `CLAUDE.local.md` | 個人 AI 指令，不進版控 | | Claude Code |
| `AGENTS.md` | 跨工具通用的 AI 指令 | | AGENTS.md 慣例 |
| `docs/agent-guide.md` | 文件結構與變更流程 | ✔ | |

**常駐文件（`docs/`）**

| 檔名 | 用途 | 本範本 | 常見來源 |
|---|---|---|---|
| `glossary.md` | 術語表：專案用語、縮寫與中英對照 | ✔ | DDD |
| `roadmap.md` | 總進程與未來方向 | ✔ | |
| `process.md` | 開發流程：分支、審查、發布 | | |
| `conventions.md` | 命名與程式風格規範，code review 的依據 | | |
| `constitution.md` | 專案不可違反的原則 | | spec-kit |
| `progress.md` | 進度與目前狀態，跨對話延續 | | Cline Memory Bank |
| `reference/` | 外部資源參照 | ✔ | |
| `operations/` | 部署、正式環境操作等影響線上的指令 | ✔ | |
| `architecture/overview.md` | 系統全貌與技術棧（現況） | ✔ | |
| `architecture/adr/` | 架構決策記錄 | ✔ | ADR |

**變更文件（`docs/changes/`）**

| 檔名 | 用途 | 本範本 | 常見來源 |
|---|---|---|---|
| `changes/` | 進行中的變更，一次只放一個階段 | ✔ | |
| `proposal.md` | 需求提案（user story） | ✔ | OpenSpec |
| `requirements.md` | 需求，與 `proposal.md` 同角色 | | Kiro |
| `tech-stack.md` | 本次技術選型 | ✔ | |
| `spec.md` | 規格，本範本以 BDD 格式撰寫 | ✔ | spec-kit |
| `design.md` | 設計 | ✔ | Kiro、OpenSpec |
| `plan.md` | 實作計畫；本範本只以 `<subject>-plan.md` 形式用於議題 | ✔ | spec-kit |
| `tasks.md` | 任務清單與勾選狀態；議題用 `<subject>-tasks.md` | ✔ | Kiro、spec-kit、OpenSpec |
| `<subject>-record.md` | 後記：改了什麼、為什麼、影響範圍 | ✔ | |
| `changes-archive/` | 完成後歸檔 | ✔ | |
