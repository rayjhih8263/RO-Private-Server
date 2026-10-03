# 03｜建立 RO Client

狀態：依子步驟建立；舊紀錄未完成

03-1 準備完整資源與乾淨 EXE → 03-2 配置資源/連線 → 03-3 WARP 補丁 → 03-4 登入、建角、進地圖測試。完成條件是確實登入自己的 Server 並進入地圖。

| 元件 | 舊紀錄位置/結果 |
| --- | --- |
| 客戶端資料夾 | C:\RO-Server\RO-Client-20220406 |
| Ragexe | 2022-04-06_Ragexe_1648707856.exe；可執行，但缺資源/補丁 |
| FroggoClient.exe | 反覆 0xc0000005 秒退；後續改用乾淨 Ragexe |
| ROEnglishRE | C:\RO-Server\ROenglishRE |
| Generator | Tools 中執行 ClientGenerator；選 Pre-Renewal / 2022-04-06 |
| 生成資源 | Tools\Client 中的 data / SystemEN |
| WARP | 最後指示下載到 C:\RO-Server\WARP，沒有完成回報 |
| Translation Session | 舊紀錄最後提出 2019-06_Translation.yml；尚未成功套用驗證 |

- 先核對實際客戶端 EXE 日期與 Server PACKETVER。原紀錄最後是 20220406。

- 原包已有 ROTP20220406.grf、official_data.grf、data / System / SystemEN / Setup.exe 等；應以實際檔案清單核對，不能把只有 Git LFS 指標的 1 KB GRF 當作完整資源。

- data\clientinfo.xml 第一組 connection 在舊紀錄改為：

```text
<address>127.0.0.1</address>
<port>6900</port>
```

這只適用 Client 與 Server 在同一台電腦。換機或區網另行設定，不沿用外部測試伺服器項目。

- Setup.exe 的 DirectX9 在舊機造成 FroggoClient 秒退；DirectX7 曾改善啟動，但重解壓後仍失敗。這不是已確認通用解法，先核對當前環境。

- ROEnglishRE Generator 曾生成 Pre-Renewal / 2022-04-06 的資料；三轉目標需要重新核對生成模式，不能直接把舊模式資源當作三轉完成品。

- 複製生成資源時，DATA.ini 被覆蓋成 server.grf / data.grf，但根目錄沒有 server.grf。舊紀錄恢復原包順序：

```text
[Data]
0=whatever
1=you
2=need
3=ROTP20220406.grf
4=official_data.grf
5=data.grf
6=data_1.grf
7=data_2.grf
```

這是舊包的歷史值，不是任意客戶端可直接使用的模板；需確認存在的 GRF 與 EXE 補丁。

- SystemEN 改成 System 的試驗失敗；不能列為正式做法。使用 Translation Session 前核對它指定的讀取路徑，以及目前 System / SystemEN / System_BACKUP 的實際狀態。

- 最後停點是準備 WARP。當時提供來源 https://github.com/WarboundRO/WARP；規劃載入乾淨 Ragexe、載入 Translation Session、Recommended、處理必要補丁。這條路尚未完成，按鈕和 Session 相容性需在真正續做時以工具與官方文件核對。

- 完成補丁後才可測試登入、建角、進地圖、顯示道具與技能；舊分享紀錄沒有這些成功證據。
接續工作需要目前 Client 根目錄與 WARP 資料夾狀態；不能依舊紀錄猜測現在已到哪一步。不要讓更新器直接覆蓋唯一一份正在配對的資源；先留可還原副本。

## 新對話開場文字

```text
這是 RO 私服步驟 03：建立 RO Client。請使用步驟 01 確定的 EXE/PACKETVER，依序準備完整資源、設定連線、套補丁，再測試登入、建角與進地圖。舊紀錄使用 2022-04-06_Ragexe_1648707856.exe，準備 WARP 但未完成；請先確認目前檔案。Server 設定見步驟 02，錯誤記到 07。每次只做一個步驟。
```
