# 06｜備份與換電腦重建

狀態：完成後保存；修改前也先備份

這頁是依整理結果補上的重建清單，不代表舊紀錄已備份，也不代表本次已從你的 Windows 電腦取得任何資料。

| 要保存 | 目的 |
| --- | --- |
| rAthena 原始碼與修改 | 保存 src/config、src/custom、conf、db、npc 及相關修改；記錄 git commit 與 git diff |
| SQL 備份 | 匯出 ragnarok、ragnarok_log；角色與帳號不在 exe 裡 |
| Client 完整資料夾 | EXE、GRF、data、System/SystemEN、DATA.ini、clientinfo.xml；不可只存登入器 |
| 乾淨 EXE / 原始 ZIP | 補丁失敗時恢復到相同起點 |
| WARP Session / 補丁選項 | 重現生成相同 Client 的方式 |
| OpenKore 資料夾 | 完成後保存版本、設定、封包表與插件 |
| 環境紀錄 | Windows、MariaDB、Visual Studio、PACKETVER、模式與成功測試 |

- 舊電腦先停止遊戲寫入並匯出兩個資料庫；確認匯出結果可讀，再複製 Server、Client 與設定。

- 記錄原始碼 commit 與修改，保存可正常啟動的版本，不以重新下載 master 代替舊版。

- 新電腦安裝相容的 MariaDB、編譯工具及執行環境；建立空的目標資料庫與專用帳號。

- 選擇「還原 SQL 備份」或「全新匯入 main.sql / logs.sql」。已有角色資料要走還原，不重複執行新建流程。

- 還原 Server 檔案，核對 DB 帳密、路徑、IP、PACKETVER 與模式，再編譯並啟動三個 Server。

- 還原 Client，核對本機/區網位址並測試登入、角色與地圖。

- 三轉、伊甸園與 OpenKore 分別測試，將各項結果寫回 01；成功前保留舊機副本。
若新電腦只用來玩，Server 仍在舊電腦，則只需配置 Client、網路與 Server 公告位址，不需在每台電腦重裝資料庫。外網連線不在此舊紀錄的完成範圍。

## 新對話開場文字

```text
這個對話專門處理 RO 備份、換電腦重建或新增 Client 電腦。請先確認我是搬整個 Server 還是只在新電腦玩。保留 rAthena 版本與修改、兩個 SQL 資料庫、完整 Client 與補丁紀錄。已有角色資料要還原，不從 main.sql 重建覆蓋。每次只帶我做一個步驟，完成後記錄成功檢查結果。
```
