# 備份紀錄

## 來源與範圍

原分享者：三師爸；原作者正式署名為 **[山獅霸的多重宇宙（mathruffian-dot）](https://github.com/mathruffian-dot)**。
原始專案：[shanshiba-workflow-32gvram-64gram](https://github.com/mathruffian-dot/shanshiba-workflow-32gvram-64gram)。本備份由 [t92016](https://github.com/t92016) 維護，非原作者官方發布。

**本 repo 適用配置：32GB 顯存（VRAM）＋64GB 系統記憶體（RAM）。顯存與系統記憶體是兩項不同規格，不能互相加總替代。**

| 安裝前核對 | 要求與限制 |
|---|---|
| NVIDIA GPU 專用顯存 | 32GB 等級或以上；仍需核對 GPU 架構、驅動與 CUDA 相容性 |
| 系統實體記憶體 | 64GB 或以上；實體容量不等於當下可用量 |
| 儲存空間 | NVMe SSD；模型約 145GB，另須工作檔、快取與輸出空間，145GB 並非足夠的總空間 |
| 平台 | 作者本機流程以 Windows 11／NVIDIA 為基礎；其他平台需另行確認 |
| 驗證範圍 | 作者使用 RTX 5090 32GB＋96GB RAM 實際製片；64GB RAM 另以模擬方式驗證。 |
| 資源限制 | 預留作業系統與其他程式使用的資源；一次只執行一項 GPU 工作。 |

安裝前先讀 [AGENTS.md](AGENTS.md)、[硬體規範資料](hardware-requirements.json)、[作者硬體說明](docs/hardware.md) 和 [第三方授權](THIRD_PARTY_NOTICES.md)。硬體不足或未確認時，先回報差距，不要直接下載大型模型或執行完整安裝。

[公開說明網站（GitHub Pages）](https://t92016.github.io/shanshiba-workflow-32gvram-64gram/)。Pages 只提供靜態說明，不會在網站上執行 AI 模型。

**授權與修改**：原程式主要依 [MIT](LICENSE)，`tools/flashvsr_cli.py` 依 GPL-3.0-or-later；原文件與素材依 [CC BY-NC 4.0](LICENSE-docs.md)（[授權連結](https://creativecommons.org/licenses/by-nc/4.0/deed.zh-hant)）。本備份僅供非商業保存及閱讀，保留原作者與第三方聲明。新增本段說明、AGENTS.md、hardware-requirements.json、BACKUP.md 與 Pages 首頁，並在 AGENT_SETUP.md 加入安裝前提示；原工作流程程式與模型設定未修改。新增說明文件與首頁依 CC BY-NC 4.0，新增 JSON 依 MIT。

備份來源 commit：[`ae7d7d844aa82368875966c1289037d58bc8f8f1`](https://github.com/mathruffian-dot/shanshiba-workflow-32gvram-64gram/commit/ae7d7d844aa82368875966c1289037d58bc8f8f1)。這是 2026-10-21 的備份快照，不會自動同步上游。

---

