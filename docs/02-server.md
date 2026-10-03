# 02 建立 Server

以下是舊電腦已成功的操作順序；建立全新、空白資料庫時使用。

## 1. 安裝編譯工具

安裝 Visual Studio Community，勾選「使用 C++ 的桌面開發」。

## 2. 準備 rAthena

把原始碼放在：

```text
C:\RO-Server\rathena
```

重新建立相同環境時，使用原電腦保存的原始碼。

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

舊電腦使用 MariaDB 11.8.9。安裝時設定：

- 服務名稱：MariaDB
- Port：3306
- 設定自己的 root 密碼
- 勾選 Install as service、Enable networking

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

**這一步完成的是 Server 啟動。三轉與伊甸園尚未設定完成。**

[下一步：建立 RO Client](03-client.md)
