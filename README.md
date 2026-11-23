# orangeschoolproject

Orange3 인공지능 기초 수행평가 프로젝트입니다.

## 프로젝트 자료

- [실험 결과 종합 분석 보고서](RESULTS_ANALYSIS.md)
- [Orange3 워크플로](workflow.ows)
- [원본 데이터 검증 기록](Sensorless_Drive_validation.txt)

## 주요 실험

UCI Sensorless Drive Diagnosis 데이터를 정상(Normal)과 이상(Fault)으로 이진 분류하고, 특징 수(48·25·11·6개) 및 표준화 여부에 따른 Logistic Regression, Random Forest, kNN 성능을 비교합니다.


## 교차검증 결과 요약

전체 데이터 58,509행에 대해 5-fold 층화 교차검증을 수행했습니다.

| 실험 | 모델 | Accuracy | MCC |
|---|---|---:|---:|
| CV-48 (48개 특징) | Random Forest | 99.9504% | 0.996998 |
| CV-25 (ANOVA 25개 + 표준화) | Random Forest | 99.9180% | 0.995029 |
| CV-25 (ANOVA 25개 + 표준화) | kNN | 97.9815% | 0.874412 |
| CV-25 (ANOVA 25개 + 표준화) | Logistic Regression | 97.5576% | 0.849119 |

CV-48 Random Forest가 가장 높은 절대 성능을 보였으며, CV-25 Random Forest는 특징을 48개에서 25개로 줄이고도 비슷한 수준의 성능을 유지했습니다. CV-25 전처리는 kNN과 Logistic Regression의 Normal 클래스 탐지 성능을 특히 크게 개선했습니다.

세부 수치, 혼동행렬, 클래스별 Recall 및 실험 설정·한계는 [실험 결과 종합 분석 보고서](RESULTS_ANALYSIS.md)를 참고합니다.


## 최종 상태

기본 모델 비교, 특징 수 비교, 표준화 전후 비교 및 5-fold 층화 교차검증을 마쳤습니다. 추가 실험을 늘리지 않고 현재 결과를 최종 보고서와 Orange3 워크플로로 정리합니다.
