# 03 建立 RO Client

繁體中文 | [English](en/03-client.md)

本章以 Client 與 Server 在同一台 Windows 電腦上測試為前提。

## 1. 用 Git 下載 Client

來源：[ROClientFullCN](https://github.com/rAthenaCN/ROClientFullCN)

開啟 Git Bash，輸入：

```bash
cd /c/RO-Server
git clone https://github.com/rAthenaCN/ROClientFullCN.git RO-Client
```

本教學下載位置：

```text
C:\RO-Server\RO-Client
```

確認資料夾內有：

```text
2021-11-03_Ragexe_patched.exe
Setup_Plus.exe
DATA.INI
data.grf
data\
System\
```

若 Git LFS 顯示下載失敗，先檢查 Client 檔案是否已下載到資料夾，再依下一步補齊大型 GRF。不要把只完成部分資源的資料夾當作可直接啟動的完整 Client。

## 2. 手動補齊 5 個大型 GRF

需要補齊的檔案：

| 順序 | 檔名 | 來源頁面 |
| --- | --- | --- |
| 1 | `luafiles.grf` | [luafiles.grf](https://github.com/rAthenaCN/ROClientFullCN/blob/master/luafiles.grf) |
| 2 | `map.grf` | [map.grf](https://github.com/rAthenaCN/ROClientFullCN/blob/master/map.grf) |
| 3 | `sprite.grf` | [sprite.grf](https://github.com/rAthenaCN/ROClientFullCN/blob/master/sprite.grf) |
| 4 | `texture_01.grf` | [texture_01.grf](https://github.com/rAthenaCN/ROClientFullCN/blob/master/texture_01.grf) |
| 5 | `texture_02.grf` | [texture_02.grf](https://github.com/rAthenaCN/ROClientFullCN/blob/master/texture_02.grf) |

1. 逐一開啟上方檔案頁面，使用 **Download／Download raw file** 取得實際檔案。
2. 下載完成後，複製到 `C:\RO-Server\RO-Client`，與登入器 EXE 放在同一層；同名檔案選擇取代。
3. 檢查這 5 個大型檔案是否完整。若檔案只有約 1 KB，且用文字編輯器開啟出現 `version https://git-lfs.github.com/spec/v1`，它是 LFS 指標，不是完整 GRF。
4. 若來源顯示 LFS 額度或下載限制，需等來源恢復或取得有權使用的完整檔案；單純把指標檔改名不會補齊資源。

**另外保留 Git 下載附帶的 `data.grf`。** 此來源的 `data.grf` 是小型 GRF（769 B），與上述 5 個大型資源檔不同；不要因為檔案小就刪除或用其他 Client 的同名檔取代。

## 3. 檢查 DATA.INI

用文字編輯器開啟：

```text
C:\RO-Server\RO-Client\DATA.INI
```

確認與來源的載入順序一致：

```ini
[Data]
0=data.grf
1=luafiles.grf
2=map.grf
3=sprite.grf
4=texture_01.grf
5=texture_02.grf
```

這裡的 **0～5 是 GRF 載入索引**，請保留。每個檔名都要與 Client 資料夾中的實際檔案相同。按 **Ctrl + S** 儲存。

[參考：來源 DATA.INI](https://github.com/rAthenaCN/ROClientFullCN/blob/master/DATA.INI)

## 4. 設定 Setup_Plus.exe

1. 在 Client 資料夾執行 `Setup_Plus.exe`。
2. 顯示裝置選擇 **「主顯示器驅動程式 [Direct3D HAL]」**（英文介面通常為 **Primary Display Driver [Direct3D HAL]**）。
3. 選擇主顯示器支援的解析度。
4. 按 **套用／確定** 儲存設定，再關閉設定視窗。

## 5. 設定本機連線

此來源附帶的連線設定檔為：

```text
C:\RO-Server\RO-Client\data\sclientinfo.xml
```

用文字編輯器開啟，找到 `<connection>` 區塊中的 `<address>`、`<port>`，修改為：

```xml
<address>127.0.0.1</address>
<port>6900</port>
```

保留 XML 其他內容，按 **Ctrl + S** 儲存。若使用的 Client 版本將設定檔命名為 `clientinfo.xml`，請修改該版本實際讀取的檔案，不要只為了配合名稱任意改名。

[參考：來源 sclientinfo.xml](https://github.com/rAthenaCN/ROClientFullCN/blob/master/data/sclientinfo.xml)

## 6. 核對 Server 與遊戲帳號

1. Client 為 `2021-11-03_Ragexe_patched.exe`，Server 的 `PACKETVER` 使用 **20211103**。設定與建置方式見 [02 編譯 Server](02-server.md#4-編譯-server)。
2. 依序啟動 `login-server.exe` → `char-server.exe` → `map-server.exe`，確認沒有連線錯誤並保持執行。
3. 確認已完成 [建立 GameMaster 帳號](02-server.md#8-建立-gamemastergm帳號)。登入遊戲使用 GM 遊戲帳號，不是 MariaDB 的 root 或資料庫帳號。

## 7. 啟動 Client 並確認

在 Client 資料夾執行：

```text
2021-11-03_Ragexe_patched.exe
```

完成確認：

1. 能進入登入畫面。
2. 使用已建立的遊戲帳號登入。
3. 能進入角色選擇，建立或選擇角色後進入遊戲地圖。
4. 沒有缺少 GRF、地圖或貼圖的錯誤。若出現缺檔錯誤，先回查步驟 2 的完整檔案及步驟 3 的載入順序。

保留整個 Client 資料夾作為備份，包含 GRF、設定檔與資源資料夾。

[下一步：三轉與伊甸園](04-third-jobs-eden.md)｜[回首頁](../README.md)

## 教學內容授權

本倉庫中由作者享有著作權的原創教學文字及自製圖解，採 [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.zh-hant) 授權。

歡迎非商業用途的分享與修改，請標示作者 **rayjhih8263**、[原始倉庫](https://github.com/rayjhih8263/RO-Private-Server-Setup-Guide)及授權連結，並註明修改內容；修改後公開分享時，須使用相同授權。未經權利人另行許可，不得將上述內容用於商業目的，包括打包販售、付費下載，或收錄於付費教材。

第三方軟體、遊戲素材、商標、截圖及圖片不屬於本授權範圍，仍依各權利人的授權規定使用。標註來源或交流用途，不等於取得授權。

[完整授權說明](../LICENSE.md)
