# RFM-Analysis

# 🎯 RFM 客戶價值分群與多維視覺化專案

本專案透過 **RFM 模型**（**R**ecency 近期消費天數、**F**requency 消費頻率、**M**onetary 消費金額），搭配 **K-Means 機器學習演算法**，將海量的客戶交易行為轉化為精準的商業分群與客製化行銷策略。


## 💡 專案核心邏輯與 10 大執行步驟

1. **資料載入與正規化（Q1 - Q2）**：讀取原始資料 `RFM_data` 後進行 Min-Max 正規化處理（命名為 `nrfm`），消除金額與頻率因數值量級差異產生的權重偏誤。
2. **最佳分群與模型訓練（Q3 - Q5）**：利用**手肘法（Elbow Chart）**觀察轉折點以選定最佳分群數，接著執行 **K-Means ($K=4$)** 聚類分析，並將預測出之 `Cluster` 標籤貼回原始資料 `df`。
3. **商業語意轉譯（Q7）**：將抽象數字轉化為具業務意義的客戶類群（`Group`）：
   * **Missing (Cluster 0)**：高流失風險/待喚醒客戶
   * **High (Cluster 1)**：高貢獻度的 VIP 核心客戶
   * **Low (Cluster 2)**：低頻次與低金額的沉寂客戶
   * **Medium (Cluster 3)**：具備消費潛力的穩定客戶
4. **多維視覺化與成果匯出（Q6, Q8 - Q10）**：運用 **Pair Plot 成對散布圖**交叉比對 R、F、M 的客群分佈，並輸出去背透明圖檔 `RFM_Pairplot.png` 與完整分群資料集 `RFM_result.csv`。


## 🚀 商業應用與延伸價值

* **精準行銷策略**：對 High 提供 VIP 獨家權益，對 Missing 發送召回折扣，對 Medium 進行交叉銷售，達成行銷資源效益最大化。 
* **動態流失預警**：持續追蹤顧客在不同時間點的分群轉移（如 High 降級至 Missing），在客戶離去前即時啟動挽留機制。
  
## ✨ 指令參考
Q1：請載入 RFM_data.csv

Q2：請將 df 執行正規化處理，並命名為 nrfm

Q3：請根據 nrfm 繪製 Elbow Chart，以幫助判斷執行 K-means 的最佳分組數

Q4：請以 nrfm 執行 k-maans 分群，群數為 4

Q5：請將分組標籤 Cluster 回貼至原始資料 df

Q6：請以 df 的 R、F、M欄位繪製 "成對散布圖 Pair Plot"，並以 Cluster 標籤分組

Q7：請在 df 新增一欄，標頭為 Group，內容對應 Cluster：0>Missing，1>High，2>Low，3>Medium

Q8：請以 df 之 R、F、M 繪製成對散布圖，以 Group 標籤分組

Q9：請將此圖以透明圖格式下載，檔名為 RFM_Pairplot.png

Q10：請將 df 以 csv 格式下載，檔名為 RFM_result.csv
