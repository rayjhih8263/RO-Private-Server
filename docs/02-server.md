# 02｜建立 Server（含資料庫）

狀態：依子步驟建立

依 01 確認的版本建立；新目標的模式尚未實作。02 的完成條件是三個 Server 正常連接資料庫並啟動。

## 02-1 安裝工具、下載原始碼與編譯

- 安裝 Git for Windows、Visual Studio Community；勾選「使用 C++ 的桌面開發」。Python 開發是選配。資料庫見下方 02-2。

- 建立 C:\RO-Server，在此開 Git Bash，執行：

```text
cd /c/RO-Server
git clone https://github.com/rathena/rathena.git
cd rathena
git status
```

- 確認原始碼位於 C:\RO-Server\rathena。原紀錄下載 master，但沒有記錄 commit，因此重新抓最新版不等於重現同一版。

- 開啟 C:\RO-Server\rathena\rAthena.sln，設定 Release / x64，建置方案。

- 確認產出 login-server.exe、char-server.exe、map-server.exe。原紀錄為 15 成功、0 失敗；其他版本不必有相同專案數，重點是無失敗與產出完整。

- 修改 PRERE 或 PACKETVER 等編譯設定前，先關閉伺服器；儲存後重新建置。模式與封包值見下方 02-3。
新電腦若要忠實重現，優先使用已備份的 rAthena 原始碼與設定；本次沒有操作你的 Windows 電腦，也沒有產生或編譯 Server。

## 02-2 建立資料庫與連線設定

- 原紀錄安裝 MariaDB 11.8.9 / Windows x86_64 / MSI；root 設定自選密碼；未開放遠端 root。Install as service、Enable networking，服務名 MariaDB、port 3306。這是舊版記錄，不是最新版本推薦。

- 從開始選單開 MySQL Client (MariaDB)，以 root 登入。以下只用於新的空白安裝；已有資料庫時先做 06 備份。

- 建立資料庫及專用帳號；將 YOUR_DB_PASSWORD 改成自己的密碼：

```text
CREATE DATABASE ragnarok CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
CREATE DATABASE ragnarok_log CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
CREATE USER 'ragnarok'@'localhost' IDENTIFIED BY 'YOUR_DB_PASSWORD';
GRANT ALL PRIVILEGES ON ragnarok.* TO 'ragnarok'@'localhost';
GRANT ALL PRIVILEGES ON ragnarok_log.* TO 'ragnarok'@'localhost';
FLUSH PRIVILEGES;
SHOW DATABASES;
```

- 用 MariaDB Client 匯入同一份 rAthena 的 SQL：

```text
USE ragnarok;
SOURCE C:/RO-Server/rathena/sql-files/main.sql;
SHOW TABLES;
USE ragnarok_log;
SOURCE C:/RO-Server/rathena/sql-files/logs.sql;
SHOW TABLES;
```

- 原紀錄確認主庫 56 表、Log 10 表；其他版本表數可能不同。確認沒有 SQL 錯誤，且存在 login、char、inventory、storage 等主表。原紀錄未匯入 item/mob SQL 或 upgrades。

- HeidiSQL 連線：MariaDB or MySQL (TCP/IP)、127.0.0.1、3306、ragnarok、自選資料庫密碼。

- 在 conf\inter_athena.conf 配置資料庫；依原紀錄已存在欄位修改，勿把未確認欄位整段新增：

```text
login_server_pw: YOUR_DB_PASSWORD
ipban_db_pw: YOUR_DB_PASSWORD
char_server_pw: YOUR_DB_PASSWORD
map_server_pw: YOUR_DB_PASSWORD
web_server_pw: YOUR_DB_PASSWORD
log_db_pw: YOUR_DB_PASSWORD

login_server_db: ragnarok
char_server_db: ragnarok
map_server_db: ragnarok
web_server_db: ragnarok
log_db_db: ragnarok_log
log_login_db: loginlog
```

- 各資料庫帳號使用 ragnarok，主機 127.0.0.1、3306。loginlog 是資料表名。設定後儲存，啟動驗證見下方 02-3。

- 原紀錄用 HeidiSQL 的查詢頁建立 GM 帳號。先選 ragnarok，替換帳密，僅執行一次：

```text
INSERT INTO `login`
(`userid`, `user_pass`, `sex`, `email`, `group_id`)
VALUES ('YOUR_GAME_USER', 'YOUR_GAME_PASSWORD', 'M', 'gm@localhost', 99);
```

M / F 為男性 / 女性帳號。此 SQL 對應舊紀錄的設定；目前密碼處理設定與 groups.conf 應先確認。不要更動 sex=S 的伺服器帳號來建立玩家。
HeidiSQL 1064 的最終處理是改用 SOURCE 匯入；不需要修改官方 main.sql。舊紀錄曾更換外露密碼，重建不需重演刪除帳號這段。

## 02-3 模式、封包、倍率與啟動測試

舊紀錄為懷舊模式。現在要三轉＋伊甸園，模式先依 01 確認，玩法驗證見 04；以下 PRERE 只記錄當時的成功設定。

- 舊模式檔案：src\config\renewal.hpp。當時把 //#define PRERE 改成 #define PRERE，重新建置後確認載入 db/pre-re。這不是新的三轉目標設定。

- 最後封包版本寫在 src\custom\defines_pre.hpp 的結尾 #endif 之前：

```text
#define PACKETVER 20220406
```

保留檔案原有結構，不直接修改 packets.hpp 的預設值。重新建置 Release / x64。

- conf\battle\exp.conf：

```text
base_exp_rate: 2000
job_exp_rate: 2000
```

100 表示 1 倍，2000 表示 20 倍。

- conf\battle\drops.conf：

```text
item_rate_common: 500
item_rate_heal: 500
item_rate_use: 500
item_rate_equip: 500
item_rate_card: 300

item_rate_common_boss: 100
item_rate_heal_boss: 100
item_rate_use_boss: 100
item_rate_equip_boss: 100
item_rate_card_boss: 100
item_rate_mvp: 100
```

掉率上下限等其餘設定未調整。

- 自動拾取：舊紀錄討論過 item_auto_get: yes 與 @autoloot；最後摘要寫使用 @autoloot，無法由文字判定 item_auto_get 最終值。此項列待確認，不補寫成已啟用。

- 依序啟動 login-server.exe → char-server.exe → map-server.exe。防火牆舊紀錄選私人網路，依實際連線需求配置。

- 確認 Login ready / 6900、Char ready / 6121、Map ready / 5121，以及 Successfully logged on to Char Server / Map Server is now online；資料庫連線不得反覆出錯。

- 舊紀錄曾自動使用 192.168.0.18 做伺服器間連線，後來確認先在同一台筆電遊玩；新電腦勿照抄此 IP。將來區網連線要核對 Server 對客戶端公告的 IP 與 Client 位址。

- 關服時先 Map，再 Char，再 Login。設定檔修改後需重新載入或重啟；原紀錄使用重啟確認。
99/70 未完成實機驗證；char_athena.conf 中沒有 max_base_level。不要把該欄位憑空新增，也不要把 Pre-Renewal 當成自動禁止三轉。

## 新對話開場文字

```text
這是 RO 私服步驟 02：建立 Server。請沿用步驟 01 確認的版本，依序安裝工具、取得原始碼、編譯、建立 MariaDB 與匯入 SQL、設定資料庫連線、模式/PACKETVER/倍率，最後測試 login、char、map 啟動。資料庫放在這個對話，不另外拆出去。現在目標三轉＋伊甸園＋OpenKore；已有角色資料時先備份再還原。每次只做一個步驟，完成後列出成功設定。
```
