---
title: "Statistics(기초)"
excerpt: "Upstage X FastCampus AI Lab - Statistics"
categories:
  - Bootcamp
tags:
  - [statistics, bootcamp]

permalink: /bootcamp/bootcamp-04/

toc: true
toc_sticky: true

date: 2024-04-24
last_modified_at: 2024-04-24
---
# 🦥 Statistics(기초)

## **기초 통계학**  

- **평균값**  
    - 산술평균
    - 기하평균
    - 조화평균

- **중앙값**
    - 데이터를 크기 순으로 정렬했을 때 가운데에 있는 데이터  

- **최빈값**
    - 가장 많이 등장한 데이터  

(ex)  
  {1,1,1,2,2,3,3,3,3,3}  
    - 평균 : 2.2  
    - 중앙값 : 2.5  
    - 최빈값 : 3

(참고)  
![image](https://github.com/huniii32/huniii32.github.io/assets/164001121/49901ad9-a218-47d1-905e-8aedda02d704)  

- **분산 & 표준편차**  

- **사분위 범위(IQR)**  
    - 값을 같은 갯수로 4개로 나는 각각의 값  
    - 1사분위(Q1) : 25%  
    - 2사분위(Q2) : 50% = 중앙값  
    - 3사분위(Q3) : 75%  
    - 사분위간 범위 : Q3-Q1  

    ![image](https://github.com/huniii32/huniii32.github.io/assets/164001121/c93080fd-711a-4754-96b4-34408dc7949e)

- **변동계수**  
    - 상대적으로 얼마나 변동이 많은지를 보기 위한 지표  
    - 단위가 다르거나, 표준편차가 비슷한 그룹끼리 비교하고 싶을 때 일정한 기분에 따라 비교 가능  
    - **변동계수(CV) = 표준편차/평균  
 
- **왜도(Skewness) & 첨도(Kurtosis)**  
    - **왜도**
        - 분포의 비대칭도를 나타내는 통계량  
        - 비대칭이 커질수록 왜도의 절대값은 증가  
        - 일반적으로 왜도가 -1~+1 범위는 치우침이 없는 데이터라 부름  

    ![image](https://github.com/huniii32/huniii32.github.io/assets/164001121/4e5164d0-d8fe-4313-a3f4-4fe4e124b169)

    - **첨도**
        - 꼬리 부분의 길이와 중앙 부분의 뾰족함을 ㅗ데이터의 분포를 알 수 있음  
        - Mesokurtic : 정규 분포 모양
        - Leptokurtic : 중앙 부분은 Mesokurtic보다 높고 뾰족하기 때문에 이상치가 많을수 있음  
        - PlatyKurtic : Leptokurtic와 반대, 이상치가 없음 → 데이터 다시 확인 필요  

    ![image](https://github.com/huniii32/huniii32.github.io/assets/164001121/28bb91bb-c251-49ac-b5bf-c4d63ebfee8a)

- **모집단**
    - 확률 표본 추출  
        - 단순 샘플링 : 단순 랜덤으로 샘플을 추출  
        - 층화 샘플링 : 모집단을 몇 개의 그룹으로 나누어 각 그룹에서 랜덤으로 n개씩 추출  
        - 계통 샘플링 : 모집단 데이터에서 1~n개의 번호를 임의로 매긴 다음 일정 간격마다 데이터 추출  
        - 군집 샘플링 : Cluster로 모집단 데이터로 분할하고, 군집 중 하나 or 여러개의 군집을 선정, 선정된 군집의 전체 데이터 사용  

        ![image](https://github.com/huniii32/huniii32.github.io/assets/164001121/de0716b1-920c-44f8-a4a8-e44c04b835cd)

- **정규분포 & 중심극한정리**  
    - **정규분포**
        - 연속 확률 분포 중에서 가장 많이 사용  
        - 평균에 대해서 좌우 대칭, 평균에서 최대값, 종모양  
        - 자연 현상이나 사회 여러 현상들이 정규 분포를 따름  
        - 평균과 표준편차에 의해 결정됨  

        ![image](https://github.com/huniii32/huniii32.github.io/assets/164001121/bc69f65f-53d2-4b30-9155-6dad605a0a99)

    - **중심극한정리**
        - **표본의 크기가 커질수록** 표본 평균의 분포는 모집단의 **분포 모양과는 관계없이 정규분포에 가까워짐**  
        - 표본 평균의 평균은 모집단의 모평균과 같고, 표본 평균의 표준 편차는 모집단의 모 표준 편차를 표본 크기의 제곱근으로 나눈 것과 같음  

        ![image](https://github.com/huniii32/huniii32.github.io/assets/164001121/686a288a-e760-46a5-83e8-2b470c8c578c)

- **카이제곱분포**
  - 검정 통계량이 카이제곱 분포를 따르느 통계 검정에 사용  
  - **분산의 특징**을 확률 분포로 만든 것  
  - 분포는 자유도에 의해 정의  
  - 모분산을 구하는 것  
  - 카이제곱 분포의 자유도가 높을수록 정규 분포에 근접  
  - y-skewed(y축에 편향된) 분포  
  - 제곱된 값의 분산을 다루기 때문에 → -값은 존재하지 않고 +값만 존재  

  ![image](https://github.com/huniii32/huniii32.github.io/assets/164001121/69cca972-7c4a-48b6-90c2-cf3c8d8b9268)

- **스튜던트 t분포**
    - **모분산이 알려져 있지 않고 소규모 표본**인 경우에 쓸 수 있는 새로운 분포 개발  
    - 정규 분포와 생김새가 비슷 but 꼬리 부분이 더 두껍고 길게 생김  
    - 표본의 크기가 30 이하인 경우 t분포 사용  
    - t분포가 널리 적용되는 이유 : 중심극한정리 → **표본통계량**은 보통 정규분포를 따름  
    - t분포는 표본평균, 두 표본평균 사이의 차이, 회귀 파라미터 등의 분포를 위한 기준으로 사용함  

    ![image](https://github.com/huniii32/huniii32.github.io/assets/164001121/28d190c7-9e50-4eff-b3fb-66e2025fac8c)

- **F분포**
    - 스튜던트 t분포는 집단 3개 이상은 검정이 불가함 → F분포로 검정  
    - 집단간의 분산을 다룸  
    - 분산분석에 주로 사용함  
    - F = 집단 **간** 분산 / 집단 **내** 분산  

    ![image](https://github.com/huniii32/huniii32.github.io/assets/164001121/585a67a5-8f77-4cae-9da1-30ded1066b3b)

- **분산분석**  
    - 3개 이상의 다수 집간을 비교할 때 사용하는 검정 방법  
    - F분포 사용(집단 간 분산 / 집단 내 분산)  
    - 등분산성 가정  
        - 집단 내 분산이 서로 비슷한가? 비슷해야 비교 가능  
    - 검정 순서  
        - Omnubus F검정
            - F값이 큰가? 차이가 있는가?
        - post hoc검정  
            - 구체적으로 얼마나 차이가 나는가?  

    ![image](https://github.com/huniii32/huniii32.github.io/assets/164001121/4a064633-2a72-4ccf-8140-91e3b50358d6)
    ![image](https://github.com/huniii32/huniii32.github.io/assets/164001121/8b44f782-2b6d-4608-ba40-6e89b38c5086)






#패스트캠퍼스 #업스테이지패스트캠퍼스 #AI부트캠프