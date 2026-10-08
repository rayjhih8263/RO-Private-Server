# RO 私服架設教學｜RO Private Server Setup Guide

繁體中文 | [English](README.en.md)

## 1. 基本架設

依序完成 01～03，即可建立 Server、設定 Client 並開始遊戲。

| 章節 | 內容 | 狀態 |
| --- | --- | --- |
| [01 確認版本](docs/01-versions.md) | Server、RO Client 與安裝工具版本 | ✅ |
| [02 建立 Server](docs/02-server.md) | 安裝工具、編譯、資料庫與 GM 帳號設定 | ✅ |
| [03 建立 RO Client](docs/03-client.md) | 下載 Client、補齊 GRF、連線並開始遊戲 | ✅ |

## 2. 延伸選項

依需求選擇；先完成基本架設，再進行下列調整。多人連線前建議先閱讀備份與帳號權限管理章節。

| 章節 | 內容 | 狀態 |
| --- | --- | --- |
| [01 中文化](docs/09-localization.md) | Client 介面、道具說明、NPC 對話與系統訊息 | 待補充 |
| [02 三轉與伊甸園](docs/04-third-jobs-eden.md) | 職業與伊甸園相關設定 | 待補充 |
| [03 經驗與掉寶倍率](docs/06-server-rates.md) | Base／Job 經驗、道具與卡片掉落倍率 | 待補充 |
| [04 遊戲規則設定](docs/optional-game-rules.md) | 等級上限、技能、負重與倉庫容量 | 待補充 |
| [05 帳號註冊方式](docs/optional-account-registration.md) | 一般玩家帳號建立與註冊設定 | 待補充 |
| [06 多人連線與對外連線](docs/optional-multiplayer-network.md) | 區域網路、IP、防火牆與路由器設定 | 待補充 |
| [07 NPC 與活動設定](docs/optional-npcs-events.md) | 傳送、補血、商店與自訂活動 | 待補充 |
| [08 新增武器與防具](docs/07-custom-equipment.md) | Server 道具資料與 Client 顯示資源 | 待補充 |
| [09 OpenKore](docs/05-openkore.md) | 連接自己的 Server | 待補充 |

## 3. 管理與指令參考

依日常管理、資料保護、排錯、GM 操作及版本維護的順序整理。

| 章節 | 內容 | 狀態 |
| --- | --- | --- |
| [01 啟動、關閉與重新載入](docs/admin-server-lifecycle.md) | 開關服順序、重新載入與重新編譯時機 | 待補充 |
| [02 備份與還原](docs/admin-backup-restore.md) | 資料庫、Server 設定與 Client 備份及還原 | 待補充 |
| [03 常見問題與排錯](docs/admin-troubleshooting.md) | Warning／Error、無法登入與缺少 GRF | 待補充 |
| [04 GM 指令手冊](docs/08-gm-commands.md) | 常用範例、完整內建指令與別名、權限及參數 | ✅ |
| [05 玩家帳號與 GM 權限管理](docs/admin-accounts-permissions.md) | 權限分組、停權與解除停權 | 待補充 |
| [06 Server 更新與版本管理](docs/admin-updates-versions.md) | 版本紀錄、更新前備份與更新失敗還原 | 待補充 |

## 參考來源

- [Git for Windows](https://gitforwindows.org/)
- [Visual Studio Community](https://visualstudio.microsoft.com/zh-hant/vs/community/)
- [Microsoft：Visual Studio 安裝說明與圖片](https://learn.microsoft.com/zh-tw/cpp/build/vscpp-step-0-installation)
- [rAthena 原始碼](https://github.com/rathena/rathena)／[Windows 安裝手冊](https://github.com/rathena/rathena/wiki/Install-on-Windows)
- [MariaDB 下載](https://mariadb.org/download/)／[Windows 安裝說明與圖片](https://mariadb.com/docs/server/server-management/install-and-upgrade-mariadb/installing-mariadb/binary-packages/installing-mariadb-msi-packages-on-windows)
- [ROClientFullCN：Client 來源紀錄](https://github.com/rAthenaCN/ROClientFullCN)（連結僅記錄使用來源；不代表已確認遊戲素材的散布授權。）

## 用途與權利說明

本倉庫提供 Windows 環境的架設教學，供學習與技術交流參考，並非官方文件，亦不代表與相關權利人有合作或授權關係。文中提及的軟體、商標及第三方圖片，其權利屬各權利人；使用、修改或散布時，仍須遵守原始授權及適用法律。標註來源或交流用途，不等於取得授權。


## 教學內容授權

本倉庫中由作者享有著作權的原創教學文字及自製圖解，採 [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.zh-hant) 授權。

歡迎非商業用途的分享與修改，請標示作者 **rayjhih8263**、[原始倉庫](https://github.com/rayjhih8263/RO-Private-Server-Setup-Guide)及授權連結，並註明修改內容；修改後公開分享時，須使用相同授權。未經權利人另行許可，不得將上述內容用於商業目的，包括打包販售、付費下載，或收錄於付費教材。

第三方軟體、遊戲素材、商標、截圖及圖片不屬於本授權範圍，仍依各權利人的授權規定使用。標註來源或交流用途，不等於取得授權。

[完整授權說明](LICENSE.md)
