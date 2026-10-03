# 03 建立 RO Client

繁體中文 | [English](en/03-client.md)

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


## 教學內容授權

本倉庫中由作者享有著作權的原創教學文字及自製圖解，採 [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.zh-hant) 授權。

歡迎非商業用途的分享與修改，請標示作者 **rayjhih8263**、[原始倉庫](https://github.com/rayjhih8263/RO-Private-Server)及授權連結，並註明修改內容；修改後公開分享時，須使用相同授權。未經權利人另行許可，不得將上述內容用於商業目的，包括打包販售、付費下載，或收錄於付費教材。

第三方軟體、遊戲素材、商標、截圖及圖片不屬於本授權範圍，仍依各權利人的授權規定使用。標註來源或交流用途，不等於取得授權。

[完整授權說明](../LICENSE.md)
