# Music Player · YouTube Playlist v1.1.1 — GitHub Pages 版

此版本以使用者提供的 `v1.1.0 完整整合版` 為基礎，**保留原本的音樂庫、YouTube 網址／播放清單匯入、小卡片開關、播放佇列與 IndexedDB 儲存功能**，改為可以直接使用 GitHub Pages 發布的靜態網站。

## GitHub 上傳與啟用

1. 在 GitHub 建立公開儲存庫，例如 `MusicPlayer-YouTube`（既有儲存庫亦可）。
2. 解壓縮 ZIP，將 `index.html`、`README.md`、`LICENSE`、`.nojekyll` **放在儲存庫根目錄**；請不要把外層資料夾整個當成根目錄上傳。
3. 開啟儲存庫 **Settings → Pages → Build and deployment**。
4. `Source` 選 **Deploy from a branch**，`Branch` 選 `main`、資料夾選 **/(root)**，按 **Save**。
5. 使用 GitHub Pages 顯示的網址開啟，例如 `https://<username>.github.io/MusicPlayer-YouTube/`。

**不需要安裝 Node.js、不需要執行 BAT、不需要 Server，也不需要 GitHub Actions。**

## 操作

1. 點右下方 **YouTube Music**，打開播放器卡片。
2. 點選 **Add YouTube Link**（首次使用）或 `+ → Add YouTube Link / Playlist`（已建立音樂庫）。
3. 貼上公開的 YouTube 影片或播放清單網址。
4. 開始播放後，按右上角 `×` 關閉卡片，再從右下角按鈕重新開啟。關閉卡片不會主動執行 pause/stop，也不會刪除播放器實例。

## 注意事項

- GitHub Pages 必須以 **https 網頁網址**開啟，請勿以電腦的 `file:///` 方式測試，部分瀏覽器的 IndexedDB 可能無法正常初始化。
- 歌曲／播放清單存放在**各瀏覽器、各網站來源（origin）的 IndexedDB**。從原本的 `http://127.0.0.1:8765` 換成 GitHub Pages 後，原本的音樂庫**不會自動搬過去**，須重新匯入。這不是程式遺失資料。
- YouTube 播放與清單匯入需連線至 YouTube；只有**公開且允許嵌入**的內容才有機會正常載入。私人、受地區限制、禁止嵌入或 YouTube 未公開完整清單的項目可能失敗。
- 此版沿用原版的隱藏 YouTube iframe 音樂模式。**關閉卡片時程式不主動停止播放**，但 YouTube 的嵌入政策、瀏覽器自動播放／背景播放限制，可能使播放中斷，無法保證在所有裝置持續播放。
- 此網站是**獨立播放測試頁**，沒有改動或直接整合進 TruckSimulator。

## 改版範圍

- 移除發布時對 `serve-static.js` 和 `.bat` 啟動器的依賴。
- 移除原 ZIP 重複的巢狀資料夾，改為 GitHub Pages 可識別的根目錄 `index.html`。
- YouTube iframe 使用部署網站的 `location.origin`，支援 GitHub Pages 自訂路徑。
- 保留原播放器功能與樣式，未重做介面或資料儲存架構。

## 授權

原始播放器基於 `kirillsaidov/music-player`，授權詳見 `LICENSE`。
