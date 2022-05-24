# DACON_Agricultures
![20220524_125522](https://user-images.githubusercontent.com/84311270/169951121-53c73805-81fc-4794-b9b1-9bac003d188f.png)
기존 농넷의 농산물 가격 예측 모형을 개선할 수 있는 알고리즘 개발

# Dataset  
1. public_data : public leaderboard용 데이터  
1-1. train.csv : 베이스라인 코드용으로 가공된 학습 데이터  
date: 일자  
요일: 요일  
품목_거래량(kg): 해당 품목의 거래량  
품목_가격(원/kg): 해당 품목의 kg당 가격  
품목_가격 산출 방식 : 품목 또는 품종의 총 거래금액/총 거래량 (※취소된 거래내역 제외)  
1-2. test_files : 베이스라인 코드용으로 가공된 테스트 데이터(추론일자별 분리, ex.test_2020-08-29.csv => 2020년 8월 29일 추론에 사용 가능 데이터)  
1-3. train_AT_TSALET_ALL : 학습용 전국 도매시장 거래정보 데이터(train.csv 생성에 사용)  
SALEDATE: 경락 일자  
WHSAL_NM: 도매시장  
CMP_NM: 법인  
PUM_NM: 품목  
KIND_NM: 품종  
DAN_NM: 단위  
POJ_NM: 포장  
SIZE_NM: 크기  
LV_NM: 등급  
SAN_NM: 산지  
DANQ: 단위중량  
QTY: 물량  
COST: 단가  
TOT_QTY: 총물량 (음수로 집계된 값은 거래 취소 내역)  
TOT_AMT: 총금액  
1-4. test_AT_TSALET_ALL : 추론용 전국 도매시장 거래정보 데이터(test_files 생성에 사용)  

2. private_data : private leaderboard용 데이터, public leaderboard 학습 및 추론 사용 불가  
	2-1. private.csv : 베이스라인 코드용으로 가공된 데이터  
	2-2. AT_TSALET_ALL : 2021년 8월까지의 전국 도매시장 거래정보 데이터(private.csv 생성에 사용)  

3. sample_submission.csv : 제출 양식  
예측대상일자: 예측대상일(기준일로부터 1,2,4주 뒤 일자)  
품목_가격(원/kg): 해당 품목의 kg당 가격  

## Model
농산물 데이터에 대한 결측치 및 계절성을 파악하고 Wide & Deep Model과 Xgboost, LightGBM 모델을 사용하여 학습.

## Results
Public Score : 0.18301, Private Score : 0.25476로 최종 6위로 우수상 수상.
![20220524_125545](https://user-images.githubusercontent.com/84311270/169951898-b5f13688-34af-47c3-af7c-4263b583044c.png)

