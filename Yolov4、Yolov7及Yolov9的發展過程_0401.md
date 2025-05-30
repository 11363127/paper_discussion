# 11363127 林士傑 2025/4/1
## Yolov4、Yolov7及Yolov9的發展過程
**廖弘源 博士**


# 物件偵測系統

## Some issues need to be considered:
  1. Network architecture
  2. Feature integration method
  3. Detection method
  4. Loss function
  5. Label assignment method
  6. Training method

## 設計的考量及策略
- lightweight  快又準 
- 用於：
  -  Cloud  (如：伺服器)
  -  Local  (如：Notebook)
  -  Edge  (如：手機)
- 調查現存的  State-of-the-art  物件偵測系統

## Variation of Partial Residual Network
-  目標： 
  - 減少計算量與參數
  - 維持連結
  - 增加梯度組合

## Stage-level
- 一個完整的 stage 是從 backbone 組織不同層的資訊進行 feature organization，處理某個任務，例如：
  - Small object detection
  - Large object detection
- 在一個 stage 中的 gradient flow 是具有語意的。

## 要以既存的模型為基礎，或創建新模型
-  Model Scaling 
-  Inference Speed at Edge 
-  Data loss during feedforward 

## Model Scaling 的影響因素
- Possible scaling factors include:
  - Resolution (size of input image)
  - Depth (no. of layers)
  - Width (no. of channels)
  - Stage (no. of feature pyramids)
-  目標：  在網路參數量、計算量、推論速度與準確性之間達到良好平衡。

## Network Architecture Optimization: Extended Efficient Layer Aggregation Networks (E-ELAN)
-  ELAN (正常 v7)： 
  - 控制最短與最長的梯度路徑，讓網絡更有效學習與收斂
  - model scaling 會破壞穩定狀態
-  Extended ELAN (適用大型 v7)： 
  - 透過 expand, shuffle, merge cardinality 等方式，達到：
    - 不破壞梯度路徑
    - 增強網路學習能力

-  YOLOv4 to YOLOv7: 
  - 學習 diverse and consistent features
  -  優化重點： 
    - YOLOv4 to YOLOv7：優化梯度路徑
    - YOLOv9：同時優化 forward path 與 gradient path