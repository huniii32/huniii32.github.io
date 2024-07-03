---
title: ""
excerpt: "Upstage X FastCampus AI Lab"
categories:
  - Coding Test
tags:
  - [python, bootcamp]

permalink: /coding-test-boot/deep-learning-02/

toc: true
toc_sticky: true

date: 2024-06-19
last_modified_at: 2024-06-19
---
# 🦥 

## 딥러닝의 구성요소  
1. 데이터  
    - 해결하고자 하는 문제(task)에 따라 필요로 하는 데이터의 형태나 구성이 달라짐  
      - 문제(1)
        - 문제 : 고양이 존재 여부 판단  
        - 데이터 : 고양이가 있는 이미지, 없는 이미지  

      - 문제(2)
        - 문제 : 고양이, 개 존재 여부 및 위치 판단  
        - 데이터 : 고양이, 개 이미지, 둘 다 **있는** 이미지, 둘 다 **없는** 이미지
      
      - **라벨링** : 위치를 사각형으로 표시한다면 **사각 영역** → **정답 값 지정**  

      ![image](https://github.com/huniii32/huniii32.github.io/assets/164001121/d1487e53-660c-408a-a1a9-cec6adee30bb)  

2. 모델  
    - 입력을 원하는 결과로 바꾸어주는 일련의 **연산 과정을 구조화한 것**  
    ![image](https://github.com/huniii32/huniii32.github.io/assets/164001121/cbf4b5a2-2c42-44a3-abd5-e3e4198a56f6)

3. 손실 함수  
    - 실제 혹은 목표로 하는 값과 모델의 추정한 값 사이의 차이, 오차를 **수치화하는 함수**
    ![image](https://github.com/huniii32/huniii32.github.io/assets/164001121/c2354606-02ef-4c63-8401-381690ed17ed)  

4. 최적화 알고리즘  
    - **손실 함수가 최소값**을 가지도록 모델의 **파라미터**를 최적화하는 알고리즘
    ![image](https://github.com/huniii32/huniii32.github.io/assets/164001121/2376862b-6ff7-40f7-9a94-532f62255e94)

    - 모든 값의 조합에 대해서 비용을 계산하는 것은 불가능함 → 최적화 알고리즘 사용  

## 딥러닝 파이프라인 
- 모델이 **데이터**를 통해 추정한 값이 정답/목표와 최대한 가까워지도록 파라미터를 **최적화 알고리즘**을 적용하여 최적의 모델 파라미터를 찾는 과정  

  ![image](https://github.com/huniii32/huniii32.github.io/assets/164001121/5b57e176-dccf-4f4b-be5b-616d56517d71)



## **💻Insight💻**  

#패스트캠퍼스 #업스테이지패스트캠퍼스 #AI부트캠프