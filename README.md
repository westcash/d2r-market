# D2R 非天梯拍賣所

架在 GitHub Pages 上的 D2R 非天梯物品拍賣頁面（戒指、護身符、頭環、咒符，以及自訂類別）。

- 前台：`https://<你的帳號>.github.io/<repo 名稱>/`
- 管理後台：網址後面加上 `#admin`

## 檔案

| 檔案 | 用途 |
| --- | --- |
| `index.html` | 整個網站（前台 + 截圖上架 + 管理後台） |
| `data/listings.json` | 所有刊登資料與網站設定，由管理後台自動更新 |
| `images/` | 上傳的物品截圖與自訂樣式圖片，由管理後台自動建立 |

## 更新網站（已經架好的人）

只要把 repo 裡的 `index.html` 換成新版就好。**不要**覆蓋 `data/listings.json` 和 `images/`，那是你的刊登資料。舊的刊登資料不用轉換，新版可以直接讀。

## 第一次設定

1. 建立一個 **Public** repository，把 `index.html`、`data/listings.json`、`README.md` 上傳上去。
2. Settings → Pages → Source 選 **Deploy from a branch**，Branch 選 `main`、資料夾選 `/ (root)` → Save。
3. 建立權杖：GitHub 右上角頭像 → Settings → Developer settings → Personal access tokens → **Fine-grained tokens** → Generate new token
   - Repository access：**Only select repositories** → 選這個 repo
   - Permissions → Add permissions → **Contents** → 權限選 **Read and write**
   - 產生後複製 `github_pat_...` 開頭的權杖
4. 開啟 `https://<你的帳號>.github.io/<repo 名稱>/#admin`，填入帳號、repo 名稱、權杖，按「連線並登入」。

## 截圖上架（登入後上方的「截圖上架」）

1. 先填「上架預設值」：模式、平台、區域、聯絡方式（全部刊登都是非天梯）。
2. 用電腦版 Chrome 或 Edge，遊戲設為「視窗化」或「無邊框視窗」，按「選取遊戲視窗」選 D2R，再按「開啟置頂視窗」。**置頂視窗開著時才會自動擷取。**
3. 把滑鼠移到裝備上，素質方塊停住一下就會擷取（等待秒數在 管理後台 → 設定 → 截圖等待秒數）。
4. 在確認視窗：
   - 名稱欄打字會列出資料庫的暗金、套裝、符文之語和魔法咒符，選了之後屬性會變成表單，只有會變動的數值要填。
   - 「＋ 新增詞條」可以手動加屬性；方塊沒截完整可以按「重新框選」在整個畫面上重框。
   - 戒指、咒符可以選樣式（不選也可以）；在「價格」分頁設定符文或以物易物。
5. 按「儲存並上架」直接發佈；或按「儲存」先存到擷取區，之後再上架。

## 管理後台 → 設定

- **截圖等待秒數**：素質方塊停住多久才擷取（存在這台電腦的瀏覽器）。
- **戒指 / 咒符樣式圖片**：可以換成自己截的高畫質圖。
- **買家聊天（tawk.to）**：貼上 tawk.to 的 Direct Chat Link，拍賣所右下角就會出現聊天視窗，物品頁多一個「💬 詢問這件」。用 tawk.to 的手機 app 回覆。
- 文字辨識引擎、預設聯絡方式。

## 注意

- 權杖只存在你登入那台裝置的瀏覽器裡。不要把權杖貼到任何其他地方，也不要寫進 repo 的檔案。
- 別人也能打開 `#admin`，但沒有權杖就無法讀寫任何東西。
- 每次上架或修改都會在 repo 產生一筆 commit；GitHub Pages 約 1 分鐘後更新，其他人才會看到。
- 刊登資料都在 git 歷史裡，改錯了可以從 commit 紀錄還原。

## 資料來源

- 暗金、套裝、符文之語、魔法咒符詞綴的屬性與數值範圍：[blizzhackers/d2data](https://github.com/blizzhackers/d2data)（MIT License, Copyright (c) 2020 blizzhackers）。
- 獄火重生繁體中文物品名稱、詞綴名稱：[yatyricky/d2r-loot-filter](https://github.com/yatyricky/d2r-loot-filter) 收錄的遊戲字串（item-names、item-nameaffixes）。
- 繁體中文屬性文字、符文之語名稱：[elmagnificogi/diablo2_resurrected_filter](https://github.com/elmagnificogi/diablo2_resurrected_filter) 收錄的遊戲字串（item-modifiers、item-runes）。
- 2.6 / 3.0 新符文之語的中文名稱：[D2R World 新舊翻譯對照](https://d2r.world/zh-TW/info/misc/translates/runewords)。
- 技能的官方繁體中文名稱：[波波攻略島 新舊譯名對照](https://bobogameguides.com/diablo2/misc/translations.html)。
- 戒指、咒符樣式預設圖：直接連結 Blizzard 官方 classic.battle.net 的物品圖片，沒有存放在本網站。
- Diablo II: Resurrected 與相關名稱、圖片為 Blizzard Entertainment 所有；本網站為玩家自製，與 Blizzard 無關。
