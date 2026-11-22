# D2R 飾品拍賣所

架在 GitHub Pages 上的 D2R 戒指／護身符／頭環拍賣頁面。

- 前台：`https://<你的帳號>.github.io/<repo 名稱>/`
- 管理後台：網址後面加上 `#admin`

## 檔案

| 檔案 | 用途 |
| --- | --- |
| `index.html` | 整個網站（前台 + 管理後台） |
| `data/listings.json` | 所有刊登資料，由管理後台自動更新 |
| `images/` | 上傳的物品截圖，由管理後台自動建立 |

## 第一次設定

1. 建立一個 **Public** repository，把 `index.html`、`data/listings.json`、`README.md` 上傳上去。
2. Settings → Pages → Source 選 **Deploy from a branch**，Branch 選 `main`、資料夾選 `/ (root)` → Save。
3. 建立權杖：GitHub 右上角頭像 → Settings → Developer settings → Personal access tokens → **Fine-grained tokens** → Generate new token
   - Repository access：**Only select repositories** → 選這個 repo
   - Permissions → Repository permissions → **Contents：Read and write**
   - 產生後複製 `github_pat_...` 開頭的權杖
4. 開啟 `https://<你的帳號>.github.io/<repo 名稱>/#admin`，填入帳號、repo 名稱、權杖，按「連線並登入」。

## 截圖上架（登入後上方的「截圖上架」）

1. 先填「上架預設值」：天梯、模式、平台、區域、聯絡方式。
2. 用電腦版 Chrome 或 Edge，遊戲設為「視窗化」或「無邊框視窗」，按「選取遊戲視窗」選 D2R；沒開遊戲時可用「上傳整張截圖」測試。
3. 把滑鼠移到裝備上停約半秒，會跳出確認視窗：修正文字、在「價格」分頁設定符文或以物易物。
4. 按「儲存並上架」直接發佈；或按「儲存」先存到擷取區，之後再按卡片上的「上架」或「全部上架」。
5. 按「開啟置頂視窗」可讓確認表單浮在遊戲畫面上。
6. 上架的截圖會轉成 JPEG 存到 repo 的 images/ 資料夾；擷取區本身只存在這台電腦的瀏覽器。

## 注意

- 權杖只存在你登入那台裝置的瀏覽器裡。不要把權杖貼到任何其他地方，也不要寫進 repo 的檔案。
- 別人也能打開 `#admin`，但沒有權杖就無法讀寫任何東西。
- 每次上架或修改都會在 repo 產生一筆 commit；GitHub Pages 約 1 分鐘後更新，其他人才會看到。
- 刊登資料都在 git 歷史裡，改錯了可以從 commit 紀錄還原。
