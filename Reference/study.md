# 인공지능 핵심 개념 정리

## 1. 인공지능에서 지능에 해당하는 기능
- 학습(Learning)
- 추론(Reasoning)
- 문제 해결(Problem Solving)
- 언어 이해(NLP)
- 시각 인식(Vision)
- 행동 제어(Control)

## 2. 인공지능의 종류 3가지
- **지도학습 (Supervised Learning)**: 입력 + 정답으로 모델 학습
- **비지도학습 (Unsupervised Learning)**: 정답 없이 패턴 학습
- **강화학습 (Reinforcement Learning)**: 보상 기반 최적 정책 학습

## 3. 전통적 프로그래밍 vs. 인공지능 프로그래밍
| 구분 | 전통 프로그래밍 | 인공지능 |
|------|----------------|-----------|
| 방식 | 규칙 + 데이터 → 결과 | 데이터 + 결과 → 규칙(모델) |
| 목적 | 명시적 알고리즘 구현 | 자동 학습 |

## 4. 딥러닝 vs. 머신러닝
- 머신러닝: 특징을 사람이 설계
- 딥러닝: 특징도 모델이 자동 학습 (Ex. CNN)

## 5. Classification vs. Regression
| 구분 | Classification | Regression |
|------|----------------|------------|
| 목적 | 범주 분류 | 수치 예측 |
| 예시 | 이메일 스팸 분류 | 집값 예측 |

## 6. 차원의 저주 (Curse of Dimensionality)
- 특성이 많아질수록 데이터 희소해지고 학습 어려워짐

## 7. 차원 축소 (Dimensionality Reduction)의 필요성
- 계산 효율성 증가
- 과적합 방지
- 시각화 용이

## 8. Ridge vs. Lasso
| 항목 | Ridge | Lasso |
|------|-------|--------|
| 규제 방식 | L2 규제 | L1 규제 |
| 효과 | 가중치 축소 | 일부 특성 제거 |
| Feature Scaling | 필요함 | 필요함 |

## 9. Overfitting vs. Underfitting
- Overfitting: 학습 데이터에 과도하게 적합
- Underfitting: 너무 단순해서 학습 부족

## 10. Feature Engineering vs. Feature Selection
- Engineering: 특성 생성
- Selection: 불필요 특성 제거

## 11. 전처리(Preprocessing)
- **목적**: 품질 향상, 성능 향상
- **방법**: 이상치 제거, 결측치 보정, 정규화 등

## 12. EDA (탐색적 데이터 분석)
- 데이터 분포, 상관관계, 이상치 파악

## 13. 회귀에서 절편과 기울기
- 절편: y축 교차점
- 기울기: 입력 1 증가 → 출력 변화
- 딥러닝의 weight/bias와 연관

## 14. Activation Function
- 비선형성 부여
- **Sigmoid**: 이진 분류, 0~1 출력
- **Softmax**: 다중 분류

## 15. Forward / Backward Propagation
- Forward: 예측값 계산
- Backward: 오차 역전파로 가중치 업데이트

## 16. 손실함수 (Loss Function)
- 예측과 실제 차이 측정
- 대표: MSE, MAE, Cross-Entropy, Hinge

## 17. Optimizer
- 손실 최소화를 위한 가중치 조정 도구
- 손실함수와는 역할이 다름 (손실 → 옵티마이저가 반응)

## 18. 경사하강법 (Gradient Descent)
- **SGD**: 샘플 하나씩
- **Batch GD**: 전체 데이터
- **Mini-Batch GD**: 일부 데이터 묶음

## 19. 교차검증 (Cross Validation)
- 모델 일반화 성능 평가
- K-Fold: 데이터를 K개로 나눠 K번 검증

## 20. 하이퍼파라미터 튜닝
- 학습률, 에포크 수, 배치 크기 등 최적화

## 21. CNN – 합성곱(Convolution)
- 이미지에서 특징 추출

## 22. CNN – 풀링(Pooling)
- 공간 크기 축소, 과적합 방지

## 23. CNN – Dense Layer
- 최종 예측을 위한 완전 연결층

## 24. CNN – Stride / Filter
- **Stride**: 필터 이동 간격
- **Filter**: 특징 추출, 가중치는 학습됨

## 25. RNN의 이유와 한계
- 순차 데이터 학습에 유리
- **한계**: 장기 의존성 문제 (기울기 소실)

## 26. LSTM의 이유와 한계
- 장기 의존성 해결
- 구조 복잡, 학습 느림

## 27. GRU의 이유와 차별성
- 간단한 구조로 빠른 학습
- LSTM과 성능 비슷

## 28. 결정트리 – Gini Index
- 낮을수록 노드가 순수함 (0: 완전 순수)

## 29. 앙상블 (Ensemble)
- 여러 모델을 조합해 성능 향상 (예: 랜덤 포레스트)

## 30. 부트스트랩핑 (Bootstrapping)
- 중복 허용 랜덤 샘플링 → 다양성 확보

## 31. 배깅 (Bagging)
- 여러 학습기를 병렬로 학습 → 과적합 방지

## 32. PCA (주성분 분석)
- 고차원 데이터를 저차원 선형 결합으로 축소

## 33. Dense Layer란?
- 완전 연결층. 모든 노드와 연결되어 최종 예측 담당
