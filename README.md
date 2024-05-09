# Anomaly_Detection
이상 탐지 : '이상'이라고 정의한 사건 및 패턴을 탐지하는 활동

더 큰 **리스크 발생 전 피해를 최소화** 하는 것이 목적 

풀려고 하는 문제에 대한 정의가 중요 </br></br>

- 이상(Abnormal) vs 이상치(Outlier)
  - 이상치
    - 데이터 자체에 초점을 맞췄을 때 멀리 떨어진 데이터 
    - 분석하고자 하는 데이터에서 매우 적은 확률로 나타나는 데이터
    - 위험한 이유 : 결과 해석시 오해를 발생시킴

  - 이상
    - 데이터가 아닌 **현업의 문제해결 관점**에서 이상일 것 같은 데이터
    - 현업 도메인 관점에서 문제 발생 가능성이 높은 데이터
      - **정상 범주에 있어도 이상 현상으로 정의 할 수 있음** (패턴 / 발생 빈도)</br>
      - 관리하지 않았을 때 큰 리스크 </br>
        ex) 고장 일으키거나, 사기 전조 증상 => 이상 데이터로 관리해야
      - 자주 발생하지 않는 패턴이 이상일 확률이 일반적으로 높은 편</br></br>


- 이상 데이터 발생 원인
  - 다양한 원인 학습 이유 : 이상 데이터 발생 원인 알아야 근본 원인 해결 가능
  - 분석 전 데이터가 올바르게 수집되어 있는 상황인지 **사전 점검**이 필수</br>
  - 오류 원인</br>
    1. `표본 추출 오류(Sampling Error)` : 샘플링 과정에서 잘못 샘플링 (ex. 다른 모수에서 추출)
    2. `입력 오류 (Data Entry Error)` : Human Errror (데이터 분포로 쉽게 탐지 가능) 
    3. `실험 오류 (Experimental Error)` : 실헙 통해 데이터 수집시 실험 조건이 상이
    4. `측정 오류 (Measurement Error)` : 측정 장비 오류 (다른 측정기와의 측정 분포 확인해 찾아낼 수)
    5. `데이터 처리 오류 (Data Preprocessing Error)` </br>
       : 데이터 **ETL** (Extract > Transform > Load) 과정에서 발생할 수 있는 오류</br>
         서버 셧 다운 등 데이터 **정합성과 신뢰성 확인하는 과정**을 필수적으로 거쳐야 함 </br>
    6. `자연 오류 (Natural Outlier)` : 자연스럽게 발생하는 이상 값 (*분석 통해 해결하려는 문제) </br></br>

- 이상 탐지 종류
  - 데이터 타입 </br>
    1. `*Time series` (sequential) vs `*static`(정적, point) : 데이터 간의 연관성 유무 차이 
    2. `univariate`(단변량) vs `multivariate`(다변량)
    3. `data type` (binary / categorical / continuous / hybrid)
    4. `relational`(상관관계 있는) vs `independent`(독립적인)
    5. `well-known or not` (기존 룰 적용 가능한 / 알려져 있지 않은)  </br></br>

  - 문제 해결 관점 이상 탐지 유형</br>
    1. `Point Anomaly Detection` : 정적 점 분포에 초점. Outlier를 distance 기반 찾는
    2. `Contextual Anomaly Detection` : 시계열 데이터 분석</br>
       연속적인 변화 패턴을 읽어 예상 변화와 동떨어진 결과를 탐지 (global하게)</br>
       `*민감도` : 이상 증상을 얼마나 예민하게 탐지할 것인지 기준 설정 
    3. `Collective Anomaly Detection` (Local한 이상치) </br>
       개별 포인트는 이상이 아닌데, 개별 인스턴스가 아닌 집단 인스턴스에서 이상 확인
    4. `Online Anomaly Detection` </br>
       실시간 데이터 수집 체계가 구축되어 있는 환경에서 탐지 </br>
       실시간으로 어떻게 빠르게 처리하고 이상을 탐지할지 설계하는 것이 매우 중요 </br>
       무거운 알고리즘도 쓸 수 없다 
    5. `Distributed Anomaly Detection` </br>
       관측치의 정상 분포에서 벗어난 이상 데이터를 탐지 </br></br>

- Label(라벨)에 따른 문제 유형 분류
  - *
