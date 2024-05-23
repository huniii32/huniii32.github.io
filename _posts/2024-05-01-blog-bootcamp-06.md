---
title: "Python-EDA (Numpy)"
excerpt: "Upstage X FastCampus AI Lab - Python EDA"
categories:
  - Bootcamp
tags:
  - [python, bootcamp]

permalink: /bootcamp/bootcamp-06/

toc: true
toc_sticky: true

date: 2024-05-01
last_modified_at: 2024-05-02
---
# 🦥 Python-EDA

## **Numpy 특징**
1. 모든 원소의 **dtype이 같다.**  
2. 연산의 의미가 조금 다르다. **(Broadcasting)**  
3. **대용량 array**인 경우에 for문을 직접 사용하는 것보다 **내부적으로 정의된 연산**을 사용하는게 더 빠르다.    
4. 생성 후에 **크기 변경이 불가**능하다.  

## **Numpy 문법**
- **library**  
  ```python
  import numpy as np
  ```

- **np.array()**  
  ```python
  # 파이썬 list
  data = [1, 2, 3, 4]

  # 파이썬 list → numpy array 변환
  np.array(data)
  ```

- **np.arange(), zeros(), linspace(), random.randn()**  
  ```python
  # array 생성하기(0~9까지의 숫자 생성)  
  np.arange(0, 10)
  np.zeros(shape=(5, 3))
  np.linspace(0, 1, 100) # [start, stop]에서 num개의 number를 균등한 구간으로 잘라서 원소를 생성
  np.random.randn(5, 3)  # 주어진 shape을 가지는 numpy array를 만들어주는데, 원소는 표준정규분포에서 sampling
  ```

- **reshape()** 
  > 1차원 : vector  
  > 2차원 : matrix  
  > 3차원 이상 : tensor  
  > shape은 가장 바깥 괄호부터 원소의 개수를 순차적으로 기록한 것으로 정의    

  ```python
  x = np.zeros(shape=(5, 3, 4))

  # 224 x 224 크기의 3개(RGB) channel을 가지고 있는 이미지가 32개.
  x = np.zeros(shape=(32, 3, 224, 224))

  # reshape을 이용하여 만들기
  #x = np.arange(1, 10).reshape(9, 1)  # (9, ) != (9, 1)
  x = np.arange(1, 121).reshape(-1, 4, 2)
  ```  

- **Concatenation of arrays**  
  ```python
  arr1 = np.array([1, 2, 3])
  arr2 = np.array([4, 5, 6])
  # arr1 + arr2 = ?

  # arr1와 arr2를 합치기
  arr1 + arr2

  # stacking vertically
  np.vstack([arr1, arr2])

  # stacking horizontally
  np.hstack([arr1, arr2])
  ```

- **Array Arithmetic(like vector) → Universal Function**
  ```python
  v1 = np.array((1, 2, 3))
  v2 = np.array((4, 5, 6))

  # vector addition
  v1 + v2
  
  # vector subtrcation
  v1 - v2

  # elementwise multiplication
  v1 * v2

  # elementwise division
  v1 / v2

  # dot product
  v1 @ v2 
  ```

- **Broadcast & Universal Function**
  - 서로 크기가 다른 numpy array를 연산할 때, 자동으로 연산을 전파(broadcast)해주는 기능, 행렬곱 연산에 사용함
    ```python
    arr1 = np.array([1, 2, 3])

    arr2 = np.array([[-1, -1, -1], [1, 1, 1]])

    arr1 + arr2 # 오류 발생(operands could not be broadcast together with shapes (3,) (3,2))
    ```

    > (5,) + (3, 4, 5) **(가능)**  
    > (3, 4) + (5, 3, 4) **(가능)**  
    > (3, 4) + (3, 4, 5) **(불가능)**  

  - Universal Function : broadcast 기능을 확장해서, numpy array의 모든 원소에 동일한 함수를 반복문으로 적용한 것과 같은 효과를 내는 기능  
      ```python
      # f = lambda x : 1/x
      arr1 / 1  ## int -> float

      # Universal Function
      1 / arr1  ## 각 원소를 reverse 연산

      def reverse_num(x):
        return 1/x
      for i in range(len(arr1)):
        arr1[i] = reverse_num(arr1[i])
      ```
- **Math Function**  
  - **seed()**
    ```python
    # 표준정규분포에서 random sampling을 한 원소를 가지는 5x3 행렬을 만듦
    # pseudo-random : 현재 시각(ns)
    np.random.seed(42)   # set seed number
    mat1 = np.random.randn(5, 3)
    ```
  
  - **abs(), square(), sqrt(), norm(), eig()**
    ```python
    # 절대값 씌우기  
    np.abs(mat1)  

    # 제곱하기  
    np.square(mat1)

    # 제곱근 구하기
    np.sqrt(mat1.astype('complex')) # nan = not a number

    # linear algebra functions
    vec = np.array([1, 2, 3])

    # 1. norm
    np.linalg.norm(vec)

    # 2. eigenvalue
    mat = np.array([[1, 0], [0, 1]])
    np.linalg.eig(mat)
    ```

- **Aggregation Function**
  - sum(), mean(), std(), min(), max(), argmin(), argmax()
    ```python
    # Summation
    # axis=0 : 세로방향(=column방향), axis=1 : 가로방향(=row방향)

    # 총합
    np.sum(mat2, axis=1)

    # 평균
    np.mean(mat2, axis=0)

    # std
    np.std(mat2, axis=1)

    # min, max
    np.min(mat2)
    np.max(mat2, axis=1)

    # 최소값이 있는 Index
      np.argmin(mat2, axis=1)

    # 최대값이 있는 Index
    np.argmax(mat2, axis=0)
    ```

- **Numpy dtype**
  ```python
  print(f"int4 : -{2**3} ~ {2**3 - 1}")
  print(f"int8 : -{2**7} ~ {2**7 - 1}")
  print(f"int16 : -{2**15} ~ {2**15 - 1}")
  print(f"int32 : -{2**31} ~ {2**31 - 1}")
  print(f"int64 : -{2**63} ~ {2**63 - 1}")
  ```
  > int4 : -8 ~ 7  
  > int8 : -128 ~ 127  
  > int16 : -32768 ~ 32767  
  > int32 : -2147483648 ~ 2147483647  
  > int64 : -9223372036854775808 ~ 9223372036854775807  

## **💻Insight💻**
1. 데이터 분석을 위한 라이브러리 numpy에 대해 다지는 시간이였다!  
2. 다양한 함수들을 사용해 봤다...내가 모르는게 많구나....  

마음 다잡고 열심히 해봅세!!!  

![image](https://github.com/huniii32/huniii32.github.io/assets/164001121/5d673e3d-e228-48c3-ba1a-7e13bf0994d3)

#패스트캠퍼스 #업스테이지패스트캠퍼스 #AI부트캠프