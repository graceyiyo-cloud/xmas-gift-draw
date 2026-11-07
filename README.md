# 聖誕樹下抽禮物

單一檔案網頁 `index.html`（HTML＋CSS＋JS 都在裡面，不需建置），直接用瀏覽器開啟即可。
線上版（Claude Artifact，私人）：https://claude.ai/artifact/JNXVvWEfmvbjK3KMG9QZbu

## 已完成的功能（修改美感時請保留）

- 參加人數 2–20 人（預設 10），開始抽之後鎖定，按「重新開始」才可改。
- 抽法：按「抽一份禮物」（樹下禮物輪流亮起再停住），或直接點樹下任一禮物。
- 抽中：禮物發光 → 飛到畫面中央 → 搖晃 → 蓋子彈開、金色亮片 → 卡片升起顯示「抽到 N 號」，有鈴聲（可用鈴鐺按鈕關閉）。
- 號碼不重複；全部抽完顯示「禮物都送出去了，聖誕快樂！」。
- 「抽到自己，這輪重抽」：號碼放回禮物堆、這輪排除它再抽；只剩這一個號碼時停用。
- 「復原上一抽」「重新開始」都要按兩次確認（不能用 alert/confirm）。
- 樹下禮物以 `pileLayout()` 層層疊放、微微歪斜；抽走後其餘禮物滑動重新堆好。
- 進度存在 localStorage（`xmas-gift-draw-v1`），重新整理可接著抽。
- 手機（約 384×824）與電腦版都要正常、不可出現水平捲動；支援 `prefers-reduced-motion`。

## 技術限制（日後要再發布回 Claude Artifact 時需要）

- 外部資源只能用 Google Fonts 的字型；腳本只能從 cdnjs 等白名單 CDN 載入，圖片請用內嵌 SVG／data URI。
- 不可使用 `alert()`／`confirm()`／`prompt()`、`window.print()`。
- 發布到 Artifact 時只需要 `<body>` 內的內容（`<title>`、`<style>`、HTML、`<script>`），外層 `<!doctype>`／`<head>` 會自動加上。
