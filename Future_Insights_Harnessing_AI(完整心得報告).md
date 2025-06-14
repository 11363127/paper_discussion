# 11363127 林士傑 2025/06/03
## Future Insights: Harnessing AI and Social Media for Advanced Event and Epidemic Forecasting(完整心得報告)
**呂昌田 博士**

## 目錄
1. 摘要
2. 監督式與非監督式方法
3. 一對多與一對一模型
4. 多任務學習與特徵互動
5. 模型融合與挑戰
6. 案例研究
7. 結論
8. 參考文獻



## 摘要

- **社群媒體與AI事件預測**  
  結合社群媒體平台與AI模型（如EMBERS），可即時預測社會事件與疫情，透過大規模公開資料分析，實現即時預警。

- **動態查詢擴展（DQE）**  
  動態查詢擴展技術能捕捉新興關鍵字與趨勢，提升事件召回率，並適應社群媒體上的即時變化。

- **即時疫情監控**  
  結合計算流行病學與社群媒體資料，可更快速、精確地追蹤疫情爆發，克服傳統監控方法的延遲。

- **多任務學習（Multitask Learning）**  
  將歷史資料與即時輸入結合，提升跨區域預測準確率。

- **模型融合（Model Fusion）**  
  結合監督式與非監督式學習模型，有效處理資料稀疏、區域異質性等問題，在低資料環境下也能產生更可靠的預測。

---

## 監督式與非監督式方法

### 監督式方法（Supervised Methods）

- **優點**：可充分利用歷史事件知識，擁有大型訓練集，特徵（如關鍵字）固定。
- **缺點**：受限於歷史關鍵字，無法即時反映新興主題。
- **實例**：LASSO、SVM等模型，從推文語料中萃取固定關鍵字，進行事件分類與預測。

### 非監督式方法（Unsupervised Methods）

- **優點**：可即時捕捉動態關鍵字，反映社群媒體新興事件。
- **缺點**：未能充分利用歷史事件知識。
- **實例**：DQE、EDCoW等方法，根據種子查詢自動擴展事件相關新興關鍵字，提升即時性。


---

## 一對多與一對一模型

### 一對多模型（One-for-all model）

- **說明**：所有地點共用一個模型。
- **優點**：數據量充足，模型訓練穩定。
- **缺點**：忽略各城市獨特性（如人口、規模），同樣數量推文在不同城市意義不同。


### 一對一模型（One-to-one model）

- **說明**：每個地點建立一個專屬模型。
- **優點**：能考慮每個城市的獨特特性。
- **缺點**：小城市資料不足，且忽略地點間的相關性。

---

## 多任務學習與特徵互動

- **每個地點視為一個任務**，同時利用靜態（如地理、人口）與動態（如即時推文）特徵。
- **特徵選擇具互動性**：不同地點間的特徵會互相影響，透過正則化特徵權重，提升整體預測表現。

## 模型融合與挑戰

- **監督式+非監督式模型結合**：  
  - 監督式模型充分利用歷史數據
  - 非監督式模型能捕捉動態關鍵字
  - 結合後兼具兩者優勢

- **一對一+一對多模型結合**：  
  - 一對一模型考慮地點專屬特性
  - 一對多模型確保數據量充足
  - 結合後同時兼顧個別性與泛用性

---

## 案例研究（Case Study）

- 展示多種模型（CMTFL-II、LASSO、rMTFL）在不同城市事件預測的成功案例。
- 成功捕捉小城市事件與動態關鍵字（如“Misiones”）。
- 與實際報導事件比對，證明模型在不同地點、不同事件類型下的有效性。

---

## 結論

本次講座展示了結合社群媒體資料與AI技術，如何有效進行時空事件與疫情預測。透過監督式與非監督式、多任務學習及模型融合，能克服資料稀疏與異質性，提升預測的準確性與即時性。

## 參考文獻
L. Zhao*, F. Chen*, C.T. Lu, R. Ramakrishnan, "Dynamic Theme Tracking in Twitter" Proceedings of the IEEE International Conference on Big Data (IEEE BigData), pp. 561-570, 2015.

L. Zhao*, J. Chen, F. Chen, W. Wang, C.T. Lu, R. Ramakrishnan, "SimNest: Social Media Nested Epidemic Simulation via Online Semi-supervised Deep Learning" Proceedings of the IEEE International Conference on Data Mining (IEEE ICDM), 2015, Atlantic City, NJ. (DQE + Simulation)