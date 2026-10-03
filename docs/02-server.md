# 02 建立 Server

依序完成下面步驟。資料庫指令用於全新、空白資料庫。

## 0. 安裝 Git

下載：[Git for Windows](https://gitforwindows.org/)

點 **Download**，下載 Windows 安裝程式並完成安裝。後面的原始碼下載會使用 Git Bash。

## 1. 安裝編譯工具

下載：[Visual Studio Community](https://visualstudio.microsoft.com/zh-hant/vs/community/)

1. 點「免費下載」，執行下載的安裝程式。
2. 開啟 Visual Studio Installer 的「工作負載」畫面。
3. 勾選 **使用 C++ 的桌面開發**。
4. 點「安裝」，等待完成。

完成確認：能開啟 Visual Studio。

參考畫面（Microsoft 官方文件，版本不同時外觀可能略有差異）：

![Visual Studio：選擇 C++ 桌面開發](https://learn.microsoft.com/zh-tw/cpp/get-started/media/vs-2026/visual-studio-installer-cpp-workload.png)

[查看官方圖文說明](https://learn.microsoft.com/zh-tw/cpp/build/vscpp-step-0-installation)

## 2. 準備 rAthena

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

## 3. 編譯 Server

開啟：

```text
C:\RO-Server\rathena\rAthena.sln
```

選擇 **Release → x64 → 建置方案**。

完成後應有這三個檔案，且建置沒有失敗：

```text
login-server.exe
char-server.exe
map-server.exe
```

## 4. 安裝資料庫

下載：[MariaDB Server](https://mariadb.org/download/)

已使用版本：**11.8.9**。下載時核對版本，選 **Windows / x86_64 / MSI**，再執行 `.msi` 安裝程式。

安裝時設定：

- 服務名稱：MariaDB
- Port：3306
- 設定自己的 root 密碼
- 勾選 Install as service、Enable networking

完成確認：開始選單可找到 MariaDB Client。

參考畫面（MariaDB 官方文件）：

**設定 root 密碼的畫面**

![MariaDB：設定 root 密碼](https://2988006611-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FSsmexDFPv2xG2OTyO5yV%2Fuploads%2Fgit-blob-9a33617da161fc206c87b5bfc620c2bad5297f36%2FDatabaseProperties_1_New.png?alt=media)

**設定服務名稱與 Port 的畫面**

![MariaDB：服務名稱與 Port](https://2988006611-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FSsmexDFPv2xG2OTyO5yV%2Fuploads%2Fgit-blob-2e4b4eee2d20b741a9ee1cda8b5c9cfcf0495537%2FDatabaseProperties_2_New.png?alt=media)

圖片只供辨認欄位；請填本手冊的 **MariaDB / 3306**，密碼用自己的。

[查看官方圖文說明](https://mariadb.com/docs/server/server-management/install-and-upgrade-mariadb/installing-mariadb/binary-packages/installing-mariadb-msi-packages-on-windows)

## 5. 建立資料庫

開啟 **MySQL Client (MariaDB)**，輸入 root 密碼。

將下面的 `YOUR_DB_PASSWORD` 換成自己的資料庫密碼，再執行：

```sql
CREATE DATABASE ragnarok CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
CREATE DATABASE ragnarok_log CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
CREATE USER 'ragnarok'@'localhost' IDENTIFIED BY 'YOUR_DB_PASSWORD';
GRANT ALL PRIVILEGES ON ragnarok.* TO 'ragnarok'@'localhost';
GRANT ALL PRIVILEGES ON ragnarok_log.* TO 'ragnarok'@'localhost';
FLUSH PRIVILEGES;
```

## 6. 匯入資料表

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

## 7. 設定資料庫連線

開啟：

```text
C:\RO-Server\rathena\conf\inter_athena.conf
```

修改檔案中已有的資料庫連線欄位：

- 主機：127.0.0.1
- Port：3306
- 資料庫帳號：ragnarok
- 資料庫密碼：步驟 5 設定的密碼
- Login、Char、Map、Web 使用資料庫：ragnarok
- Log 使用資料庫：ragnarok_log
- `log_login_db`：loginlog

儲存檔案。

## 8. 啟動 Server

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
