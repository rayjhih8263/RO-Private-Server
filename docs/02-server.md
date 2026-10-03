# 02 建立 Server

依序完成下面步驟。資料庫指令用於全新、空白資料庫。

## 1. 安裝 Git

下載：[Git for Windows](https://gitforwindows.org/)

點 **Download**，下載 Windows 安裝程式並完成安裝。後面的原始碼下載會使用 Git Bash。

## 2. 安裝編譯工具

下載：[Visual Studio Community](https://visualstudio.microsoft.com/zh-hant/vs/community/)

1. 在網頁找到 **Visual Studio Community**，點這一欄的 **「免費下載」**。
2. 執行下載的安裝程式。
3. 開啟 Visual Studio Installer 的「工作負載」畫面。
4. 勾選 **使用 C++ 的桌面開發**。
5. 點「安裝」，等待完成。

下載頁參考截圖：選左側 **Community → 免費下載**。

![Visual Studio Community 免費下載](../assets/vs-community-free-download.jpg)

完成確認：能開啟 Visual Studio。

參考畫面（Microsoft 官方文件，版本不同時外觀可能略有差異）：

![Visual Studio：選擇 C++ 桌面開發](https://learn.microsoft.com/zh-tw/cpp/get-started/media/vs-2026/visual-studio-installer-cpp-workload.png)

[查看官方圖文說明](https://learn.microsoft.com/zh-tw/cpp/build/vscpp-step-0-installation)

## 3. 準備 rAthena

原始碼：[rAthena GitHub](https://github.com/rathena/rathena)

建立 `C:\RO-Server` 資料夾，在資料夾空白處按右鍵 → 顯示其他選項 → Open Git Bash here，輸入：

```bash
cd /c/RO-Server
git clone https://github.com/rathena/rathena.git
```

下載完成後，原始碼位於：

```text
C:\RO-Server\rathena
```

要重現原本成功的版本，使用已保存的原始碼；上面的指令會下載當前版本。

完成確認：資料夾內能找到 `rAthena.sln`。

[Windows 安裝參考手冊](https://github.com/rathena/rathena/wiki/Install-on-Windows)

## 4. 編譯 Server

開啟：

```text
C:\RO-Server\rathena\rAthena.sln
```

先選擇 **Release → x64**，再用以下任一方式建置：

- 選單：上方「建置（B）」→「建置方案」。
- 快捷鍵：**Ctrl + Shift + B**（同時按下，Visual Studio 預設按鍵）。

[快捷鍵參考：Microsoft 官方文件](https://learn.microsoft.com/zh-tw/visualstudio/ide/default-keyboard-shortcuts-in-visual-studio)

完成後，查看 Visual Studio 下方的「輸出」視窗。

你當時成功的建置結果是：

```text
15 成功，0 失敗
```

確認 **失敗為 0**，並產生以下三個檔案。若使用不同版本的 rAthena，成功專案數可能不同：

```text
login-server.exe
char-server.exe
map-server.exe
```

## 5. 安裝資料庫

下載：[MariaDB Server](https://mariadb.org/download/)

已使用版本：**11.8.9**。在下載頁依序選擇：

1. MariaDB Server Version：**11.8.9**。
2. Operating System：**Windows**。
3. Architecture：**x86_64**。
4. Package Type：**MSI Package**。
5. 點 **Download**，下載完成後執行 `mariadb-11.8.9-winx64.msi`。

下載頁參考截圖：

![MariaDB 11.8.9 Windows MSI 下載選項](../assets/mariadb-download-options-11-8-9.jpg)

安裝時設定：

- **Service Name（Windows 服務名稱）**：可以自訂，例如 `MariaDB` 或 `RODatabase`。這是 Windows「服務」中的名稱，不是遊戲內的 Server 名稱，也不是資料庫帳號。
- **TCP port：3306**：MariaDB／MySQL 慣用的預設連接埠，保持預設能讓後面的連線設定一致。可以改，但步驟 8 的所有資料庫 Port 都要一起改；若 3306 已被其他資料庫占用，可另選未使用的 Port。
- 設定自己的 root 密碼
- 勾選 Install as service、Enable networking

完成確認：開始選單可找到 MariaDB Client。

參考畫面（MariaDB 官方文件）：

**設定 root 密碼的畫面**

![MariaDB：設定 root 密碼](https://2988006611-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FSsmexDFPv2xG2OTyO5yV%2Fuploads%2Fgit-blob-9a33617da161fc206c87b5bfc620c2bad5297f36%2FDatabaseProperties_1_New.png?alt=media)

**設定服務名稱與 Port 的畫面**

![MariaDB：服務名稱與 Port](https://2988006611-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FSsmexDFPv2xG2OTyO5yV%2Fuploads%2Fgit-blob-2e4b4eee2d20b741a9ee1cda8b5c9cfcf0495537%2FDatabaseProperties_2_New.png?alt=media)

圖片只供辨認欄位（圖中為 MariaDB 10.6）；服務名稱可自訂，TCP port 建議維持 **3306**，密碼用自己的。

**紅框欄位說明（整理圖，非安裝程式截圖）：**

![服務名稱、Port 與資料庫帳號紅框說明](../assets/mariadb-custom-fields.svg)

[查看官方圖文說明](https://mariadb.com/docs/server/server-management/install-and-upgrade-mariadb/installing-mariadb/binary-packages/installing-mariadb-msi-packages-on-windows)

## 6. 建立資料庫

開啟 **MySQL Client (MariaDB)**，輸入 root 密碼。

**資料庫帳號也可以自訂**。下面的 `YOUR_DB_USER`、`YOUR_DB_PASSWORD` 都是占位文字，執行前要換成自己的帳號和密碼（例如帳號 `ro_user`）。三行中的帳號必須相同。

這是供 rAthena 連線的資料庫帳號，不是遊戲登入帳號；`localhost` 表示限本機使用。資料庫名稱這份手冊維持 `ragnarok`、`ragnarok_log`。

![資料庫帳號與其他可調整欄位紅框說明](../assets/mariadb-custom-fields.svg)

```sql
CREATE DATABASE ragnarok CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
CREATE DATABASE ragnarok_log CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
CREATE USER 'YOUR_DB_USER'@'localhost' IDENTIFIED BY 'YOUR_DB_PASSWORD';
GRANT ALL PRIVILEGES ON ragnarok.* TO 'YOUR_DB_USER'@'localhost';
GRANT ALL PRIVILEGES ON ragnarok_log.* TO 'YOUR_DB_USER'@'localhost';
FLUSH PRIVILEGES;
```

## 7. 匯入資料表

在同一個視窗依序執行：

```sql
USE ragnarok;
SOURCE C:/RO-Server/rathena/sql-files/main.sql;
SHOW TABLES;
USE ragnarok_log;
SOURCE C:/RO-Server/rathena/sql-files/logs.sql;
SHOW TABLES;
```

完成後能看到資料表，沒有 SQL 錯誤。

## 8. 設定資料庫連線

開啟：

```text
C:\RO-Server\rathena\conf\inter_athena.conf
```

修改檔案中已有的資料庫連線欄位：

- 主機：127.0.0.1
- Port：步驟 5 設定的 TCP port（預設 `3306`）
- 資料庫帳號：步驟 6 自訂的帳號（`YOUR_DB_USER` 替換後的實際值）
- 資料庫密碼：步驟 6 設定的密碼
- Login、Char、Map、Web 使用資料庫：ragnarok
- Log 使用資料庫：ragnarok_log
- `log_login_db`：loginlog

儲存檔案。

## 9. 啟動 Server

依序開啟：

```text
login-server.exe
char-server.exe
map-server.exe
```

看到以下結果代表啟動成功：

- Login：ready，Port 6900
- Char：ready，Port 6121
- Map：online，Port 5121
- 沒有資料庫連線錯誤

**完成：三個 Server 正常啟動。**

[下一步：建立 RO Client](03-client.md)


## 來源與用途說明

安裝畫面來源：上方已標示的 Microsoft、MariaDB 官方網站與文件；紅框欄位整理圖為本手冊製作。

本倉庫整理個人的安裝紀錄，供學習與技術交流參考，並非官方文件，亦不代表與相關權利人有合作或授權關係。文中提及的軟體、商標及第三方圖片，其權利屬各權利人；使用、修改或散布時，仍須遵守原始授權及適用法律。標註來源或交流用途，不等於取得授權。
