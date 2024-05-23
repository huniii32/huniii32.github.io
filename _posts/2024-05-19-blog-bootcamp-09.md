---
title: "Coding Test - Algorithm"
excerpt: "Upstage X FastCampus AI Lab - Coding Test"
categories:
  - Bootcamp
tags:
  - [python, bootcamp]

permalink: /bootcamp/bootcamp-09/

toc: true
toc_sticky: true

date: 2024-05-19
last_modified_at: 2024-05-19
---
# 🦥 Algorithm  
 
## **Python 특수 문법(참고)**  
- **중첩 함수**  
    - 어떤 함수 안에 정의도니 함수 객체를 의미함  
    - 예시

        ```python
        def say(text): # 외부 함수
            print("hello")
            def hello(): # 내부 함수 
                print("안녕하세요")
            hello()
        say()
        ```   
        
    - 사용하는 이유  
        1. 간결한 코드 작성  
            - 외부 함수에서 만든 객체에 내부 함수가 접근할 수 있도록 만들어 코드를 간결하게 함
            - 예시  
            
                ```python
                def sum_of_n_list():
                    n_list = [5, 2, 7, 3, 9]
                    def get_sum():
                        result = 0
                        for num in n_list:
                            print(f"num : {num}")
                            result += num
                        return result
                    return get_sum()
                print(sum_of_n_list())
                ```  
                > get_sum()에서 sum_of_list()의 리스트 n_list를 접근 가능하여  
                > 외부에서 따로 get_sum()을 선언하지 않고도 코드를 쓸 수 있음
                
        2. 클로저
            - 외부 함수에서 정의된 데이터를 외부 함수가 종료 되었음에도, 그 데이터를 사용할 수 있는 중첩된 함수 객체를 의미함  
            - 클로저가 되기 위한 조건 3가지  
                1. 특 정 함수의 내부 함수일 것  
                2. 외부 함수의 변수(프리 변수)를 반드시 참조할 것  
                3. 외부 함수가 내부 함수를 반환할 것 
            - 예시
                
                ```python
                def greeting(): # 외부 함수
                    s = 'good'
                    def hello(t):
                        greet = s + t
                        return greet
                    return hello
                
                g = greeting()
                print(g("morning"))
                ``` 
                > greeting은 외부 함수, 호출되면 함수 hello를 변수 g에 반환함  
                > 이때 hello는 외부 변수 s를 참조해서 새로운 문자열 greet를 반환함  
                > hello는 클로저가 됨  
                
            - ❌코딩 테스트에서 실질적으로 사용하지 않음❌  
            
    - ❗주의 사항❗  
        - 외부 함수에서 참조하는 변수는 변경이 불가함  
        - 외부 변수에 접근 가능하지만, 직접적으로 수정은 불가함  
        - 예시  
        
            ```python
            def compute():
                a = 5
                b = 9
                x = 3
                def linear_comb():
                    a = a * x + b # 예외 상황 발생(외부 변수 a 변경 시도)
                    return result
                return linear_comb()
            ```

            - nonlocal 명령어 사용 : 외부 변수에 대한 수정을 가능하게 해줌   

            - global 명령어 사용 : 특정 변수를 전역 변수로 설정  
            
            ```python
            def foo():
                global a # global a = 1(x)
                a = 1
                print("내부 함수 :", a)

            foo()
            a += 1
            print("외부 :", a)
            ```  
            > 함수에서 선언된 변수를 외부에서도 접근 가능하도록 만듦  
            > global를 지정함과 동시에 할당은 불가함  
        
- **함수를 통한 자유로운 데이터 전달과 반환**  
    1. 반환 개수에 대한 제한이 없음  
    2. 다른 언어에 비해 데이터 이동에 대한 제약이 적음!!

        ```python
        def return_lots_of_result():
            result1 = 0
            result2 = False 
            result3 = []
            return result1, result2, result3

        print(return_lots_of_result())
        ```

## **정의**
- 문제해결 방법, 어떠한 문제를 해결하기 위해 정해진 일련의 절차나 방법  
- 자주 쓰이는 문제 해결 방법(알고리즘)은 패턴화  
    - BFS, DFS, Binary Search, Dijkstra 등   
- 한 문제를 해결할 수 있는 알고리즘은 다양함   
    - 각 문제에 적합한 알고리즘을 선택할 수 있어야 함  
    - 알고리즘을 평가할 수 있어야 함  

## **코딩테스트 알고리즘 유형**  
1. **완전 탐색**
    - 정답이 될 가능성이 있는 **모든 후보**를 **체계적\(반복문, 재귀, 비트마스크\)**으로 확인하는 것(쉽게 말해 무식한 방법)  
    - 시간 복잡도가 매우 높아질 수 있음  
    - 문제의 종류
        - **모든 가능성 탐색** : 모든 가능성을 탐색해보고 문제에서 원하는 결과와 일치하는 값을 찾는 문제  
        - **부분집합 생성** : 모든 부분집합을 생성하여 특정 조건을 만족하는 부분집합을 찾는 문제  
        - **순열과 조합** : 주어진 요소들로 가능한 모든 순열 또는 조합을 생성하는 문제  
        - **격자 탐색** : 격자 내의 모든 위치를 탐색하며 특정 조건을 만족하는 위치를 찾는 문제  
    
    - (예시) 리스트[4, 9, 7, 5, 1]에서 **두 개**의 숫자를 더해서 **14**가 될 수 있나요? (중복 X)   
  
2. **재귀**  
    - 자신을 정의할 때 자기 자신을 재참조하는 함수를 뜻 함  
    - **시간 복잡도**  
        - 재귀 함수 호출 수 * (재귀 함수 하나당) 시간 복잡도  
            - 팩토리얼의 경우  
                1. 재귀 함수의 호출 : $$(N)$$      
                2. 재귀 함수 하나 당 시간 복잡도 : $$O(1)$$    
                3. 재귀의 시간 복잡도 : $$O(N * 1)$$    
            - 피보나치의 경우  
                1. 재귀 함수의 호출 : $$(2^N)$$  
                2. 재귀 함수 하나 당 시간 복잡도 : $$O(1)$$    
                3. 재귀의 시간 복잡도 : $$O((2^N) * 1)$$  
    - **점화식**  
        - 팩토리얼과 피보나치를 자세히 살펴보면 N번째 함수를 N-1번째 함수로 표현 함  
            - 팩토리얼의 경우 $$f(n) = n * f(n-1)$$  
            - 피보나치의 경우 $$f(n) = f(n-1) + f(n-2)$$  
    - **재귀는 자기 자신을 참조하게 되면, 무한 루프에 빠질 수 있음**    
        → **Base Case**를 설정 해줘야 함    
    - 문제의 종류    
        - **팩토리얼**  

            ```python  
            def factorial(n):
                if n == 1:  
                    return 1  
                return n * factorial(n - 1)  
            ``` 
            > 점화식 : $$f(n) = n * f(n-1)$$    
            > Base Case : $$f(1) = 1$$  
          
        - **피보나치**  
        
            ```python
            def fibo(n):
                if n == 1 or n == 2:  
                    return 1
                return fibo(n - 1) + fibo(n - 2)  
            ``` 
            > 점화식 : $$f(n) = f(n-1) + f(n-2)$$  
            > Base Case : $$f(1) = 1, f(2) = 1$$

    **💻재귀 = 점화식 + Base Case💻**   

    - ❗추가❗  
        - 재귀 한도 구하기  
        
            ```python
            import sys 
            print(sys.getrecursionlimit())
            ```

## **💻Insight💻**  
1. **특정 알고리즘**은 그냥 외우는 게 좋아 보인다!!!  
    → 완전 탐색, 재귀, BFS, DFS 등등...   
2. 대학교 수업 시간에 배운것을 다시 상기해보는 시간이였음😶

#패스트캠퍼스 #업스테이지패스트캠퍼스 #AI부트캠프