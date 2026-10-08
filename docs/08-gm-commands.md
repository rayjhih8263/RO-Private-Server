# 08 GM 指令手冊

繁體中文 | [English](en/08-gm-commands.md) | [回目錄](../README.md)

## 1. 確認 GM 權限

先依 [建立 GameMaster 帳號](02-server.md) 完成帳號設定，登入遊戲後在聊天欄輸入指令，按 Enter 執行。指令名稱使用半形英文字元。

標準設定中 `group_id = 99` 對應 Admin，`conf/groups.yml` 的 `Permissions: all_commands: true` 開放所有註冊指令。自訂 `conf/import/groups.yml`、地圖限制、角色狀態、Server 編譯模式及 Client 支援仍可能限制執行。

本手冊是指定 rAthena 來源版本的完整內建指令參考，不代表每一台 Server 都有同樣的指令；不含自訂 C++ 指令和 NPC 腳本綁定指令。2021 Client 不一定支援較新指令所開啟的介面或較新職業。

## 2. 查看這台 Server 真正可用的指令

1. 輸入 `@commands`，列出目前 GM 可用的 `@` 指令。
2. 輸入 `@charcommands`，列出目前 GM 可用的 `#` 指令。
3. 輸入 `@help item`，查看指定指令說明；把 `item` 換成要查的指令名称。
4. 網頁按 Ctrl + F 搜尋指令名稱；完整索引列於第 5 節。

`@` 通常以自己為操作角色；有些指令本身已包含玩家名稱。`#` 則指定另一位角色作為指令的執行對象：

```text
#指令 "角色名稱" 參數
#heal "Test Player"
```

使用 `#` 前先核對 `@charcommands`。不是所有操作都應任意改成 `#`；指令本身的目標、權限與限制仍需確認。預設符號為 `@` 和 `#`，可由 Server 自訂。

`<...>` 表示需要填入的參數，`[...]` 表示可選參數；不要把括號照打進遊戲。表格中的「玩家名稱／職業ID」需換成實際值。

## 3. 常用指令與範例

| 分類 | 輸入範例 | 用途 |
| --- | --- | --- |
| 查詢 | `@commands` | 列出此 GM 可用的 @ 指令 |
| 查詢 | `@charcommands` | 列出此 GM 可用的 # 指令 |
| 查詢 | `@help item` | 查看 item 的參數及說明 |
| 查詢 | `@rates` | 查看伺服器經驗及掉寶倍率 |
| 查詢 | `@who` | 列出線上玩家 |
| 查詢 | `@where 玩家名稱` | 查看指定角色位置 |
| 移動 | `@warp prontera 150 150` | 移動到普隆德拉指定座標 |
| 移動 | `@go 0` | 移動到普隆德拉 |
| 移動 | `@load` | 回到自己的儲存點 |
| 角色 | `@heal` | 補滿自己的 HP、SP |
| 角色 | `@alive` | 復活自己 |
| 角色 | `@raise 玩家名稱` | 復活指定角色 |
| 角色 | `@blvl 10` | 增加 10 個 Base 等級；不是設定為等級 10 |
| 角色 | `@jlvl 10` | 增加 10 個 Job 等級；不是設定為等級 10 |
| 角色 | `@jobchange 職業ID` | 變更職業；需符合 Server 模式及 Client 支援 |
| 角色 | `@allskill` | 取得技能；不代表 Client 支援所有技能 |
| 角色 | `@reset` | 重置素質與技能點數 |
| 角色 | `@resetstat` | 重置素質點數 |
| 角色 | `@resetskill` | 重置技能點數 |
| 角色 | `@speed 150` | 設定移動速度；預設 150，數值越小越快 |
| 角色 | `@hide` | 切換 GM 隱身，再輸入一次恢復 |
| 道具 | `@item 501 10` | 取得 10 個紅色藥水 |
| 道具 | `@zeny 100000` | 增加 100000 Zeny |
| 道具 | `@storage` | 開啟倉庫 |
| 怪物 | `@monster 1002 1` | 在附近生成 1 隻波利 |
| 管理 | `@kick 玩家名稱` | 讓指定角色斷線 |
| 管理 | `@jail 玩家名稱` | 將指定角色送入監獄 |
| 管理 | `@unjail 玩家名稱` | 將指定角色釋放 |
| 重新載入 | `@reloadscript` | 重新載入 NPC 腳本；可能中斷進行中的對話或活動 |
| 重新載入 | `@reloadbattleconf` | 重新載入戰鬥設定 |
| 重新載入 | `@reloadatcommand` | 重新載入指令設定 |

## 4. 管理與重新載入注意事項

1. `@item`、`@zeny`、等級及技能指令會改變遊戲資料；測試角色與一般遊玩角色建議分開。
2. `@kickall` 會讓全部角色斷線；封鎖、刪除道具、清除怪物及變更帳號指令，先核對目標及參數。
3. 修改 NPC、道具或倍率設定後，依對應指令重新載入；需要變更 C++、PACKETVER 或編譯模式時，仍要重新建置。
4. 顯示 Unknown Command 時，先核對指令拼字、Server 版本及 GM 權限；有列在手冊不代表目前角色能執行。

## 5. 完整指令索引（313 個內建名稱及所有設定別名）

以下完整參考保留官方英文用途和參數，避免翻譯改變語法。每個指令都有獨立說明；英文長篇清單可直接搜尋。官方 Help 可能與實作有差異，以同版本原始碼及遊戲內實際結果為準。

- [完整指令、別名、參數與用途](reference/gm-commands-rathena.md)
- [原始 Help 設定快照](reference/rathena-atcommands.yml)

## 6. 參考來源與授權

- [Command registry and implementation](https://github.com/rathena/rathena/blob/d4b8e7b8f16061cc2496d377ac8f777ce72a4f39/src/map/atcommand.cpp)
- [Help and aliases](https://github.com/rathena/rathena/blob/d4b8e7b8f16061cc2496d377ac8f777ce72a4f39/conf/atcommands.yml)
- [GM group permissions](https://github.com/rathena/rathena/blob/d4b8e7b8f16061cc2496d377ac8f777ce72a4f39/conf/groups.yml)

Source revision: `d4b8e7b8f16061cc2496d377ac8f777ce72a4f39`.

完整參考與官方設定快照保留 rAthena 的 GPL-3.0-or-later 授權，**不適用本倉庫教學內容的非商業限制**；詳見 [來源與授權](reference/README.md)。原創操作說明依 [教學授權](../LICENSE.md) 使用。
