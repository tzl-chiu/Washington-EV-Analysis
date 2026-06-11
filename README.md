# 華盛頓州電動車 (EV) 用戶行為分析計畫

本計畫利用華盛頓州政府公開的電動車註冊數據（包含 28 萬筆以上的車輛紀錄），旨在分析電動車的市場分布趨勢。本專案透過資料清洗、視覺化分析與機器學習模型（K-Means），探討電動車的普及狀況與規格特徵，並為區域性充電設施的策略性佈建提供決策參考。
簡報連結 : https://canva.link/yhwnoiy4a9hppb5
---

## 專案內容與技術棧
*   **資料獲取**：分析來自 Kaggle 的華盛頓州電動車人口數據。
*   **資料清洗**：處理缺失值、排除非華盛頓州樣本、進行欄位型態轉換。
*   **探索性分析 (EDA)**：品牌市佔率分析、地理空間分佈、車型偏好分析。
*   **機器學習建模**：利用 Scikit-learn 進行 K-Means 分群，分析「續航里程」與「生產年份」的關聯。

## 資料欄位說明
專案處理的數據集包含 16 個欄位，主要分為四大類：
1.  **基礎識別與地理資訊**： `County`, `City`, `State`, `Postal Code`, `Vehicle Location`。
2.  **車輛產品資訊**：`Model Year`, `Make`, `Model`, `Electric Vehicle Type。
3.  **技術規格與政策**：`Clean Alternative Fuel Vehicle (CAFV) Eligibility`, `Electric Range`, `Base MSRP`。
4.  **行政與電力資訊**：`Legislative District`, `DOL Vehicle ID`, `Electric Utility`, `2020 Census Tract`。

---

## 資料清洗流程
為了確保分析的精確性，執行了以下清洗步驟：
*   **範圍鎖定**：過濾掉非 WA (華盛頓州) 的資料，因樣本數極低且非研究範圍。
*   **缺失值處理**：
    *   刪除關鍵欄位（`County`, `City`, `Postal Code`, `Electric Range`）含有缺失值的紀錄。
    *   將 `Legislative District` 缺失值補上 `Unknown`，並刪除 `Vehicle Location` 的少量缺失值以利繪圖。
*   **型態轉換**：將 `Postal Code` 與 `Legislative District` 轉換為字串類型。

---

## 主要分析洞察
1.  **市場佔比**：Tesla 在華盛頓州具有絕對的品牌支配力，特斯拉在該州佔比為 40.86%。
2.  **區域熱點**：King County 為全州電動車數量最多之區域，建議優先在此進行基礎設施佈建。
3.  **品牌與型號**：除了 Tesla 穩居龍頭外，CHEVROLET 與 NISSAN 亦佔據市場前段班，而 Model Y 為熱門型號首選。

---

## 執行環境
*   **語言**: Python
*   **資料處理**: Pandas, NumPy
*   **視覺化**: Matplotlib, Seaborn
*   **機器學習**: Scikit-learn (KMeans)

---

### 使用方式
1.  確保已安裝必要的依賴套件：
```bash
    pip install pandas numpy seaborn matplotlib scikit-learn
    ```
2.  將 `Electric_Vehicle_Population_Data.csv` 放置於專案根目錄下。
3.  執行 `EV_Analysis.ipynb` 即可查看完整分析結果。

---

### 專案作者
Tz Chiou
