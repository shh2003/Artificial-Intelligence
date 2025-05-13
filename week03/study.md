코렙 - 구글 드라이브에 업로드 

header=None 컬럼명 데이터가 필요없을떄



## 🆚 넘파이 배열 vs 판다스 데이터프레임

### 🎯 정리표

| 구분                         | 넘파이 배열 (numpy array)              | 판다스 데이터프레임 (pandas DataFrame)      |
|------------------------------|----------------------------------------|---------------------------------------------|
| **형태**                      | **n차원 배열** (matrix 형태)            | **표 형태 (엑셀 같은 2차원 테이블)**         |
| **기반**                      | 수학/과학 연산용 (고속 수치 계산용)     | 데이터 분석/가공 용도                       |
| **컬럼명 / 인덱스**            | 없음 (숫자 인덱스만 존재)              | 있음 (컬럼명, 행 인덱스 둘 다 존재)         |
| **데이터 타입**                | 한 배열 안에 **단일 타입**만 가능        | 여러 컬럼에 **혼합 타입** 사용 가능 (숫자 + 문자열 등) |
| **주요 사용 예**               | 선형대수, 배열 연산, 벡터/행렬 계산     | 데이터 분석, 통계 처리, 데이터 시각화 준비 |
| **메서드/기능**                | 벡터 연산, 행렬 연산, 브로드캐스팅 등   | 그룹화, 필터링, 조인, 결합, 집계 등 다양한 데이터 조작 |
| **연동**                      | pandas, sklearn, tensorflow 등에서 사용 | 머신러닝, 데이터 분석에서 직접 사용          |

### ✨ 쉽게 기억하는 팁:
- **넘파이 배열**: "숫자 계산에 특화된 n차원 배열"  
- **데이터프레임**: "엑셀처럼 컬럼명과 인덱스를 가진 표 형태 데이터"
---<br><br><br><br>

## 📌 분류 vs 회귀

### 🎯 정리표

| 구분        | 분류 (Classification)                  | 회귀 (Regression)                |
|-------------|----------------------------------------|----------------------------------|
| **예측 결과**   | **카테고리(클래스)**                   | **숫자(연속적인 수치)**            |
| **문제 유형**   | 스팸 여부, 질병 유무, 고객 이탈 등       | 가격 예측, 기온 예측, 수요량 예측 등 |
| **출력 예시**   | 'Yes' / 'No', `0` / `1` / `2` 등       | 23.5, 150.0, -4.7 등              |
| **사용 모델**   | KNN, Random Forest, SVM 등              | 선형 회귀, SVR, Gradient Boosting |

### ✨ 쉽게 기억하는 팁:
- **분류**: "어느 그룹이야?"  
- **회귀**: "얼마야?"
---
<br><br><br><br>


## 🔄 LabelEncoder vs One-Hot Encoding

### 🎯 정리표

| 구분                  | LabelEncoder                                       | One-Hot Encoding                                |
|-----------------------|----------------------------------------------------|-------------------------------------------------|
| **목적**              | 순서가 있는 범주를 **숫자 하나**로 변환             | 순서 없는 범주를 **0/1로 나눈 여러 컬럼**으로 변환 |
| **출력 예시**          | `['low', 'medium', 'high'] → [0, 1, 2]`            | `['Red', 'Blue', 'Green'] → [1,0,0], [0,1,0]`   |
| **사용 상황**          | 순서/등급/단계가 중요한 데이터 (ex: 등급, 학년)    | 순서 없는 카테고리 데이터 (ex: 도시, 직업, 성별) |
| **특징**              | 하나의 컬럼만 생성됨                               | 여러 개의 컬럼으로 확장됨                        |
| **주의할 점**          | 순서를 학습할 가능성 있음                           | 차원이 증가할 수 있음 (컬럼 수 늘어남)           |

### ✨ 쉽게 기억하는 팁:
- **LabelEncoder**: "1, 2, 3처럼 번호를 매김"  
- **One-Hot**: "0/1로 나누어 독립적인 컬럼으로 만듦"

---
<br><br><br><br>

# 🧹 데이터 전처리 체크리스트
## 🔍 1단계: 결측치 처리 (Missing Values)

### ☐ 결측치 확인
```python
df.isnull().sum()
```

### ☐ 결측치 처리 전략
- ☐ **평균/중앙값/최빈값 대체 (SimpleImputer)**
- ☐ **특정 값으로 채우기 (ex: 0 또는 'Unknown')**
- ☐ **행 제거 (dropna)**

```python
mean_age = df['Age'].mean()

# age 컬럼의 결측치를 평균값으로 채우기

df['Age'] = df['Age'].fillna(mean_age)
```

---

## 🔍 2단계: 이상치 처리 (Outliers)

### ☐ IQR 또는 Z-score를 이용한 이상치 탐지
```python
import scipy.stats as stats

z_scores = stats.zscore(df)
print((abs(z_scores) > 3).sum())
```

### ☐ 이상치 처리 전략
- ☐ **제거 (drop)**
- ☐ **클리핑 (clip)**
- ☐ **값 대체 (ex: 상한/하한 값으로 대체)**

---

## 🔍 3단계: 데이터 스케일링 (Scaling)

### ☐ 스케일링 필요 여부 판단
- ☐ 모델이 거리 기반인지 확인 (ex: KNN, SVM, 선형모델 등은 필요)

### ☐ 스케일링 적용
```python
scaler = StandardScaler()
X_train = scaler.fit_transform(X_train)
X_test = scaler.transform(X_test)
```

---

## 🔍 4단계: 인코딩 (Categorical Encoding)

### ☐ 범주형 변수 확인
```python
df.select_dtypes(include='object').columns
```

### ☐ 인코딩 적용
- ☐ **One-Hot Encoding**
- ☐ **Label Encoding**
- ☐ **Target Encoding** (필요 시)

```python
# LabelEncoder 초기화

label_encoder = LabelEncoder()

# 특정 컬럼만 인코딩

columns_to_encode = ['Sex']  # 인코딩할 컬럼 리스트

for column in columns_to_encode:

    df[column] = label_encoder.fit_transform(df[column])

display(df)
```

---

## 🔍 5단계: 불필요한 컬럼 제거
- ☐ 식별자 컬럼(ID 등) 삭제
- ☐ 타겟 변수 관련 컬럼 삭제 (데이터 누수 방지)
```python
df = df.drop(columns=['ID', 'Outcome'])
```

---

## ✨ 6단계: 최종 확인
- ☐ 데이터셋 shape 확인 (`df.shape`)
- ☐ 데이터 타입 확인 (`df.dtypes`)
- ☐ 이상치/결측치 처리 여부 재확인 (`df.describe()`, `df.isnull().sum()`)

---
<br><br><br><br>

# 📝 피처 제거 & 전처리 체크리스트

## 🔍 1단계: 목표 정의
- 예측할 타겟 변수(Target): `ex) BMI`
- 모델링 목적: `ex) BMI 수치를 예측하여 건강 리스크 분석`

---

## ✅ 2단계: 제거할 컬럼 체크리스트

### ☐ 타겟 변수와 직접적인 관계가 있는 컬럼
- Outcome 등 타겟 변수(BMI)와 **인과관계가 있는 컬럼**은 제거  
  ➡ 데이터 누수(Leakage) 방지

### ☐ 식별자(ID) 컬럼
- ID, 이름, 코드 등 **식별 목적으로만 사용되는 컬럼** 제거

### ☐ 상관관계가 높은 컬럼
- **상관계수 0.9 이상**의 컬럼들 중 하나 제거

```python
#상관 관계 행렬
# 0.3 이상인 경우 상관관계가 있고, 0.7이상이면 아주 높음

df_corr=df.corr()

#히트맵
plt.figure(figsize=(10,10))
sns.set(font_scale=0.8)
sns.heatmap(df_corr, annot=True, cbar=False)
plt.show()

```
### ☐ 결측치 비율이 높은 컬럼
- 결측치가 50% 이상인 컬럼 제거 고려
➡ 필수 컬럼일 경우 평균/중앙값 대체(imputation) 또는 모델링에서 제외

### ☐ 중요도가 낮은 컬럼
- Feature Importance가 매우 낮은 컬럼 제거 가능
```
# 랜덤포레스트로 중요도 확인 예시
from sklearn.ensemble import RandomForestRegressor

model = RandomForestRegressor()
model.fit(X_train, y_train)
print(model.feature_importances_)
```
---
<br><br><br><br>




