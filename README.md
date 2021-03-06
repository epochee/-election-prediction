# 선거 예측
직접 데이터 수집 및 EDA 후 머신러닝을 통해 2022년의 대통령 선거를 예측하는 프로젝트

# 프로젝트 선정 이유 
'어떤 프로젝트를 해야 베네핏이 많을까' 라는 생각을 많이 해봤습니다.   
그러다 문득 대통령 선거가 약 1년정도 남은 이 시점에 대통령 선거를 예측한다면 주식투자에 있어 큰 베네핏이 있을거라고 생각했기에 이 프로젝트를 선정했습니다.

# 데이터 수집   
1. 데이터를 수집하기 위해 대통령 여론조사하는 곳에 하나씩 하나씩 전화를 돌려 raw data 를 얻을 수 있을지 여쭤보았습니다.   
그 중 '한국갤럽조사연구소'라는 곳에서 raw data를 받았습니다.   
# 데이터 전처리   
1. raw data 가 년도 별로 나눠져 있어서 melt 함수를 통해 합쳐준 뒤 필요없는 column은 제거하고 column 명이 어렵게 된 경우 쉽게 만들어줬습니다.  ex)'variable'->'대선후보'   
2. 나이별 투표수를 만들기 위해 투표수에 통계청에서 구한 나이별 인구수를 백분율해 나누어 새로운 column을 생성했습니다.
3. raw data에서 얻은 정당지지도와 대선후보 선호도를 기준으로 투표수를 나누어 새로운 column을 생성했습니다.

# 모델 생성
1. 모델간의 성능비교를 위해 3개의 모델 LinearRegression,Ridge,xgboost 성능을 비교했습니다.
2. 데이터를 히스토스램으로 확인한 결과 데이터가 한쪽으로 치우쳐있어 표준화를 해줬습니다. 
3. 지역명 column에서 읍동명까지 세세하게 나눈 결과 카디널리티가 너무 높아 제거 후 다시 학습했습니다. 
4. xgboost모델의 성능이 가장 높게 나왔기에 xgboost모델을 최종 모델로 선정했습니다.

# 프로젝트 후기
모델을 잘 선정하고 학습하는 것도 너무나 중요하지만 데이터가 정말 중요하다고 깨달았습니다.    
대통령 선거에 대한 데이터라서 법적으로 개인이 구할 수 있는 한계가 있고 구하기도 힘들었지만 이보다 더 구하기 힘든 데이터가 많다고 생각합니다.   
따라서 구하기 힘든 데이터들을 어떻게하면 구할 수 있는지 많은 생각을 해야겠다고 다짐하게된 프로젝트였습니다.
