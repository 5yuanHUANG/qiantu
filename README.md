# 錢途・個人財務規劃 App

獨立的手機網頁 App（PWA）。不需要 Claude 帳號，裝到主畫面後全螢幕開啟，沒網路也能記帳。

## 檔案
- `index.html`：App 本體
- `manifest.webmanifest`：App 名稱、圖示、全螢幕設定
- `sw.js`：離線快取
- `icons/`：Logo（`icon.svg` 是向量原檔）

## 上線（免費，二選一）

App 必須放在 https 網址上，手機才能「安裝」。

### 方法 A：GitHub Pages（推薦，網址永久不變）
1. 到 github.com 註冊並登入
2. 右上角「+」→「New repository」，名稱填 `qiantu`，選 **Public**，按「Create repository」
3. 在新頁面點「uploading an existing file」，把這個資料夾**裡面的所有檔案和 icons 資料夾**拖進去，按「Commit changes」
4. 到 repository 的「Settings」→ 左側「Pages」→ Branch 選 `main`、資料夾選 `/ (root)` → Save
5. 等 1–2 分鐘，網址會是 `https://你的帳號.github.io/qiantu/`

之後要更新 App，只要重新上傳 `index.html` 覆蓋即可。

> 程式碼公開沒關係：你的財務資料只存在你的手機，不在這些檔案裡。

### 方法 B：Netlify Drop（最快，拖曳即可）
1. 到 app.netlify.com/drop
2. 把整個 `qiantu-app` 資料夾拖進去
3. 註冊帳號以保留網址（不註冊的話網址只保留 1 小時）

## 安裝到手機
- **iPhone**：用 Safari 開網址 → 下方「分享」→「加入主畫面」
- **Android**：用 Chrome 開網址 → App 裡會出現「安裝」按鈕，或右上角「⋮」→「安裝應用程式」

## AI 功能（選用）
「該不該買」的 AI 深入分析、AI 健檢、顧問聊天、拍收據需要 Claude API 金鑰：
1. 到 console.anthropic.com 註冊、儲值
2. 「API Keys」建立金鑰，**並在 Limits 設定每月花費上限**
3. 在 App 的「設定 → AI 功能」貼上金鑰

金鑰只存在你的手機，不會出現在備份檔。使用模型：Claude Opus 5.5（遇到安全審查時會自動改用備援模型）。

## 資料與備份
- 資料只存在安裝 App 的那支手機的瀏覽器裡，不會同步到其他裝置
- 每月到「設定 → 匯出備份」，存到雲端硬碟或用 LINE 傳給自己
- 換手機時：新手機安裝後「匯入備份」即可
- 在 Claude 版本記的資料也可以用同樣方式匯出、匯入過來
