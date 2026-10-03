# 03 建立 RO Client

## 這套 Client 的組成

依分享對話最後續做的順序：

1. 最初嘗試 [ROClientFullCN](https://github.com/rAthenaCN/ROClientFullCN)，但完整 GRF 下載遇到 Git LFS 問題。
2. 改用 Froggo Rö Folder 完整包，解壓到 `C:\RO-Server\RO-Client-20220406`。
3. 保留這個資料夾的資源，另外放入 `2022-04-06_Ragexe_1648707856.exe`，改用這個乾淨 EXE 測試。
4. 使用 ROEnglishRE 的 ClientGenerator，選擇 Pre-Renewal / 2022-04-06，產生 data 與 SystemEN，接著進行資源複製與調整。
5. 最後停在準備 WARP 補丁，尚無成功登入的完成紀錄。

這段是來源追查紀錄；資源複製與補丁的完整組合尚未測試成功。

以下保留舊對話中已完成的準備與設定。最後停在補丁階段，尚未成功登入遊戲。

## 1. 準備 Client 資料夾

舊電腦已將 Client 放在：

```text
C:\RO-Server\RO-Client-20220406
```

Client 包含遊戲資源，不能只有一個 EXE。舊包中已有：

```text
ROTP20220406.grf
official_data.grf
data
System
SystemEN
Setup.exe
```

## 2. 放入 Client EXE

舊對話使用的檔案：

```text
2022-04-06_Ragexe_1648707856.exe
```

放在 Client 根目錄。這個 EXE 在舊電腦能啟動，但後續資源與補丁尚未完成。

## 3. 設定連線到自己的 Server

Client 和 Server 在同一台電腦時，開啟：

```text
C:\RO-Server\RO-Client-20220406\data\clientinfo.xml
```

將第一組 `connection` 的位址與 Port 改成：

```xml
<address>127.0.0.1</address>
<port>6900</port>
```

儲存檔案。這是舊對話已完成的設定。

## 目前做到哪裡

Client 檔案與本機連線設定已有紀錄。下一個未完成的階段是 WARP 補丁，之後才是登入、建角與進地圖測試。成功後再補上操作步驟。

[回首頁](../README.md)
