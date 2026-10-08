# 03 建立 RO Client

繁體中文 | [English](en/03-client.md)

## 1. 取得 Client

來源：[ROClientFullCN](https://github.com/rAthenaCN/ROClientFullCN)

目前使用的登入器：

```text
2021-11-03_Ragexe_patched.exe
```

## 2. 補齊 GRF

手動個別下載完整 GRF，再複製到 Client 資料夾。確認檔案已完整下載，而非 Git LFS 指標文字檔。

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

這個登入器的日期是 2021-11-03，Server 的 `PACKETVER` 應設定為 `20211103`。設定後依 [02 編譯 Server](02-server.md#4-編譯-server) 建置，再重新啟動 Server。

## 完成確認

1. Login、Char、Map 三個 Server 都保持執行。
2. 執行 `2021-11-03_Ragexe_patched.exe`，確認能進入登入畫面。
3. 使用已建立的遊戲帳號登入，確認能進入角色選擇與遊戲地圖。

Client 資料夾路徑依實際安裝位置為準。完整資源合併與遊戲帳號建立的詳細步驟尚待補充。

[回首頁](../README.md)


## 教學內容授權

本倉庫中由作者享有著作權的原創教學文字及自製圖解，採 [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.zh-hant) 授權。

歡迎非商業用途的分享與修改，請標示作者 **rayjhih8263**、[原始倉庫](https://github.com/rayjhih8263/RO-Private-Server-Setup-Guide)及授權連結，並註明修改內容；修改後公開分享時，須使用相同授權。未經權利人另行許可，不得將上述內容用於商業目的，包括打包販售、付費下載，或收錄於付費教材。

第三方軟體、遊戲素材、商標、截圖及圖片不屬於本授權範圍，仍依各權利人的授權規定使用。標註來源或交流用途，不等於取得授權。

[完整授權說明](../LICENSE.md)
