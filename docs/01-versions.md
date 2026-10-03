# 01｜確認 Server、Client 與工具版本

狀態：開始前先確認

先確定整套版本與玩法，再開始安裝。這頁同時保存舊進度供核對；已用過的版本不等於現在推薦或已確認的最終組合。

| 先確認的項目 | 目前可確定 / 尚待確認 |
| --- | --- |
| 玩法 | 你已指定三轉＋伊甸園＋OpenKore；等級上限尚未指定 |
| Server | 使用 rAthena；舊 commit 未記錄，需由現有原始碼確認 |
| Server 模式 | 舊版 Pre-Renewal；新目標要檢視 Renewal 模式與三轉設定 |
| Client EXE | 舊紀錄為 2022-04-06_Ragexe_1648707856.exe，補丁未完成 |
| PACKETVER | 舊紀錄最後為 20220406；最終須和選用 EXE 及封包支援一致 |
| Client 資源 | 確認 GRF、data、System/SystemEN 與 Translation Session 的相容組合 |
| 資料庫 | 舊 MariaDB 11.8.9；新安裝/還原版本尚待確認 |
| 編譯工具 | 舊 Visual Studio Community 2026 / C++ 桌面開發 / Release x64 |
| 補丁工具 | 舊紀錄準備使用 WARP；版本與可用 Session 待確認 |
| OpenKore | 尚未選定版本及驗證封包支援 |
| 連線方式 | 先同一台電腦本機測試；換電腦/區網時另核對 IP |

01 的完成條件：記錄 rAthena commit、模式、Client EXE、PACKETVER、資料庫、補丁工具與 OpenKore 相容性決策。未確認的欄位保留「待確認」，再進入 02。

## 舊紀錄進度與文件使用方式

整理日期：2026-10-03。來源：你提供的「RO私服架設指南」分享對話；另加入本對話的新目標。

這份文件整理的是舊紀錄，不是對目前電腦的即時檢查。原始截圖沒有匯入，截圖內的設定值只能依文字回報判斷。下載網址、軟體版本和 WARP 操作未重新驗證，保留作歷史參考。

| 項目 | 舊紀錄的結果 |
| --- | --- |
| Windows | Windows 11；後來確認先在同一台筆電架設及遊玩 |
| Visual Studio | 使用 Community 與 C++ 桌面開發；紀錄顯示選用 2026 |
| MariaDB | 11.8.9；服務 MariaDB；TCP 3306 |
| rAthena | C:\RO-Server\rathena；Release / x64；曾建置 15 成功、0 失敗 |
| 資料庫 | ragnarok、ragnarok_log；當時確認 56 / 10 個資料表 |
| 伺服器啟動 | login / char / map 已成功；6900 / 6121 / 5121 |
| 模式 | Pre-Renewal 已載入 db/pre-re；99/70 尚待實際驗證 |
| 封包版本 | 最後已重新編譯成 PACKETVER 20220406 |
| 倍率 | Base / Job 20 倍；一般掉落 5 倍；一般卡片 3 倍；Boss/MVP 保留 1 倍 |
| GM | 紀錄回報已建立；group_id 99 |
| Client | 2022-04-06_Ragexe_1648707856.exe；可啟動但有資源/補丁問題 |
| 最後停點 | 準備下載及設定 WARP；沒有成功登入遊戲的完成證據 |
| 現在的新目標 | 三轉＋伊甸園＋可用 OpenKore；尚未在本次工作中實作 |

重建順序：01 確認版本 → 02 建立 Server → 03 建立 Client → 04 三轉與伊甸園 → 05 OpenKore → 06 備份。遇到錯誤查 07。三轉目標不要直接沿用舊的 PRERE 定義。

使用方式：從首頁 README 的步驟索引點選 01～07；每頁末尾的開場文字可複製到同名 ChatGPT 對話。這份 GitHub 手冊保留整理後的流程與結論，完整歷史紀錄另保存在先前的 HTML 手冊。

## 新對話開場文字

```text
這是 RO 私服步驟 01：確認版本。我要三轉＋伊甸園＋OpenKore。請先確認 rAthena commit、Renewal 模式、Client EXE 日期、PACKETVER、資源與補丁工具、MariaDB、OpenKore 支援，整理成一張版本表。舊紀錄為 Windows 11、rAthena、MariaDB 11.8.9、Pre-Renewal、PACKETVER 20220406，Client 補丁未完成。不要把舊版直接當新目標的最終版本。每次只帶我做一個步驟。
```
