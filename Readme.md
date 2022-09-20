# 전체 진행 프로세스

1. 머신러닝 전처리 및 모델용 패키지 설치
    !pip install catboost
    !pip install imblearn

2. 학습용 모듈 불러오기 (사용한 라이브러리)
    import pandas as pd
    import numpy as np

    from sklearn.model_selection import train_test_split, GridSearchCV, cross_val_score
    from imblearn.under_sampling import RandomUnderSampler

    from catboost import CatBoostClassifier

    from sklearn.metrics import classification_report, confusion_matrix


3. 학습데이터 불러오기 및 전처리(열 삭제 및 가변수화) 진행
    drop_col = ['ADID','DSP ID', '매체 ID', '애드유닛 ID', '노출 ID', 'SSP 입찰ID', 
            'DSP 입찰ID', 'AX 낙찰ID', 'WUID (웹 유저 ID)', '국가코드 ID', 'OS 버전 ID',
            '광고 응답 광고주 도메인','광고 응답 소재 카테고리','P5']
    해쉬값으로 되어있는 ID와 결측치 열 그리고 테스트 셋에는 없는 P5 제거

    dum_cols=['ADID 타입', '플랫폼', 'OS 종류', '사이즈 ID']
    범주화 컬럼들 가변수화

4. 모델 학습용 데이터 분할 및 언더 샘플링 진행

5. 캣부스트 분류기를 통하여 데이터 학습 진행

6. 테스트 데이터 불러온 후 예측을 위해 학습 데이터와 열값 같게 만듦

    drop_col_test = ['ADID','DSP ID', '매체 ID', '애드유닛 ID', '노출 ID', 'SSP 입찰ID', 
            'DSP 입찰ID', 'AX 낙찰ID', 'WUID (웹 유저 ID)', '국가코드 ID', 'OS 버전 ID',
            '광고 응답 광고주 도메인','광고 응답 소재 카테고리','Bid Index']

    dum_cols=['ADID 타입', '플랫폼', 'OS 종류', '사이즈 ID']

7. 테스트 데이터 예측 및 결과물 저장

# 사용한 OS 및 개발환경

    MS Windows 10에서 Python(3.9) Juypyter Lab(3.4.4)을 사용하여 학습진행하였습니다.