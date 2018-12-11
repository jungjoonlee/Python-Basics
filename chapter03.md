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
  1. 1부터 100까지 더하기
  ```python
  >>> result = 0
  >>> i = 1
  >>> while i <= 100:
  ...     result += i
  ...     i += 1
  ...
  >>> print(result)
  5050
  ```
  2. 3의 배수의 합
  ```python
  >>> result = 0
  >>> i = 0
  >>> while i <= 1000:
  ...     i += 1
  ...     if i % 3 != 0: continue
  ...     result += i
  ...
  >>> print(result)
  166833
  ```
  ```python
  # 교재 풀이
  >>> result = 0
  >>> i = 1
  >>> while i <= 1000:
  ...     if i % 3 == 0:
  ...         result += i
  ...     i += 1
  ...
  >>> print(result)
  166833
  ```
  3. 50점 이상의 총합
  ```python
  >>> A = [20, 55, 67, 82, 45, 33, 90, 87, 100, 25]
  >>> result = 0
  >>> i = 0
  >>> while i < 10:
  ...     if A[i] < 50:
  ...         i += 1
  ...         continue
  ...     result += A[i]
  ...     i += 1
  ...
  >>> print(result)
  481
  ```
  ```python
  # 교재 풀이
  >>> A = [20, 55, 67, 82, 45, 33, 90, 87, 100, 25]
  >>> result = 0
  >>> while A:
  ...     mark = A.pop()
  ...     if mark >= 50:
  ...         result += mark
  ...
  >>> print(result)
  481
  ```
  4. 별 표시하기1
  ```python
  >>> i = 1
  >>> while i < 5:
  ...     a = '*'
  ...     a = a * i
  ...     print(a)
  ...     i += 1
  ...
  *
  **
  ***
  ****
  ```
  ```python
  # 교재 풀이
  >>> i = 0
  >>> while True:
  ...     i += 1
  ...     if i > 4: break
  ...     print('*' * i)
  ...
  *
  **
  ***
  ****
  ```
  5. 별 표시하기2
  ```python
  >>> i = 4
  >>> while i > 0:
  ...     a = '*'
  ...     b = ' '
  ...     a = a * ((i * 2) - 1)
  ...     b = b * (4 - i)
  ...     print(b + a + b)
  ...     i -= 1
  ...
  *******
   ***** 
    ***
     *
  ```
  ```python
  # 교재 풀이
  >>> star = 7
  >>> space = 0
  >>> while star > 0:
  ...     print(' ' * space + '*' * star)
  ...     star -= 2
  ...     space += 1
  ...
  *******
   *****
    ***
     *
  ```
---
#### 03-3. for문
+ for문의 기본 구조
```python
for 변수 in 리스트(또는 튜플, 문자열):
    수행할 문장1
    수행할 문장2
    ...
```
```python
# 예시1 - 전형적인 for문
>>> test_list = ['one', 'two', 'three']
>>> for i in test_list:
...     print(i)
...
one
two
three
```
```python
# 예시2 - 다양한 for문의 사용
>>> a = [(1, 2), (3, 4), (5, 6)]
>>> for (first, last) in a:
...     print(first + last)
...
3
7
11
```
```python
# 예시3 - for문 응용
"총 5명의 학생이 시험을 보았는데 시험 점수가 60점이 넘으면 합격이고 그렇지 않으면 불합격이다. 합격인지 불합격인지 결과를 보여주시오."
```
```python
# marks1.py
marks = [90, 25, 67, 45, 80]

number = 0
for mark in marks:
    number = number + 1
    if mark >= 60:
        print("%d번 학생은 합격입니다." % number)
    else:
        print("d%번 학생은 불합격입니다." % number)
```
```python
# marks1.py 실행 결과
1번 학생은 합격입니다.
2번 학생은 불합격입니다.
3번 학생은 합격입니다.
4번 학생은 불합격입니다.
5번 학생은 합격입니다.
```
+ for문과 continue
```python
# marks2.py
marks = [90, 25, 67, 45, 80]

number = 0
for mark in marks:
    number = number + 1
    if mark < 60: continue
    print("%d번 학생 축하합니다. 합격입니다." % number)
```
```python
# marks2.py 실행 결과
1번 학생 축하합니다. 합격입니다.
3번 학생 축하합니다. 합격입니다.
5번 학생 축하합니다. 합격입니다.
```
+ for와 함께 자주 사용하는 range함수
  1. range함수 사용법
  ```python
  >>> a = range(10)
  >>> a
  range(0, 10)
  >>> a = range(1, 11)
  >>> a
  range(1, 11)
  ```
  2. range함수 예시
  ```python
  >>> sum = 0
  >>> for i in range(1, 11):
  ...     sum = sum + i
  ...
  >>> print(sum)
  55
  ```
  ```python
  # marks3.py
  marks = [90, 25, 67, 45, 80]
  for number in range(len(marks)):
      if marks[number] < 60: continue
      print("%d번 학생 축하합니다. 합격입니다." % (number + 1))
  ```
  ```python
  # marks3.py 실행 결과
  1번 학생 축하합니다. 합격입니다.
  3번 학생 축하합니다. 합격입니다.
  5번 학생 축하합니다. 합격입니다.
  ```
  3. for와 range를 이용한 구구단
  ```python
  >>> for i in range(2, 10):
  ...     for j in range(1, 10):
  ...         print(i * j, end = " ")  # 입력 인수 end를 넣음으로써 결과값 출력 시 다음 줄로 넘어가지 않고 해당 줄에 계속해서 결과값 출력.
  ...     print('')  # 2단, 3단 등을 구분하기 위해 두 번째 for문이 끝나면 결과값을 다음 줄부터 출력하게 해주는 문장.
  ...
  2 4 6 8 10 12 14 16 18
  3 6 9 12 15 18 21 24 27
  4 8 12 16 20 24 28 32 36
  5 10 15 20 25 30 35 40 45
  6 12 18 24 30 36 42 48 54
  7 14 21 28 35 42 49 56 63
  8 16 24 32 40 48 56 64 72
  9 18 27 36 45 54 63 72 81
  ```
+ 리스트 안에 for문 포함하기
```python
>>> a = [1, 2, 3, 4]
>>> result = []
>>> for num in a:
...     result.append(num*3)
...
>>> print(result)
[3, 6, 9, 12]
```
```python
# 리스트 내포(List comprehension)의 일반적인 문법
[표현식 for 항목 in 반복가능객체 if 조건]
```
```python
# 리스트 내포(List comprehension) 예시1
>>> a = [1, 2, 3, 4]
>>> result = [num * 3 for num in a]
>>> print(result)
[3, 6, 9, 12]
```
```python
# 리스트 내포(List comprehension) 예시2
>>> a = [1, 2, 3, 4]
>>> result = [num * 3 for num in a if num % 2 == 0]
>>> print(result)
[6, 12]
```
```python
# for문을 여러 개 사용할 경우의 문법
[표현식 for 항목1 in 반복가능객체1 if 조건1
        for 항목2 in 반복가능객체2 if 조건2
        ...
        for 항목n in 반복가능객체n if 조건n]
```
```python
# for문을 여러 개 사용한 예시 - 구구단
>>> result = [x * y for x in range(2, 10)
...                 for y in range(1, 10)]
>>> print(result)
[2, 4, 6, 8, 10, 12, 14, 16, 18, 3, 6, 9, 12, 15, 18, 21, 24, 27, 4, 8, 12, 16, 20, 24, 28, 32, 36, 5, 10, 15, 20, 25, 30, 35, 40, 45, 6, 12, 18, 24, 30, 36, 42, 48, 54, 7, 14, 21, 28, 35, 42, 49, 56, 63, 8, 16, 24, 32, 40, 48, 56, 64, 72, 9, 18, 27, 36, 45, 54, 63, 72, 81]
```
+ 연습문제
  1. 1부터 100까지 출력
  ```python
  >>> for i in range(1, 101):
  ...     print(i)
  ...
  1
  2
  3
  ...
  98
  99
  100
  ```
  2. 5의 배수의 총합
  ```python
  >>> sum = 0
  >>> for i in range(1, 1001):
  ...     if i % 5 == 0: 
  ...         sum = sum + i
  ...
  >>> print(sum)
  100500
  ```
  3. 학급의 평균 점수
  ```python
  >>> A = [70, 60, 55, 75, 95, 90, 80, 80, 85, 100]
  >>> total = 0
  >>> for score in A:
  ...     total += score
  ...
  >>> average = total / len(A)
  >>> print(average)
  79.0
  ```
  4. 혈액형
  ```python
  >>> BloodType = ['A', 'B', 'A', 'O', 'AB', 'AB', 'O', 'A', 'B', 'O', 'B', 'AB']
  >>> sumA = 0
  >>> sumB = 0
  >>> sumO = 0
  >>> sumAB = 0
  >>> for i in BloodType:
  ...     if i == 'A':
  ...         sumA = sumA + 1
  ...     if i == 'B':
  ...         sumB = sumB + 1
  ...     if i == 'O':
  ...         sumO = sumO + 1
  ...     if i == 'AB':
  ...         sumAB = sumAB + 1
  ...
  >>> print(sumA)
  3
  >>> print(sumB)
  3
  >>> print(sumO)
  3
  >>> print(sumAB)
  3
  ```
  ```python
  # 교재 풀이
  >>> data = ['A', 'B', 'A', 'O', 'AB', 'AB', 'O', 'A', 'B', 'O', 'B', 'AB']
  >>> result = {}
  >>> for blood_type in data:
  ...     if blood_type in result:
  ...         result[blood_type] += 1
  ...     else:
  ...         result[blood_type] = 1
  ...
  >>> print(result)
  {'A': 3, 'B': 3, 'O': 3, 'AB': 3}
  ```
  5. 리스트 내포1
  ```python
  >>> numbers = [1, 2, 3, 4, 5]
  >>> result = []
  >>> for n in numbers:
  ...     if n % 2 == 1:
  ...         result.append(n * 2)
  ...
  >>> print(result)
  [2, 6, 10]
  ```
  ```python
  >>> numbers = [1, 2, 3, 4, 5]
  >>> result = [n * 2 for n in numbers if n % 2 == 1]
  >>> print(result)
  [2, 6, 10]
  ```
  6. 리스트 내포2
  ```python
  >>> A = 'Life is too short, you need python'
  >>> B = 'aeiou'
  >>> result = [i for i in A if i not in B]
  >>> print(' '.join(result))
  L f   s t   sh rt, y   n  d pyth n
  ```
  ```python
  # 교재 풀이
  >>> vowels = 'aeiou'
  >>> sentence = 'Life is too short, you need python'
  >>> ' '.join([a for a in sentence if a not in vowels])
  'L f   s t   sh rt, y   n  d pyth n'
  ```
