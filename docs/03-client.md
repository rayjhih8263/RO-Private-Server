# 03 建立 RO Client

## 1. 取得 Client

來源：[ROClientFullCN](https://github.com/rAthenaCN/ROClientFullCN)

目前使用的登入器：

```text
2021-11-03_Ragexe_patched.exe
```

## 2. 補齊 GRF

Git LFS 下載遇到問題後，你改用手動個別下載完整 GRF，再複製到 Client 資料夾。

保留這些實際檔案，不要只備份登入器 EXE。

## 3. 設定本機連線

Client 和 Server 在同一台電腦時，開啟 Client 資料夾內的：

```text
data\clientinfo.xml
```

連線位址與 Port：

```xml
<address>127.0.0.1</address>
<port>6900</port>
```

儲存檔案。

## 4. 核對 Server 封包設定

這個登入器的日期是 2021-11-03，日期值為 `20211103`。Server 曾改為 `20220406`；目前是否已改回，還需要核對，不能直接當作已完成。

## 完成確認

後續對話已交叉核對（2026-10-01，台灣時間）：

- 08:24：使用 ROClientFullCN，ZIP 內有 `2021-11-03_Ragexe_patched.exe`。
- 09:17～09:23：手動下載 `luafiles.grf`、`map.grf` 後複製覆蓋；後續也確認其他 GRF 容量。
- 10:51：已有成功進入遊戲的回覆。

**Client 已有成功進入遊戲的紀錄。**

目前資料夾路徑及完整資源合併細節仍在核對。先前測試過的 2022-04-06 EXE 與 WARP 流程，不列為目前這個登入器的建立步驟。

[回首頁](../README.md)
