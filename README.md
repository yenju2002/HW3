Q:Extract Radiomics features using tools like pyradiomics and use the features to predict the age of the subjects.
![image](https://github.com/user-attachments/assets/057a4676-06ba-485d-8286-7b1dc58278be)

參考於https://github.com/AIM-Harvard/pyradiomics/releases 

流程:

[開始]

    v
    
[1. 特徵提取]

    |--- 加載 MRI 文件
    
    |--- 加載 IXI.csv
    
    |--- 遍歷每個 MRI 文件
    
    |       |- 提取 PID, 年齡
    
    |       |- 匹配分割掩碼文件
    
    |       |- 提取放射組學特徵
    
    |       |- 保存特徵和對應年齡
    
    v

[保存為 radiomics_features.csv]

    v

[2. 隨機森林回歸]
 
    |--- 加載 radiomics_features.csv
    
    |--- 預處理 (去除 PID, 標準化, 填充缺失值)
    
    |--- 分割數據集 (80% 訓練集, 20% 測試集)
    
    |--- 訓練隨機森林回歸模型
    
    |--- 預測測試數據
    
    |       |- 篩選預測值 > 100 的樣本
    
    |       |- 評估性能 (MSE, R²)
    
    |       |- 可視化結果 (實際值 vs 預測值, 誤差分佈)
    
    v

[3. 線性回歸]

    |--- 加載 radiomics_features.csv
    
    |--- 預處理 (去除 PID 和年齡, 標準化)
    
    |--- 分割數據集 (80% 訓練集, 20% 測試集)
    
    |--- 訓練線性回歸模型
    
    |--- 預測測試數據
    
    |       |- 篩選預測值 > 100 的樣本
    
    |       |- 評估性能 (MSE, R²)
    
    |       |- 可視化結果 (實際值 vs 預測值, 誤差分佈)
    
    v

[結束]


