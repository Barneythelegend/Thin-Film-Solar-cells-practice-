# Solar Cell Exam Lab — 薄膜太陽能電池英文題庫

可直接部署在 **GitHub Pages** 的靜態網站，不需要伺服器、不需要 API Key，也不需要裝 Node.js。

## 內容

- **209 題**：140 題英文四選一、43 題英文簡答、26 題數值計算。
- **每題顯示來源**：主要依 `Solar Cell-Review.pdf` 的 **PDF 頁碼（共 53 頁）** 標記。講義外的歷屆考卷題目會註明「講義未收錄」，不會虛構頁碼。帶有「觀念延伸」標籤的題目包含補充觀念。
- **答案與詳解**：選擇題、計算題自動判分；中文詳解；英文手寫題提供容易抄寫的英文標準答案、關鍵詞、自我評分。
- **練習功能**：章節／題型／難度篩選、關鍵字搜尋、模擬考、收藏、錯題重練、學習進度。
- 所有學習紀錄只存在 **自己瀏覽器的 localStorage**，不會同步給別人、沒有班級排行榜。
- 可選擇本機 PDF 講義，從題目引用快速定位對應頁面（不會上傳檔案到網站）。

## GitHub Pages 部署（最簡單）

1. 登入 GitHub，按 **New repository**，例如取名 `solar-cell-exam-lab`。選 **Public**（要讓同學直接瀏覽）。
2. 把壓縮檔內的 `index.html`、`styles.css`、`app.js`、`questions-data.js`、`favicon.svg`、`README.md` **直接上傳到 repository 最外層（root）**。不要只上傳 ZIP。
3. 到 repository → **Settings** → **Pages**。
4. 在 **Build and deployment** 選 `Deploy from a branch`，Branch 選 `main`、資料夾選 `/(root)`，按 **Save**。
5. 部署成功後網址通常會是：`https://你的GitHub帳號.github.io/solar-cell-exam-lab/`。
6. 把連結傳給同學即可；每位同學的進度獨立存在各自的裝置中。

若建立 repository 名稱為 `你的GitHub帳號.github.io`，網址也可以直接是 `https://你的GitHub帳號.github.io/`。

## 本機開啟

雙擊 `index.html` 即可開啟，大部分瀏覽器可正常執行。建議以 GitHub Pages 開啟，方便跨裝置分享。

## 如何修改題庫

題庫資料來源為 `questions-data.js`，內容是一個 `window.EXAM_BANK = {...}` 物件。

- `type: "mc"`：英文選擇題；`options` 是四個選項、`answer` 是 **0–3** 的正確選項 index。
- `type: "short"`：英文手寫題；`model` 是示範英文答題、`keywords` 是自評提醒。
- `type: "calc"`：計算題；`answer` 是數值答案、`tolerance` 是可接受的絕對誤差、`model` 是計算步驟。
- `pages` 是 PDF 頁碼陣列，**不是原始講義投影片的頁碼**。

修改後記得保持 JavaScript 格式正確、題目 `id` 不重複；首頁的題數由資料自動更新。

## 講義與學術誠信

題目由課堂複習資料與過去試卷資訊重新改寫、擴充，並非教師正式題庫或正式考題預測，內容可能與授課老師的考題不同。請以老師的講義與上課說明為最終依據。

此套件**不包含授課講義 PDF 本體**，避免在公開 GitHub repository 上未經允許重新散布課程檔案；每題頁碼仍完整顯示。若同學有講義，可透過網站內「查看講義頁碼說明」載入本機 PDF 進行跳頁。
