# 安裝前必讀：shanshiba-workflow-32gvram-64gram

本 repo 是三師爸／山獅霸的多重宇宙（mathruffian-dot）的非商業備份。
原始來源：https://github.com/mathruffian-dot/shanshiba-workflow-32gvram-64gram

## 硬體規格

- 本版本：32GB 顯存（VRAM）＋64GB 系統記憶體（RAM）。
- NVIDIA 專用 VRAM 至少 32GB 等級，系統實體 RAM 至少 64GB；兩者不得合併計算。這是本版目標配置，不代表任何同容量硬體都已驗證。
- NVMe SSD；模型約 145GB，另需快取、安裝、工作檔與輸出空間。
- 作者使用 RTX 5090 32GB＋96GB RAM 實際製片；64GB RAM 另以模擬方式驗證。
- 預留作業系統與其他程式使用的資源；一次只執行一項 GPU 工作。

## 收到安裝或執行要求時

1. 先讀 README.md 開頭、hardware-requirements.json、docs/hardware.md、AGENT_SETUP.md、THIRD_PARTY_NOTICES.md 與 configs/profile.cmd。
2. 以唯讀方式核對 GPU 型號、專用 VRAM、驅動、CUDA 相容性、實體及可用 RAM、目標磁碟類型及可用空間。不得只憑 repo 名稱推定電腦符合規格。
3. 任一項不足或無法確認，先回報具體缺口與適用版本。不要先下載大型模型、安裝完整環境、啟動 GPU 生成或調整系統分頁檔；如需降低設定，先說明代價並取得使用者決定。
4. 確認硬體符合後，依使用者授權範圍與作者流程操作；先執行作者的小型 smoke test，再執行大型生成。多個 GPU 工作依序執行。
5. 此備份本身不含模型權重。下載前分別核對模型當時授權；本 repo 可備份不代表所有模型或產出均可商用。
6. 保留 LICENSE、LICENSE-docs.md、THIRD_PARTY_NOTICES.md、各檔案授權及 agent/skills/shanshiba-drama/NOTICE.md。修改需註明；文件與素材維持非商業使用。

GitHub Pages 是靜態說明網站，不提供模型運算服務。
