# 07｜錯誤排除紀錄

狀態：查詢用；不列為重建主步驟

| 問題 | 結果與整理結論 |
| --- | --- |
| git clon 拼字 | 改為 git clone 後成功；不需重做 |
| HeidiSQL SQL 1064 | 查詢前端有 ragnarokragnarok；改 MariaDB SOURCE 匯入後成功；不改官方 SQL |
| char_athena.conf 找不到 max_base_level | 沒有該欄位；未完成 99/70 驗證；不新增猜測欄位 |
| GRF 下載失敗 | Git LFS 配額/取檔失敗；1 KB GRF 為指標；該下載路徑未完成，後來改 Froggo 包 |
| FroggoClient 秒退 | 0xc0000005 / 0x004dad80；VC++、DirectX 與重解壓未形成穩定解法；未解決 |
| DirectX7 | 曾讓 Client 啟動，但後來仍失敗；不能記為確定修正 |
| 更新後 Lua 錯誤 | 曾出現 Hotkey/PrivateAirplane 等錯誤；更新造成混用資源是當時推測，未全面驗證 |
| Vanilla Ragexe 缺 LUB | PetEvolutionCln_true.lub、Achievement_list.lub、PrivateAirplane_True.lub；尚需相容資源與補丁 |
| 只改 System 大小寫 | 後來撤回；不能當作修正方法 |
| SystemEN → System | 實測仍報缺檔；從成功流程移除 |
| DATA.ini 被 Generator 覆蓋 | 根目錄無 server.grf；當時恢復原包順序；新版包需重新核對 |
| Nemo 載入按鈕沒反應 | 原先操作順序錯；先「瀏覽」選 EXE 再「載入程式」；之後另有版本識別問題 |
| Nemo 無法完整辨識 EXE | 紀錄顯示支援警告；曾反覆推測版本原因，沒有修好；最後改規劃 WARP |
| Session 2022-09 | 舊紀錄後來修正為規劃 2019-06；兩者在該分享對話都無成功套用證據 |
| 下載網址失效 | 歷史來源可能失效；不把搜尋到網址視為下載成功 |

排錯紀錄格式：日期 → 操作前狀態 → 完整錯誤 → 試過的方法 → 實際結果 → 最後有效修正 → 待確認項目。完整歷史文字保留在先前的 HTML 手冊；原紀錄中的確定語氣不代表本次重新驗證。

## 新對話開場文字

```text
這個對話專門保留 RO 排錯紀錄。每個問題請記錄完整錯誤、實際嘗試與結果，只有實測成功才列為修正。舊紀錄的 SQL 匯入問題已用 SOURCE 解決；FroggoClient 秒退與 Client 資源/補丁仍未完成。請避免重複給已失敗方案，每次只帶我做一個步驟。
```
