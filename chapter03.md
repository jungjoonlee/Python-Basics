# Python-Basics
점프 투 파이썬
-------------
Link: [점프 투 파이썬](https://wikidocs.net/book/1)
### 03장. 프로그래밍의 구조를 쌓는다! 제어문
#### 03-1. if문
+ if문 예제
```python
# "돈이 있으면 택시를 타고, 돈이 없으면 걸어 간다."
>>> money = 1
>>> if money:
...     print("택시를 타고 가라")
... else:
...     print("걸어 가라")
...
택시를 타고 가라
```
+ if문의 기본 구조
```python
if 조건문:
    수행할 문장1
    수행할 문장2
    ...
else:
    수행할 문장A
    수행할 문장B
    ...
```
    1. 들여쓰기
    ```python
    # 들여쓰기 누락 시 오류 발생
    if 조건문:
        수행할 문장1
        수행할 문장2
        수행할 문장3
    ```
    ```python
    # 오류 예시1
    >>> money = 1
    >>> if money:
    ...     print("택시를")
    ... print("타고")
      File "<stdin>", line 3
        print("타고")
            ^
    SyntaxError: invalid syntax
    ```
    ```python
    # 오류 예시2
    >>> money = 1
    >>> if money:
    ...     print("택시를")
    ...     print("타고")
    ...         print("가자")
      File "<stdin>", line 4
        print("가자")
        ^
    IndentationError: unexpected indent
    ```
+ 조건문이란 무엇인가?
"조건문"이란 참과 거짓을 판단하는 문장
  1. 비교연산자
  
  비교연산자 | 설명
  --------- | ----
  x < y | x가 y보다 작다
  x > y | x가 y보다 크다
  X == y | x와 y가 같다
  x != y | x와 y가 같지 않다
  x >= y | x가 y보다 크거나 같다
  x <= y | x가 y보다 작거나 같다
  
  ```python
  >>> x = 3
  >>> y = 2
  >>> x > y
  True
  >>> x < y
  False
  >>> x == y
  False
  >>> x != y
  True
  ```
  ```python
  # 만약 3,000원 이상의 돈을 갖고 있으면 택시를 타고, 그렇지 않으면 걸어 가라"
  >>> money = 2000
  >>> if money >= 3000:
  ...     print("택시를 타고 가라")
  ... else:
  ...     print("걸어가라")
  ...
  걸어가라
  ```
  2. and, or, not
  
  연산자 | 설명
  ----- | ----
  x or y | x와 y 둘 중에 하나만 참이면 참이다
  x and y | x와 y 모두 참이어야 참이다
  not x | x가 거짓이면 참이다
  
  ```python
  # 돈이 3,000원 이상 있거나 카드가 이다면 택시를 타고 그렇지 않으면 걸어 가라
  >>> money = 2000
  >>> card = 1
  >>> if money >= 3000 or card:
  ...     print("택시를 타고 가라")
  ... else:
  ...     print("걸어가라")
  ...
  택시를 타고 가라
  ```
  3. x in s, x not in s
  
  in | not in
  ---|-------
  x in 리스트 | x not in 리스트
  x in 튜플 | x not in 튜플
  x in 문자열 | x not in 문자열
  
  ```python
  >>> 1 in [1, 2, 3]
  True
  >>> 1 not in [1, 2, 3]
  False
  ```
  ```python
  >>> 'a' in ('a', 'b' ,'c')
  True
  >>> 'j' not in 'python'
  True
  ```
  ```python
  # 만약 주머니에 돈이 있으면 택시를 타고, 없으면 걸어 가라
  >>> pocket = ['paper', 'cellphone' ,'money']
  >>> if 'money' in pocket:
  ...     print("택시를 타고 가라")
  ... else:
  ...     print("걸어가라")
  ...
  택시를 타고 가라
  ```
  ```python
  # 조건문에서 아무 일도 하지 않게 설정하고 싶을 때
  # "주머니에 돈이 있으면 가만히 있고, 주머니에 돈이 없으면 카드를 꺼내라"
  >>> pocket = ['paper', 'money', 'cellphone']
  >>> if 'money' in pocket:
  ...     pass
  ... else:
  ...     print("카드를 꺼내라")
  ...  
  ```
+ 다양한 조건을 판단하는 elif
```python
>>> pocket = ['paper', 'cellphone']
>>> card = 1
>>> if 'money' in pocket:
...     print("택시를 타고 가라")
... elif card:
...     print("택시를 타고 가라")
... else:
...     print("걸어가라")
...
택시를 타고 가라
```
```python
# if, elif, else 모두 사용 시의 기본 구조
If <조건문>:
    <수행할 문장1>
    <수행할 문장2>
    ...
elif <조건문>:  # elif는 개수에 제한 없이 사용할 수 있음.
    <수행할 문장1>
    <수행할 문장2>
    ...
elif <조건문>:
    <수행할 문장1>
    <수행할 문장2>
    ...
else:
    <수행할 문장1>
    <수행할 문장2>
    ...
```
```python
>>> if 'money' in pocket:
...     pass
... else:
...     print("카드를 꺼내라")
...
```
```python
# if문을 한 줄로 작성하는 방법
>>> pocket = ['paper', 'money' ,'cellphone']
>>> if 'money' in pocket: pass
... else: print("카드를 꺼내라")
...
```
+ 조건부 표현식
```python
>>> if score >= 60:
...     message = "success"
... else:
...     messsage = "failure"
```
```python
# 위 코드를 조건부 표현식으로 표현
>>> message = "success" if score >= 60 else "failure"
```
```python
# 조건부 표현식 정의
조건문이 참인 경우 if 조건문 else 조건문이 거짓인 경우
```
+ 연습문제
  1. 조건문1
  ```python
  >>> money = 5000
  >>> card = False
  >>> if money >= 4000 or card:
  ...     print("택시를 탈 수 있다")
  ... else:
  ...     print("택시를 탈 수 없다")
  ...
  택시를 탈 수 있다
  ```
  2. 조건문2
  ```python
  >>> hong_number = 23
  >>> lucky_list = [1, 9, 23, 46]
  >>> if hong_number in lucky_list:
  ...     print("야호")
  ...
  야호
  ```
  3. 홀수 짝수 판별
  ```python
  >>> num = 2  # num은 주어진 수
  >>> if num % 2 == 0:
  ...     print("짝수")
  ... else:
  ...     print("홀수")
  ...
  짝수
  ```
  4. 문자열 분석
  ```python
  >>> a = "나이:30,키:180"
  >>> temp = a.split(",")
  >>> age = temp[0].split(":")[-1]  # '30'
  >>> height = temp[1].split(":")[-1]  # '180'
  >>> if int(age) < 30 and int(height) >= 175:
  ...     print("YES")
  ... else:
  ...     print("NO")
  ...
  NO
  ```
  5. 조건문3
  ```python
  >>> a = "Life is too short, you need python"
  >>> if 'wife' in a:  # False
  ...     print('wife')
  ... elif 'python' in a and 'you' not in a:  # False
  ...     print('python')
  ... elif 'shirt' not in a:  # True
  ...     print('shirt')
  ... elif 'need' in a:  # True
  ...     print('need')
  ... else:
  ...     print('none')
  ...
  shirt
  ```
---
#### 03-2. while문
+ while문의 기본 구조
```python
while <조건문>:
    <수행할 문장1>
    <수행할 문장2>
    <수행할 문장3>
    ...
```
```python
# while문 예시
>>> treeHit = 0
>>> while treeHit < 10:
...     treeHit = treeHit + 1
...     print("나무를 %d번 찍었습니다." % treeHit)
...     if treeHit == 10:
...         print("나무 넘어갑니다.")
...
나무를 1번 찍었습니다.
나무를 2번 찍었습니다.
나무를 3번 찍었습니다.
나무를 4번 찍었습니다.
나무를 5번 찍었습니다.
나무를 6번 찍었습니다.
나무를 7번 찍었습니다.
나무를 8번 찍었습니다.
나무를 9번 찍었습니다.
나무를 10번 찍었습니다.
나무 넘어갑니다.
```
+ while문 직접 만들기
```python
>>> prompt = """
... 1. Add
... 2. Del
... 3. List
... 4. Quit
...
... Enter number: """
>>>
```
```python
>>> number = 0
>>> while number != 4:
...     print(prompt)
...     number = int(input())
...

1. Add
2. Del
3. List
4. Quit

Enter number:
```
```python
Enter number:
1

1. Add
2. Del
3. List
4. Quit

Enter number:
```
```python
Enter number:
4
>>>
```
+ while문 강제로 빠져나가기
```python
>>> coffee = 10
>>> money = 300
>>> while money:
...     print("돈을 받았으니 커피를 줍니다.")
...     coffee = coffee - 1
...     print("남은 커피의 양은 %d개입니다." % coffee)
...     if not coffee:
...         print("커피가 다 떨어졌습니다. 판매를 중지합니다.")
...         break
...
돈을 받았으니 커피를 줍니다.
남은 커피의 양은 9개입니다.
돈을 받았으니 커피를 줍니다.
남은 커피의 양은 8개입니다.
돈을 받았으니 커피를 줍니다.
남은 커피의 양은 7개입니다.
돈을 받았으니 커피를 줍니다.
남은 커피의 양은 6개입니다.
돈을 받았으니 커피를 줍니다.
남은 커피의 양은 5개입니다.
돈을 받았으니 커피를 줍니다.
남은 커피의 양은 4개입니다.
돈을 받았으니 커피를 줍니다.
남은 커피의 양은 3개입니다.
돈을 받았으니 커피를 줍니다.
남은 커피의 양은 2개입니다.
돈을 받았으니 커피를 줍니다.
남은 커피의 양은 1개입니다.
돈을 받았으니 커피를 줍니다.
남은 커피의 양은 0개입니다.
커피가 다 떨어졌습니다. 판매를 중지합니다.
```
    1. break문을 이용해 자판기 작동 과정 만들기
    ```python
    # coffee.py
    
    coffee = 10
    while True:
        money = int(input("돈을 넣어 주세요: "))
        if money == 300:
            print("커피를 줍니다.")
            coffee = coffee - 1
        elif money > 300:
            print("거스름돈 %d원을 주고 커피를 줍니다." % (money - 300))
            coffee = coffee - 1
        else:
            print("돈을 다시 돌려주고 커피를 주지 않습니다.")
            print("남은 커피의 양은 %d개입니다." % coffee)
        if not coffee:
            print("커피가 다 떨어졌습니다. 판매를 중지합니다.")
            break
    ```
    ```python
    # coffee.py 실행 결과
    돈을 넣어 주세요: 500
    거스름돈 200원을 주고 커피를 줍니다.
    돈을 넣어 주세요: 300
    커피를 줍니다.
    돈을 넣어 주세요: 100
    돈을 다시 돌려주고 커피를 주지 않습니다.
    남은 커피의 양은 8개입니다.
    돈을 넣어 주세요: 
    ```
+ while문의 맨 처음으로 돌아가기
```python
>>> a = 0
>>> while a < 10:
...     a = a + 1
...     if a % 2 == 0: continue
...     print(a)
...
1
3
5
7
9
```
+ 무한 루프
```python
# 무한 루프 예시
>>> while True:
...     print("Ctrl+C를 눌러야 while문을 빠져나갈 수 있습니다.")
...
Ctrl+C를 눌러야 while문을 빠져나갈 수 있습니다.
Ctrl+C를 눌러야 while문을 빠져나갈 수 있습니다.
Ctrl+C를 눌러야 while문을 빠져나갈 수 있습니다.
Traceback (most recent call last):
  File "<stdin>", line 2, in <module>
KeyboardInterrupt
```
+ 연습문제
    1. 
    
    
    


