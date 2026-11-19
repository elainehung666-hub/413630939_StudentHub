<img width="1917" height="1078" alt="螢幕擷取畫面 2026-11-18 010316" src="https://github.com/user-attachments/assets/22ea74dc-1426-4fd7-8573-a633a62bd597" />
<img width="1895" height="1078" alt="螢幕擷取畫面 2026-11-17 232220" src="https://github.com/user-attachments/assets/f29d4f73-624d-4088-911d-7071dd7b3b70" />

## 遇到的問題與解法
**現象**：Postman 呼叫 findAll 回傳 500，後端出現
`buffering timed out after 10000ms`。

**原因**：MongoDB.ts 的連線字串使用 `authSource=admin`，
但 `studenthub_app` 帳號建立在 `studenthub` 資料庫，驗證失敗。

**解法**：將 authSource 改為 `${info.dbName}`，重啟後端後回傳 200。
