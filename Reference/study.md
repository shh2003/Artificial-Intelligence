1. 인공지능에서 지능에 해당하는 기능
지능에 해당하는 기능은 학습(Learning), 추론(Reasoning), 문제 해결(Problem Solving), 언어 이해(Natural Language Understanding), 시각 인식(Visual Perception), 행동 제어(Control) 등이 있음.

2. 인공지능의 3가지 종류

지도학습(Supervised Learning): 입력과 정답(label)이 있는 데이터를 기반으로 학습. 예: 이메일 스팸 분류.

비지도학습(Unsupervised Learning): 정답 없이 입력 데이터의 패턴을 찾음. 예: 고객 군집화.

강화학습(Reinforcement Learning): 보상에 따라 최적의 행동을 학습. 예: 게임 플레이, 로봇 제어.

3. 전통적인 프로그래밍과 인공지능 프로그램 차이점
전통: 규칙을 사람이 명시 → 결과
AI: 입력과 결과 데이터를 기반으로 규칙(모델)을 기계가 학습

4. 딥러닝과 머신러닝의 차이점

머신러닝: 특징 추출 + 모델 학습

딥러닝: 특징 추출도 모델이 자동으로 수행 (예: CNN, RNN)

5. Classification vs. Regression

Classification: 범주형 출력 (예: 스팸/비스팸)

Regression: 연속형 출력 (예: 집값 예측)

6. 차원의 저주(Curse of Dimensionality)
특징 수가 많아질수록 데이터가 희소해지고 모델 학습이 어려워지는 현상

7. 차원 축소(Dimensionality Reduction)의 필요성
과적합 방지, 계산 비용 감소, 시각화 용이, 노이즈 제거

8. Ridge vs. Lasso

공통점: 과적합 방지를 위한 규제 기법

차이점:

Ridge: L2 규제 → 모든 변수 유지

Lasso: L1 규제 → 불필요한 변수 제거 (특성 선택 효과)

둘 다 feature scaling 필요

9. Overfitting vs. Underfitting

Overfitting: 학습 데이터에 과도하게 적합 → 일반화 성능 저하

Underfitting: 너무 단순한 모델 → 학습조차 제대로 못함

10. Feature Engineering vs. Feature Selection

Engineering: 도메인 지식으로 새로운 특성 생성

Selection: 성능에 기여하지 않는 특성 제거

11. 전처리(Preprocessing)
목적: 품질 향상 및 학습 성능 향상
방법: 결측치 처리, 이상치 제거, 정규화, 인코딩 등

12. EDA (탐색적 데이터 분석)
데이터의 분포, 상관관계, 이상치 등을 시각화나 통계로 분석

13. 회귀에서 절편과 기울기

절편: y축과 만나는 값

기울기: 독립변수가 1 증가할 때 종속변수의 변화

딥러닝의 가중치(weight)와 편향(bias)에 대응됨

14. Activation Function
비선형성을 부여해 학습 가능하게 함

Sigmoid: 0~1 출력, 이진 분류에 적합

Softmax: 다중 클래스 분류

ReLU: 딥러닝에서 가장 많이 사용

15. Forward/Backward Propagation

Forward: 입력 → 예측값

Backward: 오차 역전파로 가중치 업데이트

16. 손실함수 (Loss Function)
예측과 실제의 차이를 수치로 표현

MSE, MAE, Cross-Entropy, Hinge loss 등이 대표적

17. 옵티마이저 (Optimizer)
손실을 최소화하기 위해 가중치 업데이트 방법 정의

대표적: SGD, Adam, RMSProp

옵티마이저는 손실함수 결과를 이용해 가중치를 조정함

18. 경사하강법 (Gradient Descent)
손실 함수의 기울기를 따라 가중치를 조정

SGD: 하나의 샘플

Batch GD: 전체 데이터

Mini-batch GD: 일부 묶음

19. 교차검증 (Cross Validation)
모델의 일반화 능력을 평가

K-Fold: 데이터를 K개로 나누고 K번 평가

20. 하이퍼파라미터 튜닝
학습률, 에포크 수, 배치 크기 등 최적의 조합을 찾는 작업

21. CNN – 합성곱(Convolution)
입력 이미지의 특징을 추출 (필터/커널을 통해)

22. CNN – 풀링(Pooling)
공간 크기 축소, 특성 유지 → 계산량 감소, 과적합 방지

23. CNN – Dense Layer
Flatten 이후 분류나 회귀 등 최종 예측 수행

24. CNN – Stride/Filter 역할

Stride: 필터 이동 간격

Filter: 이미지 특징 감지, 가중치는 학습으로 결정됨

25. RNN 사용 이유와 한계
시계열/문장 등 순차 데이터 처리에 유리

한계: 장기 의존성 학습 어려움, 기울기 소실

26. LSTM – 이유와 한계
장기 의존성 문제 해결, 구조가 복잡하고 학습 느림

27. GRU – 이유와 차별성
LSTM보다 구조 간단, 속도 빠름, 성능은 비슷

28. 결정트리 – 불순도(Gini Index)

Gini Index: 특정 노드의 순수도 측정 (낮을수록 좋음)

29. 앙상블(Ensemble)
여러 모델을 조합해 성능 향상

예: 랜덤 포레스트, XGBoost

30. 부트스트랩핑(Bootstrapping)
데이터 샘플을 중복 허용해 여러 번 추출 → 다양성 증가

31. 배깅(Bagging)
여러 학습기를 병렬로 학습 → 과적합 방지

32. PCA (주성분 분석)
고차원 데이터를 선형결합으로 저차원으로 투영해 정보 압축

33. Dense Layer란
완전 연결층. 이전 층의 모든 뉴런과 연결된 기본적인 신경망 층
