# 山獅霸 AI 影片工作流｜本機完整版 32GB VRAM＋64GB RAM：agent 安裝前必讀

原分享者：三師爸。依作者要求署名：[山獅霸的多重宇宙（https://github.com/mathruffian-dot）](https://github.com/mathruffian-dot)。

原始專案：[mathruffian-dot/shanshiba-workflow-32gvram-64gram](https://github.com/mathruffian-dot/shanshiba-workflow-32gvram-64gram)。本份為 t92016 個人非商業公開備份，非官方發布。

授權：程式主要 [MIT](https://github.com/t92016/shanshiba-workflow-32gvram-64gram/blob/main/LICENSE)，tools/flashvsr_cli.py 為 GPL-3.0-or-later；文件、技能文字與素材依 [CC BY-NC 4.0](https://github.com/t92016/shanshiba-workflow-32gvram-64gram/blob/main/LICENSE-docs.md)（[授權連結](https://creativecommons.org/licenses/by-nc/4.0/deed.zh-hant)），須姓名標示且不得用於商業目的。保留 [THIRD_PARTY_NOTICES.md](https://github.com/t92016/shanshiba-workflow-32gvram-64gram/blob/main/THIRD_PARTY_NOTICES.md)、各檔案授權及 POUND0423 改編技能聲明。本 repo 不包含模型權重；模型與服務各有條款。

修改標示：2026-10-25 合併原作者更新至 `8b4c50a1a5e302c981914f7459d0c66e8f99e6a3`，保留上游與先前備份歷史。備份維護者更新 README 開頭提示、INSTALLATION.md、AGENTS.md、BACKUP.md、WORKFLOW-COMPARISON.md、JSON 規範與 Pages；撤去舊 AGENT_SETUP.md 額外提示，使作者原手冊回到本次上游版本。原工作流程、程式、技能本文、範本、作者手冊及原授權檔均保持與該來源 commit 相同（README 另加備份導讀）。新增說明及首頁採 CC BY-NC 4.0，新增 JSON 採 MIT。這次沒有安裝、下載模型或生成影片。

來源 commit：[8b4c50a1a5e302c981914f7459d0c66e8f99e6a3](https://github.com/mathruffian-dot/shanshiba-workflow-32gvram-64gram/commit/8b4c50a1a5e302c981914f7459d0c66e8f99e6a3)。查核／同步日期：2026-10-25；不會自動同步上游，未來仍需查當時版本。

## 讀取順序與目的

先讀 README 開頭、INSTALLATION.md、WORKFLOW-COMPARISON.md、installation-manifest.json，再讀作者 AGENT_SETUP.md、cloud/README.md、docs/hardware.md、THIRD_PARTY_NOTICES.md 與 configs/profile.cmd。閱讀／備份不代表使用者要求安裝、充值、下載模型或啟動 VM。

## 按實際硬體分流

2026-10-25 此次電腦偵測到 GT 710 2GB VRAM、實體 RAM 約 15.9GiB（16GB 等級）。不適用本機完整版（32GB VRAM＋64GB RAM），也不適用兩個 16GB VRAM 版本；本機配音／首幀的作者建議 8GB／12GB 也未達。候選為全雲端或經使用者選擇的付費 API，先核對授權、預算及環境。

每次安裝先唯讀重新檢查 GPU 型號與專用 VRAM、CUDA 相容性、實體／可用 RAM、目標磁碟可用空間及網路。不要把這份單次快照套到其他電腦，不要只看顯卡容量就假定架構相容；RAM 與 VRAM 不可加總替代。

硬體不足／未知時先回報差距，不下載大型模型、不擴大分頁檔或增加 GPU 並行硬撐。Colab 控制端不需要裝整套本機模型，且要區分 H3-only 與全雲端。start、batch 都可能開付費 VM；授權機房、Google 登入與預算尚未確認時不要執行。登入由使用者本人完成，不經手授權碼。

## 流程與付費服務

先明確選 H3、本機／Colab 或 Seedance API，不把分享案例當成目前價格。2.0 Mini 與 2.5 不同；此版本提供 tools/sd25_shot.py（2.5），未確認 2.0 Mini 專用工具。API 的 check 只按固定費率估算；submit 需要使用者明確選用並確認現價、額度及上傳素材權利。不得把 API token 或私人素材 push 到公開 repo。

最新 H3 角色參考音流程已取代先 TTS 固定音軌的預設；遵循當次來源腳本與範本。face_refine 等新增大型選配不是必要安裝。只有環境與授權均符合後先做最小 smoke／單鏡驗證，再完整短片；檢查角色、聲音、繁體字幕、時序與檔案。沒有實際測跑就不能宣稱驗證成功。

雲端結果確認下載、驗收與備份後檢查 session 狀態及關機；不要靠閒置回收當作已關閉。Pages 僅為靜態文件，不提供影片生成。保留所有 LICENSE／NOTICE 與原作者修改紀錄，模型使用仍需另外遵守各自條款。
