# Notion 相簿（GitHub Pages 版）

你有兩種做法：
1) **Albumizr 包裝**（保留 Albumizr 優點，但無法保證內頁黑底改成透明）  
2) **自架透明相簿（PhotoSwipe）**（完全自訂外觀，透明背景，無廣告）

---

## A. Albumizr 包裝（albumizr-wrapper.html）

1. 把本檔案放到 GitHub 儲存庫根目錄（例如 `albumizr-wrapper.html`）。
2. 開啟 Albumizr，取得「嵌入 iframe」的 `src` 連結（不是整段 HTML，僅 `src="..."` 的網址）。
3. 造訪：`https://你的使用者名.github.io/你的儲存庫/albumizr-wrapper.html?src=把上面網址做 URL 編碼後貼上`
   - 可用網站進行 URL encode，或在瀏覽器自動編碼。
4. 在 Notion 用 `/embed` 貼上第 3 步的完整網址。

> 限制：如果 Albumizr 內頁硬是黑背景，父頁無法強制改透明。此包裝可確保父頁本身透明與 RWD 友善。

---

## B. 透明自架相簿（photoswipe-gallery.html）

1. 建立資料夾 `images/`，放入你的縮圖與大圖，例如：
   - `images/thumb-1.jpg`（小圖，用於格子）
   - `images/large-1.jpg`（大圖，點擊後顯示）
2. 打開 `photoswipe-gallery.html`，複製 `<a>...</a>` 區塊，替換成你的檔名與尺寸：
   ```html
   <a href="images/large-1.jpg" data-pswp-width="1600" data-pswp-height="1067">
     <img src="images/thumb-1.jpg" alt="描述">
   </a>
   ```
   `data-pswp-width/height` 請填大圖實際像素，光箱才能正確比例。
3. 推送到 GitHub。到 **Settings → Pages** 啟用 GitHub Pages（Source 選擇 `Deploy from a branch`，分支 `main`，資料夾 `/root`）。
4. 取得 Pages 網址，例如 `https://你的使用者名.github.io/你的儲存庫/photoswipe-gallery.html`。
5. 在 Notion 用 `/embed` 貼上該網址即可。背景預設透明，會與 Notion 融合。

---

## 小技巧
- 想要滿版高度：把 Notion 的嵌入區塊拉高即可。
- 想要四邊無陰影：把 `.grid a` 的 `box-shadow` 刪除。
- 需要標題或描述：在 `<a>` 裡加入 `title="說明"`，PhotoSwipe 會顯示。

