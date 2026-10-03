# 05｜建立 OpenKore 與連線測試

狀態：一般 Client 成功後進行

舊分享對話沒有完成 OpenKore 安裝、連線或掛機設定。這個分類先保留獨立工作順序，不能把「想使用」記成「已相容」。

- 先讓一般 Client 成功登入自己的 Server、建角與進地圖。

- 確認 OpenKore 版本、Server 的 PACKETVER、實際 EXE 與補丁；核對這組封包是否支援。

- 核對登入模式、伺服器 IP / port、serverType、封包表與加密需求；尚無足夠資料指定值。

- 使用自建伺服器的測試帳號，先驗證登入與選角，再驗證進地圖、移動、打怪與拾取。

- 最後設定補血、技能、倉庫、購買補品、隊伍與練功地圖；每個功能確認成功才記錄。
不提供未驗證的 serverType 或 recvpackets 檔案，避免重複試錯。實際架設時再依你的 Server / Client 組合查官方資料。

## 新對話開場文字

```text
這個對話專門設定 OpenKore，對象是我自己的 RO 私服。我要搭配三轉與伊甸園。舊 rAthena 為 PACKETVER 20220406，但一般 Client 仍在補丁階段；OpenKore 尚未安裝或驗證。請先確認一般 Client 已登入，再核對目前版本的連線與封包支援，每次只帶我做一個步驟，不要猜 serverType。
```
