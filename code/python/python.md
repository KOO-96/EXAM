#### 집합(set)
- 순서가 없고 **중복을 허용하지 않는 자료형**
    - 집합 생성
        - fruit_basket = {"apple", "bannna", "grape"}
    - 집합에 요소 추가 (add)
        - fruit_basket.add("orange")  
        print(fruit_basket)  
        -> {"apple", "bannna", "grape", "orange"}
    - 집합에 요소 제거 (remove)
        - fruit_basket.remove("bannna")  
        print(fruit_basket)  
        -> {"apple", "grape", "orange"}
    - 집합 업데이트 (update)
        -  more_fruit = ["kiwi", "pear", "apple"]
        fruit_basket.update(more_fruit)
        print(fruit_basket)  
        -> {"apple", "grape", "orange", "kiwi", "pear"}
---
#### 비트 연산자(Bitwise Operator)
- 2진수 형태로 데이터를 다룰때 사용  
켜짐은 True / 꺼짐은 False
    - AND (&) -> 2개 스위치 모두 켜져있을 때
        - result = 5 & 3 ---> 101 & 011 = 001     
            print(result)  
            1
    - OR (|) -> 2개 스위치 하나라도 켜져있을 떄
        - result = 5 & 3 ---> 101 | 011 = 111    
            print(result)  
            7
    - XOR (^) -> 2개 스위치 하나만 켜져있을 때
        - result = 5 & 3 ---> 101 ^ 011 = 110  
            print(result)  
            6
    - 비트 시프트 (<<)  
        -> 왼쪽으로 한칸 이동(맨 오른쪽에 0하나 추가한다)
        - result = 5 << 1 ---> 101 << 1 = 1010   
            print(result)  
            10   
        -> 오른쪽으로 한칸 이동(맨 오른쪽 값을 지운다)
        - result = 5 >> 1 ---> 101 >> 1 = 010   
            print(result)  
            10
---
#### split()
- **문자열을 지정된 구분자를 기준으로 분할하여 리스트로 반환**  
기본 구분자는 공백이다