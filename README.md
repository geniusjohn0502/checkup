# 灰哥財務健檢表

填入收入、支出、資產、負債，自動算出個人淨值和五項財務健康指標（儲蓄率、緊急備用金倍數、收入負債比、非工資收入占比、財務自由指數）。

- **線上網址**：https://checkup.morechoice.net
- **本機檔案**：`~/Documents/checkup/index.html`（單一 HTML 檔，沒有後端、沒有資料庫）
- **來源**：2026-10-14 在 Claude 上做好，同日搬到自己的網域；Claude 版 2026-10-15 已刪除，**這裡是唯一的一份**

## 資料存在哪

填的數字只存在訪客自己瀏覽器裡（localStorage），不會傳到任何伺服器。
要交給別人看，用頁面上的「產生健檢碼」：整份資料壓成一串 `MC-日期-…` 的文字，對方打開同一個網址按「貼上健檢碼」就能還原。

## 跟 Claude 版的差別

只有「一鍵匯出 PDF」：Claude 版靠平台的下載功能，這裡改成瀏覽器直接下載。其餘完全一樣。

## 網域設定

- Cloudflare DNS：`CNAME` `checkup` → `geniusjohn0502.github.io`，**Proxy 關閉（灰色雲朵，僅 DNS）**
- GitHub：Settings → Pages → Custom domain `checkup.morechoice.net`，勾選 Enforce HTTPS
- 憑證卡住發不出來時：**先等 DNS 生效 10–15 分鐘**，再把自訂網域移除 → 等建置完成 → 等 1 分鐘 → 設回去（2026-10-14 這頁就是做太早，多等了一個多小時）
