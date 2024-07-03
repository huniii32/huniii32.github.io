---
title: "Deep Learning"
excerpt: "Upstage X FastCampus AI Lab"
categories:
  - Deep Learning
tags:
  - [python, bootcamp]

permalink: /deep-learning-boot/deep-learning-01/

toc: true
toc_sticky: true

date: 2024-06-19
last_modified_at: 2024-06-19
---
# 🦥 Deep Learning  

## AI/ML/DL 관점에서 크게 5단계로 개발 방법론

- 세 단계로 나눠서 SW 1.0, 2.0, 3.0이라 부르기도 함!  
  ![image](https://github.com/huniii32/huniii32.github.io/assets/164001121/8891c727-e789-428b-9ba9-9cca74a6e7b0)  

  1. SW 1.0 (**규칙 기반** 프로그래밍)   
      - 규칙 기반 프로그래밍은 목표 달성에 필요한 연산 방법을 사람이 전부 고안함   
      - 데이터 하나하나 찾아보고 조건을 만족하는 특징을 찾아 사람이 연산을 설계함  
      
      ![image](https://github.com/huniii32/huniii32.github.io/assets/164001121/c8ecc9e0-5b20-48b6-bc7e-61b5d3f3dee2)  
  
  2. SW 1.5 (**전통 머신 러닝** 기법)  
      - 특징값을 뽑는 방식은 사람이 직접 설계, 특징값들로 판별하는 로직은 기계가 스스로 고안하게 함  
      - 데이터에서 이런 이런 특징들을 찾겠다 → **사람**이 설계  
      - 특징들이 이런 조건이면 결과를 판단 → **기계**가 설계  
      
      ![image](https://github.com/huniii32/huniii32.github.io/assets/164001121/94f222d1-45c3-47b3-98f6-6c612185d5d3)  

      - 동작법
        1. 학습 데이터 준비  
            - 이미지, 텍스트 수집  
            - 특징 정의
            - 학습 데이터 생성  
        2. 모델 학습 : Try & Error 방식 → 최적의 연산 집합 찾기  
            - 예측 및 오차  
            - 최적의 연산 집합은 모든 Try 중에 **오차가 제일 작은 것** = 최적의 모델 = 학습 완료된 모델 = 추론 시 사용되는 모델(서비스 사용시)  
    
        [전체적인 동작 방식]  
        ![image](https://github.com/huniii32/huniii32.github.io/assets/164001121/b3aa32fa-ce9a-4f59-ac59-fdbce2f15d20)
  
  3. SW 2.0 (**딥러닝**)  
      - 출력을 계산 하기 위해 모든 연산들을 기계가 설계  
            ![image](https://github.com/huniii32/huniii32.github.io/assets/164001121/b3db6141-9fc9-4c45-8f07-ec762be97239)

      - 엄청나게 많은 연산들의 집합  
      - 자유도가 너무 높음 → **연산들의 구조**를 잡고 사용함  
          - CNN
          - RNN
      
      ![image](https://github.com/huniii32/huniii32.github.io/assets/164001121/77b85dec-fc84-4060-981e-d97c2f343070)

      - 딥러닝은 스스로 알아낼 게 더 많음(자유도 높음) → 다량의 데이터가 필요  
      - 문제점 : 분류 대상이 / 태스크가 바뀔 때마다 다른 모델이 필요  
  


    

## **💻Insight💻**  
1. 자료구조를 활용하여 알고리즘을 구현하기!!! 
2. 코테 준비는 차근 차근👍

#패스트캠퍼스 #업스테이지패스트캠퍼스 #AI부트캠프