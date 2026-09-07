# 臺北跨時空 PWA v2

這版已調整：

- PWA 名稱與桌面 ICON 下方標題統一為「臺北跨時空」。
- ICON 改成不透明滿版底色，不再出現白色／透明方塊背景。
- PWA 啟動畫面背景色改為與 ICON 接近的金棕色。
- AR 的「送出答案」移到白色辨識框正下方，並加大點擊區域。
- Service Worker 快取版本升為 v2，避免舊 ICON / manifest 被快取。
- 保留原本 720p ideal 的 AR 相機偏好設定。

## 部署

把這個資料夾中的檔案放到網站根目錄，並保留原站的 `data.txt`、`background/`、`images/`、`videos/` 等素材資料夾。網站需使用 HTTPS。

## 已安裝過舊版 PWA 的手機

手機桌面上已存在舊版 PWA 時，系統可能不會立刻刷新名稱與 ICON。請先刪除舊的主畫面捷徑 / PWA，再重新用 Safari 或 Chrome 加到主畫面，才能看到新的「臺北跨時空」名稱與無白底 ICON。


## v3 更新
- 掃描白框下方改為兩顆直式按鈕：上方「送出答案」、下方「回上一頁」。
- 兩顆按鈕改為透明底、白框、白字，並下移，方便點擊。
- 重新輸出所有 PWA / Apple Touch / Maskable icons，改成無白底的滿版金棕底版本。
- Service Worker 快取版本升級到 v3。

> 若手機已安裝舊版 PWA，請先刪除主畫面上的舊 App，再重新加入主畫面，否則系統可能繼續沿用舊圖示。


## v4 更新
- PWA / 啟動畫面背景改為純黑色。
- 啟動畫面改用 `icons/launch-icon.png`：ICON 四角為真正透明，不再出現白色矩形底。
- `manifest.webmanifest` 的 `background_color` 與 `theme_color` 都改為 `#000000`。
- 影片按鈕會先檢查 `./videos/qN.mp4` 是否真的存在；檔案不存在時不會顯示「老照片動起來」。
- Service Worker 快取版本升級為 v4。

> 若手機已安裝過舊版 PWA，請先刪除主畫面上的舊 App，再重新加入主畫面，避免沿用舊 ICON / splash 快取。


## v5 ICON 修正
- 所有實際使用的 PWA ICON 都保留原圖 Alpha 透明，完全不補黑底、白底或金色方形底。
- Manifest 已移除 `maskable` ICON，避免 Android 把黑色底層當成自適應圖示背景。
- Android 主畫面改用透明的 `icon-192-v5.png` / `icon-512-v5.png`。
- 啟動頁整個手機背景仍為黑色 (`background_color: #000000`)，中間 ICON 自身背景保持透明。
- ICON 檔名改成 v5，避免手機/Chrome 繼續讀到舊版圖示快取。
- `videos/qN.mp4` 不存在時，不會顯示「老照片動起來」。

重要：Android 已安裝的舊 PWA 圖示不會即時替換。請先解除安裝/移除舊的「臺北跨時空」，再從更新後的網站重新安裝。


## v6 更新
- AR 辨識到「不同照片」時不再立即顯示「可惜！不是這張」；只有使用者按下「送出答案」後才判定對錯。
- targetFound 現在只記錄辨識結果並顯示「已辨識到照片，請按送出答案確認」。
- 移除網頁自己做的第二層 launchSplash，因此 Android 啟動時不再先出系統小 ICON、再跳自訂大 ICON。
- 保留 manifest 黑色 background/theme，讓系統原生 PWA splash 只有一層。
- ICON 圖檔沿用 v5 正確透明版本，但改用 v6 檔名以避開手機/Chrome 的舊圖示快取。
- 影片存在檢查邏輯保留：videos/qN.mp4 不存在時，不顯示「老照片動起來」。

> Android 已安裝舊版時，請先移除主畫面的舊 PWA，再用 v6 網站重新安裝，才能確保啟動畫面與 ICON 使用新 manifest。
