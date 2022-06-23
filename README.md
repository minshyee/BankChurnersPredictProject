# BankChurnersPredictProject
"줄기는 이탈할 고객은 누구이고, 그들을 잡기 위해서는 어떤 전략을 세워야 하는가?"
## Data
![image](https://user-images.githubusercontent.com/50479962/175192503-c16317ce-8f03-49aa-907e-08412e10db2e.png)
- 불균형한 데이터 SMOTE 알고리즘 사용 
- MinMaxScaler를 이용한 정규화 진행 -> 기준값 통일
## Hypothesis
- Revolving 잔액에 따른 해/유지 고객 차이 
  - 유지고객은 보유 잔액 존재
  
    <img src="https://user-images.githubusercontent.com/50479962/175193069-e68c7f7c-2ff1-4cc3-89a5-ce0e5552827b.png" width=400, height=200/>

- 소득 수준에 따른 카드 등급의 차이 존재
  - 차이 없음
  
     <img src="https://user-images.githubusercontent.com/50479962/175192905-7e06594b-3fe8-4f24-986e-cc23f8f8cc8a.png" width=400, height=200/>
## Model
- 이탈 고객 예측 Model 실험
- Target Encoder 사용

|--|Base Model|Decision Tree|Random Forest|XGBoost with PCA|XGBoost|
|---|---|---|---|---|---|
|PCA| X | O | O | O | X |
|recall|0.42|0.83|0.88|0.91|0.98|
|F1score|0.46|0.79|0.86|0.88|0.98|

- Shap Library : Feature Importance
![image](https://user-images.githubusercontent.com/50479962/175193806-9d1f722d-8f60-427b-93dc-9f98fb6451fd.png)

## Limit
- 다차원으로 인한 Overfitting 가능성 농후
