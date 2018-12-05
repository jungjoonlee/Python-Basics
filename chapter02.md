# Python-Basics
점프 투 파이썬
-------------
Link: [점프 투 파이썬](https://wikidocs.net/book/1)
### 02장. 파이썬 프로그래밍의 기초, 자료형
#### 02-1. 숫자형
+ 숫자형의 종류
  + 정수형
```python
a = 123
a = -178
a = 0
```
++ 실수형
```python
a = 1.2
a = -3.45
a = 4.24E10
a = 4.24e-10
```
++ 8진수와 16진수
+++ 8진수
```python
a = 0o177
```
+++ 16진수
```python
a = 0x8ff
b = 0xABC
```
+ 숫자형을 활용하기 위한 연산자
++ 사칙연산
```python
a = 3
b = 4
a + b
a - b
a * b
a / b
```
++ 제곱 연산자
a ** b
```
++ 나눗셈 나머지 반환 연산자
```python
7 % 3
3 % 7
```
++ 나눗셈 몫 반환 연산자
```python
7 // 4
-7 // 4
```
+ 연습문제
++ 문제1
```python
(80 + 75 + 55) / 3
70.0
OR
a = 80
b = 75
c = 55
(a + b + c) / 3
70.0
```
++ 문제2
++ 나눗셈 나머지 연산자
```python
17 // 3
5
```
++ 문제3
```python
17 % 3
2
```
++ *문제2,3 또 다른 풀이*
```python
divmod(17 , 3)
(5, 2)
```
++ 문제4
```python
a = 임의의 자연수
if a % 2 == 0:
  print("a는 짝수이다.")
else:
  print("a는 홀수이다.")
```
---
#### 02-2. 문자열
+ 문자열 생성 방법
```python
"Hello World"
'Python is fun'
"""Life is too short, You need python"""
'''Lige is too short, You need python'''
```
+ 문자열 내 따옴표 포함 방법
  1. 큰 따옴표 사용 - 작은 따옴표 포함
  ```python
  food = "Python's favorite food is perl."
  ```
  2. 작은 따옴표 사용 - 큰 따옴표 포함
  ```python
  say = '"Python is very easy." he says.'
  ```
  3. 백슬래시 사용 - 작은 따옴표, 큰 따옴표 모두 가능
  ```python
  food = 'Python\'s favorite food is perl.'
  say = "\"Python is very easy.\" he says."
  ```
+ 여러 줄의 문자열 변수 대입
  1. 이스케이프 코드 `\n` 삽입
  ```python
  multiline = "Life is too short\nYou need python."
  ```
  2. 작은 따옴표/큰 따옴표 3개 연속 기입
  ++ 작은 따옴표 3개 사용
  ```python
  multiline = '''
  Life is too short
  You need python.
  '''
  print(multiline)
  ```
  ++ 큰 따옴표 3개 사용
  ```python
  multiline = """
  Life is too short
  You need python.
  """
  print(multiline)
  ```
  ++ *주로 활용하는 이스케이프 코드*
  +++ `\n` : 줄바꿈
  +++ `\t` : 수평 탭
  +++ `\\` : 문자 "`\`"
  +++ `\'` : 단일 인용부호(`'`)
  +++ `\"` : 이중 인용부호(`"`)
+ 문자열 연산
  1. 문자열 더하기(Concatenation)
  ```python
  head = "Python"
  tail = " is fun!"
  head + tail
  ```
  2. 문자열 곱하기
  ```python
  a = "Python"
  a * 2
  ```
  *문자열 곱하기 응용 - 에디터로 소스 작성*
  ```python
  # multistring.py
  
  print("=" * 50)
  print("My Program")
  print("=" * 50)
  ```
+ 문자열 인덱싱(Indexing)
```python
>>> a = "Life is too short, You need Python"
>>> a[3]
'e'
>>> a[0]
'L'
>>> a[-0]
'L'
>>> a[-1]
'n'
>>> a[-6]
'P'
```
+ 문자열 슬라이싱(Slicing)
```python
>>> a = "Life is too short, You need Python."
>>> a[0:4]
'Life'
>>> a[0:3]
'Lif'
>>> a[0:2]
'Li'
```
```python
>>> a[5:7]
'is'
>>> a[12:17]
'short'
```
```python
>>> a[19:]
'You need Python.'
>>> a[:17]
'Life is too short'
>>> a[:]
'Life is too short, You need Python.'
```
```python
>>> a[19:-7]
'You need '
>>> a[-3:-1]
'on'
```
```python
>>> a = "20010331Rainy"
>>> date = a[:8]
>>> weather = a[8:]
>>> date
'20010331'
>>> weather
'Rainy'
```
```python
>>> a = "20010331Rainy"
>>> year = [a:4]
>>> day = a[4:8]
>>> weather = a[8:]
>>> year
'2001'
>>> day
'0331'
>>> weather
'Rainy'
```
```python
>>> a = "Pithon"
>>> a[:1]
'P'
>>> a[2:]
'thon'
>>> a[:1] + 'y' + a[2:]
'Python'
```
+ 문자열 포매팅(Formatting)
  1. 문자열 포매팅 따라 하기
    + 숫자 바로 대입
    ```python
    >>> "I eat %d apples." % 3
    'I eat 3 apples.'
    ```
    + 문자열 바로 대입
    ```python
    >>> "I eat %s apples." % "five"
    'I eat five apples.'
    ```
    + 숫자 값을 나타내는 변수 대입
    ```python
    >>> number = 3
    >>> "I eat %d apples." % number
    'I eat 3 apples.'
    ```
    + 2개 이상의 값 넣기
    ```python
    >>> number = 10
    >>> day = "three"
    >>> "I ate %d apples. So I was sick for %s days." % (number, day)
    'I ate 10 apples. So I was sick for three days."
    ```
  2. 문자열 포맷 코드
  |코드|설명|
  |:---|:------------------------|
  |%s  |문자열 (String)           |
  |%c  |문자 1개 (Character)      |
  |%d  |정수 (Integer)            |
  |%f  |부동소수 (Floating-point) |
  |%o  |8진수                     |
  |%x  |16진수                    |
  |%%  |Literal % (문자 `%`)      |
  ```python
  %s 포맷 코드는 % 뒤 값을 자동으로 문자열로 변환
  >>> "I have %s apples." % 3
  'I have 3 apples.'
  >>> "Rate is %s." % 3.234
  'Rate is 3.234.'
  ```
  ```python
  >>> "Error is %d%%." % 98
  'Error is 98%.'
  ```
  3. 포맷 코드와 숫자 함께 사용하기
    + 정렬과 공백
    ```python
    >>> "%10s" % "hi"
    '        hi'
    ```
    ```python
    >>> "%-10sjane." % "hi"
    'hi        jane.'
    ```
    + 소수점 표현
    ```python
    >>> "%0.4f" % 3.42134234
    '3.4213'
    ```
    ```python
    >>> "%10.4f" % 3.42134234
    '    3.4213'
    ```
  4. format 함수를 이용하 포매팅
    + 숫자 바로 대입
    ```python
    >>> "I eat {0} apples.".format(3)
    'I eat 3 apples.'
    ```
    + 문자열 바로 대입
    ```python
    >>> "I eat {0} apples.".format("five")
    'I eat five apples.'
    ```
    + 숫자 값을 나타내는 변수 대입
    ```python
    >>> number = 3
    >>> "I eat {0} apples.".format(number)
    'I eat 3 apples.'
    ```
    + 2개 이상의 값 넣기
    ```python
    >>> number = 10
    >>> day = "three"
    >>> "I ate {0} apples. So I was sick for {1} days.".format(number, day)
    'I ate 10 apples. So I was sick for three days."
    ```
    + 이름으로 넣기
    ```python
    >>> " I ate {number} apples. So I was sick for {day} days.".format(number=10, day=3)
    'I ate 10 apples. So I was sick for 3 days.'
    ```
    + 인덱스와 이름 혼용해서 넣기
    ```python
    >>> "I ate {0} apples. So I was sick for {day} days.".format(10, day=3)
    'I ate 10 apples. So I was sick for 3 days.'
    ```
    + 왼쪽 정렬
    ```python
    >>> "{0:<10}".format("hi")
    'hi        '
    ```
    + 오른쪽 정렬
    ```python
    >>> "{0:>10}".format("hi")
    '        hi'
    ```
    + 가운데 정렬
    ```python
    >>> "{0:^10}".format{"hi")
    '    hi    '
    ```
    + 공백 채우기
    ```python
    >>> "{0:=^10}}.format("hi")
    '====hi===='
    >>> "{0:!<10}".format("hi")
    'hi!!!!!!!!'
    ```
    + 소수점 표현
    ```python
    >>> y = 3.42134234
    >>> "0:0.4f}".format(y)
    '3.4213'
    >>> "{0:10.4f}".format(y)
    '    3.4213'
    ```
    + `{` 또는 `}` 문자 표현
    ```python
    >>> "{{ and }}".format()
    '{ and }'
    ```
  5. f 문자열 포매팅
  ```python
  >>> name = '홍길동'
  >>> age = 30
  >>> f'나의 이름은 {name}입니다. 나이는 {age}입니다.'
  '나의 이름은 홍길동입니다. 나이는 30입니다.
  ```
  ```python
  >>> age = 30
  >>> f'나는 내년이면 {age+1}살이 된다.'
  '나는 내년이면 31살이 된다.'
  ```
  ```python
  >>> d = {'name':'홍길동', 'age':30}
  >>> f'나의 이름은 {d["name"]}입니다. 나이는 {d["age"]}입니다.'
  '나의 이름은 홍길동입니다. 나이는 30입니다.'
  ```
  ```python
  # 왼쪽 정렬
  >>> f'{"hi":<10}'
  'hi        '
  # 오른쪽 정렬
  >>> f'{"hi":>10}'
  '        hi'
  # 가운데 정렬
  >>> f'{"hi":^10}'
  '    hi    '
  ```
  ```python
  # 공백 채우기
  >>> f'{"hi":=^10}'
  '====hi===='
  >>> f'{"hi":!<10}'
  'hi!!!!!!!!'
  ```
  ```python
  # 소수점 표현
  >>> y = 3.42134234
  >>> f'{y:0.4f}'
  '3.4213'
  >>> f'{y:10.4f}'
  '    3.4213'
  ```
  ```python
  # { 또는 } 문자 사용
  >>> f'{{ and }}'
  '{ and }'
  ```
+ 문자열 관련 함수들
  1. 문자 개수 세기 (count)
  ```python
  >>> a = "hobby"
  >>> a.count('b')
  2
  ```
  2. 위치 알려주기1 (find)
  ```python
  >>> a = "Python is the best choice."
  >>> a.find('b')
  14
  >>> a.find('k')
  -1
  ```
  3. 위치 알려주기2 (index)
  ```python
  >>> a = "Life is too short."
  >>> a.index('t')
  8
  >>> a.index('k')
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  ValueError: substring not found
  ```
  4. 문자열 삽입 (join)
  ```python
  >>> a = ","
  >>> a.join('abcd')
  'a,b,c,d'
  ```
  ```python
  >>> ",".join('abcd')
  'a,b,c,d'
  ```
  ```python
  >>> ",".join(['a', 'b', 'c', 'd'])
  'a,b,c,d'
  ```
  5. 소문자 > 대문자 (upper)
  ```python
  >>> a = "hi"
  >>> a.upper()
  'HI'
  ```
  6. 대문자 > 소문자 (lower)
  ```python
  >>> a = "HI"
  >>> a.lower()
  'hi'
  ```
  7. 왼쪽 공백 지우기 (lstrip)
  ```python
  >>> a = " hi "
  >>> a.lstrip()
  'hi '
  ```
  8. 오른쪽 공백 지우기 (rstrip)
  ```python
  >>> a = " hi "
  >>> a.rstrip()
  ' hi'
  ```
  9. 양쪽 공백 지우기 (strip)
  ```python
  >>> a = " hi "
  >>> a.strip()
  'hi'
  ```
  10. 문자열 바꾸기 (replace)
  ```python
  >>> a = "Life is too short."
  >>> a.replace("Life", "Your leg")
  'Your leg is too short.'
  ```
  11. 문자열 나누기 (split)
  ```python
  >>> a = "Life is too short."
  >>> a.split()
  ['Life', 'is', 'too', 'short']
  ```
  ```python
  >>> a = "a:b:c:d"
  >>> a.split(':')
  ['a', 'b', 'c', 'd']
  ```
+ 연습 문제
  1. 문자열 출력 1
