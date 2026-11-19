# my-cluade-code-doc-template
記錄 AI 規格驅動開發（SDD）的文件結構。

## 目的

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

