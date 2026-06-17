# 政府採購每日查標整理 MVP

這是一個公司內部使用的政府採購標案整理小工具，採用「GitHub Pages 前端 + Google Apps Script 寫入 Google Sheet」的輕量方案。

## 目前功能

- 前端入口密碼：`1234`
- 人工貼上政府採購網查詢結果
- 解析欄位格式與表格格式
- 依關鍵字與規則做初步分類
- 顯示每日標案清單
- 產生可複製的群組回報文字
- 透過 Google Apps Script 寫入 Google Sheet
- 不自動傳群組
- 不自動登入政府採購網
- 不自動領標、付款、加值或請款

## 檔案說明

```text
public/index.html
apps-script/Code.gs
docs/DEPLOY_GITHUB_PAGES_APPS_SCRIPT.md
```

## 使用流程

1. 將 `apps-script/Code.gs` 貼到 Google Apps Script。
2. 在 Apps Script 設定 `SCRIPT_TOKEN`。
3. 部署 Apps Script 為 Web App。
4. 在 GitHub Pages 開啟 `public/index.html`。
5. 輸入入口密碼 `1234`。
6. 填入 Apps Script Web App URL、API Token、Google Sheet ID、分頁名稱。
7. 貼上標案資料後，按「解析標案」。
8. 確認清單後，按「寫入 Google Sheet」。

## 安全提醒

這個版本不會把 Google Service Account private key 放在前端。Google Sheet 寫入由 Apps Script 執行。

前端密碼 `1234` 只適合內部小工具，不是正式資安防護。真正防止外部寫入的是 Apps Script 的 `SCRIPT_TOKEN`。
