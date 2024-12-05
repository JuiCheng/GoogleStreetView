# ArcGIS Map with Google Street View and Arrow

這個專案展示了如何將 ArcGIS 地圖與 Google 街景視圖整合，並在地圖和街景視圖上顯示一個箭頭標記，該箭頭會根據街景的角度和位置動態更新。

## 功能
- **ArcGIS 地圖**：使用 ArcGIS API 顯示地圖，並在地圖上標記特定位置。
- **Google 街景**：顯示 Google 街景，並根據街景的視角改變顯示在地圖上的箭頭。
- **動態箭頭**：箭頭會隨著 Google 街景的旋轉而旋轉，並根據街景的實際位置更新。

## 使用說明

1. **下載並準備專案**
   - 將專案檔案放置在一個資料夾中。
   - 確保 `arrow.png` 圖片放在與 HTML 檔案相同的目錄中。這個圖片將作為箭頭的圖示。

2. **設定 Google API 金鑰**
   - 開啟 [Google Cloud Console](https://console.cloud.google.com/)，並取得您的 Google Maps JavaScript API 金鑰。
   - 在 HTML 檔案中找到以下代碼：
     ```html
     <script src="https://maps.googleapis.com/maps/api/js?key=YourKey&callback=initStreetView" async defer></script>
     ```
   - 替換 `YourKey` 為您取得的 API 金鑰。

3. **開啟專案**
   - 打開 HTML 檔案在瀏覽器中，您應該能看到一個包含 ArcGIS 地圖和 Google 街景的介面。
   - 點擊地圖上的任意位置，街景將會跳轉至該位置，並且箭頭會根據街景角度自動旋轉。

## 技術細節

- **ArcGIS API**: 使用了 ArcGIS JavaScript API 來載入並顯示地圖。
  - 使用 `esri/Map` 和 `esri/views/MapView` 來建立地圖視圖。
  - 使用 `esri/Graphic` 和 `esri/symbols/PictureMarkerSymbol` 在地圖上加入箭頭標記。

- **Google Maps API**: 使用 Google Maps JavaScript API 顯示街景。
  - 使用 `google.maps.StreetViewPanorama` 來建立街景視圖。
  - 當街景視角（heading）改變時，會更新箭頭的旋轉角度。

- **箭頭**: 箭頭標記是用圖片顯示的，並且會隨著街景的角度變動而旋轉，與 Google 街景的視角同步。

## 技術需求

- 瀏覽器：現代瀏覽器（如 Chrome、Firefox、Safari）均可支援。
- 需要有效的 Google Maps API 金鑰，並且需要啟用 Google Maps JavaScript API。

## 問題與解決
- **API 金鑰錯誤**：如果 API 金鑰無效，將無法顯示街景或地圖。請確保您已正確設置並啟用 API。
- **箭頭顯示異常**：如果箭頭顯示不正確，檢查圖片路徑是否正確，並確保 `arrow.png` 圖片存在於正確的資料夾中。

## 授權

這個專案是開源的，您可以自由使用、修改和分享，但請遵守相應的授權條款。

