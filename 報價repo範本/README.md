# 每日收盤價（金幣池報價來源）

GitHub Actions 每天抓台股、美股收盤價、美元匯率和近一年除息紀錄，存成 JSON，給「地球Online金幣池」的每日排程任務讀取。

1. 在 GitHub 建一個 **Public** repo（例如 `stock-quotes`），把這個資料夾的檔案全部上傳。
2. 編輯 `data/symbols.json`，換成你自己持有的代號（台股填 `TW`、美股填 `US`）。
3. Settings → Actions → General → Workflow permissions 選「Read and write permissions」。
4. Actions → 更新收盤價 → Run workflow，跑一次確認 `data/quotes.json` 有產生。

之後台北時間週一到週五 14:20、16:20（台股）和 06:20（美股）會自動更新。讀取網址：

```
https://raw.githubusercontent.com/<你的帳號>/<repo 名稱>/main/data/quotes.json
```

這個 repo 只放價格，不會有你的股數和成本。買了新股票記得把代號加進 `symbols.json`。
