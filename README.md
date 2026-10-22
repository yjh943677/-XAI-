# 🏢 아파트 가격 예측 및 XAI 분석

## 📌 주요 내용 및 목차

1. **서론**: 연구 배경 및 분석 목표
2. **데이터 설명**: 
   * 국토교통부 실거래가 데이터 (2015~2023년, 약 500만 건 이상)
   * 외부 데이터 수집 (시군구 단위 평균소득, 행정 경계 GIS 정보)
3. **탐색적 데이터 분석 (EDA)**:
   * 거래금액, 전용면적, 건축연도 분포 분석
   * 지역별 거래 분포 (시도별/시군구별 거래건수 및 비율)
   * 시계열 분석 (월별 거래건수 및 평균 거래금액 추이)
4. **가설 수립 및 검증**: 총 6개의 가설(전용면적, 건축연도, 지역, 층수, 건물연식, 평균소득) 검증
5. **예측 모델 구축 및 성능 비교**:
   * 사용 모델: Linear Regression, Decision Tree, Random Forest, XGBoost, LightGBM
   * 평가 지표: MAE, RMSE, MAPE (10-Fold 교차검증)
   * **최종 선정 모델**: **LightGBM** (가장 우수한 예측 성능 기록)
6. **설명 가능한 인공지능 (XAI) 기법**:
   * Feature Importance (Gain 합산)
   * Partial Dependence Plot (PDP)
   * Proxy Model (Decision Tree 규칙 추출)
   * LIME (저가·중가·고가 대표 샘플 지역별·변수별 기여도 분석)
   * SHAP (전역적/지역적 변수 영향력 분석)
7. **결론**: 분석 결과 요약 및 향후 개선 방향

---

## 🛠️ 기술 스택 및 환경
* **Language**: Python
* **Libraries**: Pandas, NumPy, Scikit-learn, XGBoost, LightGBM, Matplotlib, Seaborn 등
* **Machine Learning**: 10-Fold Cross-Validation, Hyperparameter Tuning

---

## 💡 주요 인사이트
* **핵심 영향 요인**: 아파트 가격 예측에 가장 큰 결정력을 가지는 요인은 **지역명(특히 서울 강남·서초권)**과 **전용면적**으로 확인됨.
* **신축 효과**: 건축연도가 최근이거나 건물 연식이 짧을수록, 그리고 평균소득이 높은 지역일수록 거래금액이 높게 형성되는 경향이 뚜렷하게 나타남.
* **XAI 해석**: LightGBM 모델에 XAI 기법(SHAP, PDP, LIME 등)을 적용하여 복잡한 비선형 예측 결과의 근거를 정량적으로 규명함.
