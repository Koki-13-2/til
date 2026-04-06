# stock_visualizer_express_yahoo_finance

> 保存日: 2026-04-06

# Express + Yahoo Finance API 株価・業績可視化アプリ

## 構成
- `server.js` — Express + Axios で Yahoo Finance API をプロキシ
- `public/` — Chart.js でチャート描画 (Vanilla JS)

## Yahoo Finance エンドポイント
```js
// 株価履歴 (v8)
GET https://query1.finance.yahoo.com/v8/finance/chart/{symbol}?range=6mo&interval=1d

// 業績・財務 (v10)
GET https://query1.finance.yahoo.com/v10/finance/quoteSummary/{symbol}?modules=incomeStatementHistory,defaultKeyStatistics,summaryDetail,financialData
```

## ポイント
- ヘッダーに `User-Agent: Mozilla/5.0` を付けないと弾かれる
- 日本株は `7203.T` のように `.T` suffix
- v8はtimestamp(Unix秒)→ISO日付変換が必要
- Chart.jsでbar+lineのmixedチャートは `type:'bar'` ベースで datasetに `type:'line'` を指定

## GitHub
https://github.com/Koki-13-2/stock-visualizer

