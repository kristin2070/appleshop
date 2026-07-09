# 🍎 燦坤五甲店 Apple Shop · 部署指南

> 從這個 zip 到上線只要 5 分鐘 ✨

## ✅ 包裡有什麼

- `index.html` — 手機落地頁(QR 掃進來看到的頁面)
- `dm.html` — A4 列印 DM
- `stats.html` — Apple Watch 風格統計儀表板
- `summary.html` — 對外說明頁
- `store.jpg` — 店面照片(已用你上傳的)
- `qrcode-final.png` — 800×800 QR Code(已自動指向你的網站)
- `shop-config.json` — 你填的設定(備份,以後重生用)
- `scripts/send-report.js` + `.github/workflows/weekly-report.yml` — 週報 Email


## 🚀 5 分鐘部署到 GitHub Pages

### 步驟 1:在 GitHub 建一個新 repo
1. 開 [github.com/new](https://github.com/new)
2. **Repository name** 填:`appleshop`
3. 設為 **Public**(GitHub Pages 免費版需要 public)
4. **不要** 勾 README/gitignore
5. 點 `Create repository`

### 步驟 2:上傳所有檔案
**最簡單的方法 — 網頁上拖拉:**
1. 在剛建好的 repo 頁面點 `uploading an existing file`
2. 把這個資料夾的**全部檔案**拖進去(包括 `scripts/`、`.github/` 子資料夾)
3. 下方填 commit message:`Initial deploy`
4. 點 `Commit changes`

> ⚠️ `.github` 資料夾因為以 `.` 開頭,Mac Finder 預設隱藏。按 `⌘+Shift+.` 可以顯示。

### 步驟 3:啟用 GitHub Pages
1. 到 `https://github.com/kristin2070/appleshop/settings/pages`
2. **Source** 選 `Deploy from a branch`
3. **Branch** 選 `main` + `/ (root)`,點 `Save`
4. 等約 30 秒,頁面會顯示綠色勾勾和你的網址

### 步驟 4:測試 ✅
- 開 [https://kristin2070.github.io/appleshop/](https://kristin2070.github.io/appleshop/) 看落地頁
- 開 [https://kristin2070.github.io/appleshop/stats.html](https://kristin2070.github.io/appleshop/stats.html) 看儀表板
- 用手機掃 `qrcode-final.png` → 點按鈕 → 數字會 +1 🎉


## 📧 啟用週報 Email(進階,可晚點再做)

每週日 22:00 自動寄統計報表到你的 Gmail。

### 1. 申請 Gmail App Password
1. 開 [myaccount.google.com/apppasswords](https://myaccount.google.com/apppasswords)
2. 兩步驟驗證如果還沒開,先開
3. 建一個 App Password(取名「AppleShop 週報」)
4. 把出現的 16 碼密碼複製起來

### 2. 在 GitHub Repo 加 Secrets
1. 到 `https://github.com/kristin2070/appleshop/settings/secrets/actions`
2. 點 `New repository secret`,加 3 個:
   - `GMAIL_USER` = 你的 Gmail(寄信用)
   - `GMAIL_APP_PASSWORD` = 剛才那 16 碼
   - `REPORT_TO` = lanlin2070@icloud.com
3. 完成後第一次手動測試:
   - 到 `https://github.com/kristin2070/appleshop/actions/workflows/weekly-report.yml`
   - 點 `Run workflow` → 等 30 秒 → 看信箱


## 🖨 列印 A4 DM

開 [https://kristin2070.github.io/appleshop/dm.html](https://kristin2070.github.io/appleshop/dm.html) → 按 `⌘+P`(Mac)或 `Ctrl+P`(Win):
- 紙張:**A4** + **橫向**
- 邊界:**無**
- ✅ 一定要勾 **「背景圖形」**(否則黃色變灰色)

## 📊 你的店重要 URL

| 用途 | URL |
|---|---|
| 📱 落地頁(QR 目標) | https://kristin2070.github.io/appleshop/ |
| 🖼 DM | https://kristin2070.github.io/appleshop/dm.html |
| 📊 儀表板 | https://kristin2070.github.io/appleshop/stats.html |
| 🖼 QR Code | https://kristin2070.github.io/appleshop/qrcode-final.png |
| 💻 Repo | https://github.com/kristin2070/appleshop |

## 🔧 之後要改店家資料

1. 直接到 `https://github.com/kristin2070/appleshop` 點檔案旁的鉛筆圖示編輯
2. 或重新去 [產生器頁面](https://magicbrian1206-maker.github.io/appleshop-starter/) 用 `shop-config.json` 重新生新版

## 🆘 出問題?

| 問題 | 解法 |
|---|---|
| GitHub Pages 沒生效 | 等 1-2 分鐘,刷新 `https://github.com/kristin2070/appleshop/settings/pages` |
| 統計都是 0 | 用手機(不是電腦)掃 QR 點按鈕,電腦點不算 |
| 店家照片沒顯示 | 確認 `store.jpg` 大小寫正確,有上傳到 repo 根目錄 |
| 週報沒寄出 | 檢查 3 個 Secrets 都有設;Gmail App Password 不是主密碼 |

---

**🎁 這個系統由 [燦坤華榮 AppleShop](https://github.com/magicbrian1206-maker/landing) 開源分享**
歡迎用、歡迎改、歡迎再分享給其他店家 💛
