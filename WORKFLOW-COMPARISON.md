# 雲端、本機與付費 API：如何選擇

## 先看本次電腦檢查

2026-10-25 在此次操作的電腦以 nvidia-smi 與 Windows 記憶體 API 唯讀檢查：NVIDIA GeForce GT 710，專用顯存 2GB；實體 RAM 約 15.9GiB（16GB 等級）。本次沒有進行模型安裝、效能跑分或影片生成。

這台電腦不符合本機完整版的 32GB VRAM＋64GB RAM 配置，也不符合另外兩份 16GB VRAM 版本。不要為了嘗試而直接下載約 145GB 的整套本機模型；較合理的候選是全雲端生成、這台做 agent 對話與檔案管理，但要先解決雲端授權、額度、磁碟及網路條件。低解析度剪接／播放仍需先做小型測試，不能保證本機順暢。

這是單次電腦快照，使用者換電腦、換顯卡或再次安裝時，agent 必須重新偵測，不能把它當成使用者所有電腦的永久規格。只發布與工作流判斷相關的 GPU／RAM 摘要，不含電腦名稱、序號或登入資訊。

## 三條路線

- 雲端 Colab＋MiniMax H3：H3 在雲端 GPU 上執行；本機跑不動配音、生圖時，選全雲端模式。需要 Google 帳戶、Colab CLI、可用運算單元、合適 VM 與網路；免費或付費額度、顯卡供應及價格以當時帳戶為準。
- 本機完整 MiniMax H3：目標配置 NVIDIA 32GB 專用 VRAM＋64GB 以上實體 RAM，NVMe SSD，模型約 145GB，另需環境、工作檔、快取與輸出空間。作者主要使用 RTX 5090 32GB＋96GB RAM，64GB RAM 另以模擬驗證。本次這台 GT 710／16GB 電腦不適用。
- Kie.ai＋Seedance：另一個付費雲端 API 路線，不是「Colab 版本」也不是本機 H3。新版來源含 tools/sd25_shot.py，使用模型識別 bytedance/seedance-2-5，配合相同分鏡 spec 可做對照。只在使用者明確選用、確認當下價格與上傳素材權利後送件。

## 使用者提供的分享案例

使用者於 2026-10-25 轉貼三師爸的分享：同一支颱風假短劇，比較 Colab＋H3 與 Kie.ai＋Seedance 2.5，並描述從劇本、角色資產、首幀到成片都在 agent 對話中操作。案例稱 Colab 用了 1.43 單元、Google AI Pro 每月附 200 單元；Seedance 2.5 約每秒 10「元」，90 秒花了 1,070「元」。原文未明示「元」的幣別，此處不自行補成台幣或人民幣。

以上是使用者提供的案例記錄，不是本次重測數據、目前服務報價或成本保證。生成時長、素材準備、失敗重試、重拍、配音、上傳下載及不同模型版本都會影響成本，兩組數字不能當成完全相同計費邊界的性能測試。

分享另提到「動作鏡頭用 Seedance 2.0 Mini，其餘用 H3」。這是不同的模型／混合用法，不能把 2.0 Mini 與 2.5 當成同一版本；本次確認的 repo 工具是 Seedance 2.5，未確認內附 2.0 Mini 專用工具。要照做前另查當時 API 的模型、參數、可用性與條款，不沿用其他版本的價格。

## 「不開 ComfyUI」的意思

使用者不必手動開 ComfyUI 網頁或剪輯軟體，agent 可透過腳本處理；H3 路線背後仍會由腳本部署或呼叫 ComfyUI、ffmpeg 等工具，並非完全沒有 ComfyUI 依賴。GitHub Pages 只呈現這份說明，不會提供生成算力。

## 授權與服務限制

repo 可非商業備份，不能推導成所有模型都可以商用或在任何地區執行。作者 cloud/README.md 與 THIRD_PARTY_NOTICES.md 提醒 H3 授權排除美國、歐盟、英國與南韓，作者過去分到的 Colab G4 位於美國或歐盟。真正執行前重查權利方當時授權與本次機房；沒有釐清授權範圍就不要啟動或下載模型。另有 Qwen／Breeze 等非商業限制、AI 生成標示及素材／真人聲音權利要求。

Kie.ai、Google Colab 的服務條款、API 點數與付費設定另行確認；不要在公開 repo 放 KIE_API_KEY、Google 授權碼、模型下載 token 或私人角色素材。本次僅同步備份，不代表已接受或開通這些服務。

## 來源與文件授權

原分享者：三師爸。依作者要求署名：[山獅霸的多重宇宙（https://github.com/mathruffian-dot）](https://github.com/mathruffian-dot)。

原始專案：[mathruffian-dot/shanshiba-workflow-32gvram-64gram](https://github.com/mathruffian-dot/shanshiba-workflow-32gvram-64gram)。本份為 t92016 個人非商業公開備份，非官方發布。

授權：程式主要 [MIT](https://github.com/t92016/shanshiba-workflow-32gvram-64gram/blob/main/LICENSE)，tools/flashvsr_cli.py 為 GPL-3.0-or-later；文件、技能文字與素材依 [CC BY-NC 4.0](https://github.com/t92016/shanshiba-workflow-32gvram-64gram/blob/main/LICENSE-docs.md)（[授權連結](https://creativecommons.org/licenses/by-nc/4.0/deed.zh-hant)），須姓名標示且不得用於商業目的。保留 [THIRD_PARTY_NOTICES.md](https://github.com/t92016/shanshiba-workflow-32gvram-64gram/blob/main/THIRD_PARTY_NOTICES.md)、各檔案授權及 POUND0423 改編技能聲明。本 repo 不包含模型權重；模型與服務各有條款。

修改標示：2026-10-25 合併原作者更新至 `8b4c50a1a5e302c981914f7459d0c66e8f99e6a3`，保留上游與先前備份歷史。備份維護者更新 README 開頭提示、INSTALLATION.md、AGENTS.md、BACKUP.md、WORKFLOW-COMPARISON.md、JSON 規範與 Pages；撤去舊 AGENT_SETUP.md 額外提示，使作者原手冊回到本次上游版本。原工作流程、程式、技能本文、範本、作者手冊及原授權檔均保持與該來源 commit 相同（README 另加備份導讀）。新增說明及首頁採 CC BY-NC 4.0，新增 JSON 採 MIT。這次沒有安裝、下載模型或生成影片。

來源 commit：[8b4c50a1a5e302c981914f7459d0c66e8f99e6a3](https://github.com/mathruffian-dot/shanshiba-workflow-32gvram-64gram/commit/8b4c50a1a5e302c981914f7459d0c66e8f99e6a3)。查核／同步日期：2026-10-25；不會自動同步上游，未來仍需查當時版本。
