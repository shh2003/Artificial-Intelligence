```
//age 컬럼의 평균값 계산
mean_age = df['Age'].mean()

//결측치(NaN)를 평균값으로 대체
df['Age'] = df['Age'].fillna(mean_age)
```
## age 값을 평균으로 두는 이유
  1. 데이터 손실 최소화
      age 값이 결측치라고 해서 해당 행(row)을 삭제하면 전체 데이터의 양이 줄어들어 분석에 불리할 수 있습니다. 평균으로 대체하면 데이터를 유지하면서 결측치를 처리할 수 있음.
      
  3. 평균은 대표값 
      평균은 해당 컬럼의 중심 경향을 나타내는 값으로, age 컬럼의 전반적인 경향을 잘 대변한다고 간주하기 때문에 무난하게 대체할 수 있음.
---


```표준화 (Scaling)
scaler = StandardScaler()
X_train = scaler.fit_transform(X_train)
X_test = scaler.transform(X_test)
```

## 표준화를 하는 이유
  - 데이터셋의 feature(변수)들이 서로 다른 단위를 가지고 있을 수 있음.
   
  - 따라서 거리 기반 모델(예: KNN, SVM, 선형회귀 등)은 큰 값 범위를 가진 변수에 더 큰 가중치를 부여하게 됨.
    -> 표준화는 모든 feature를 평균 0, 표준편차 1로 변환하여 동일한 스케일로 맞춤.

---
## 혼동 행렬(confusion matrix)이란?
|                      | **실제 Positive (1)** | **실제 Negative (0)** |
|----------------------|-----------------------|-----------------------|
| **예측 Positive (1)** | True Positive (TP)    | False Positive (FP)   |
| **예측 Negative (0)** | False Negative (FN)   | True Negative (TN)    |

<의미>  
- TP (True Positive): 실제 1인데 모델도 1이라고 맞춤  
- TN (True Negative): 실제 0인데 모델도 0이라고 맞춤  
- FP (False Positive): 실제는 0인데 모델이 1이라고 틀림 (False Alarm)  
- FN (False Negative): 실제는 1인데 모델이 0이라고 틀림 (놓침)

