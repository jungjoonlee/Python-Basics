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
  + 실수형
  ```python
  a = 1.2
  a = -3.45
  a = 4.24E10
  a = 4.24e-10
  ```
  + 8진수와 16진수
    ++ 8진수
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
  ```python
  >>> print('"점프 투 파이썬" 문제를 풀어보자')
  "점프 투 파이썬" 문제를 풀어보자
  >>> print('''"점프 투 파이썬" 문제를 풀어보자''')
  "점프 투 파이썬" 문제를 풀어보자
  >>> print(""""점프 투 파이썬" 문제를 풀어보자""")
  "점프 투 파이썬" 문제를 풀어보자
  >>> print("\"점프 투 파이썬\" 문제를 풀어보자")
  "점프 투 파이썬" 문제를 풀어보자
  ```
  2. 문자열 출력 2
  ```python
  >>> a = """
  ... Life is too short
  ... You need Python
  ..."""
  >>> print(a)
  
  Life is too short
  You need python
  
  >>> '''
  ... Life is too short
  ... You need Python
  ...'''
  >>> print(a)
  
  Life is too short
  You need python
  
  ```
  3. 공백 추가
  ```python
  >>> " " * 24 + "PYTHON"
  '                        PYTHON'
  ```
  ```python
  >>> "%30s" % "PYTHON"
  '                        PYTHON'
  ```
  4. 문자열 나누기
  ```python
  >>> pin = "881120-1068234"
  >>> yymmdd = pin[:6]
  >>> num = pin[7:]
  >>> print(yymmdd)
  881120
  >>> print(num)
  1068234
  ```
  5. 문자열 인덱싱
  ```python
  >>> pin = "881120-1068234"
  >>> print(pin[7])
  1
  ```
  6. 문자열 변경
  ```python
  >>> a = "1980M1120"
  >>> a[4] + a[:4] + a[5:]
  'M19801120'
  ```
  7. 문자열 찾기
  ```python
  >>> a = "Life is too short, you need python"
  >>> a.find("short")
  12
  ```
  8. 문자열 바꾸기1
  ```python
  >>> a = "a:b:c:d"
  >>> b = a.replace(":", "#")
  >>> b
  'a#b#c#d'
  ```
  9. 문자열 바꾸기2
  ```python
  >>> a = "a:b:c:d"
  >>> b = a.split(":")
  >>> b
  ['a', 'b', 'c', 'd']
  >>> c = "#".join(b)
  >>> c
  'a#b#c#d'
  ```
---
#### 02-3. 리스트 자료형
+ 리스트 작성법
```python
>>> a = []
>>> b = [1, 2, 3]
>>> c = ['Life', 'is', 'too', 'short']
>>> d = [1, 2, 'Life', 'is']
>>> e = [1, 2, ['Life', 'is']]
```
+ 리스트 인덱싱 & 슬라이싱
  1. 인덱싱 (Indexing)
  ```python
  >>> a = [1, 2, 3]
  >>> a[0]
  1
  >>> a[0] + a[2]
  4
  >>> a[-1]
  3
  ```
  ```python
  >>> a = [1, 2, 3, ['a', 'b', 'c']]
  >>> a[0]
  1
  >>> a[-1]
  ['a', 'b', 'c']
  >>> a[3]
  ['a', 'b', 'c']
  ```
  ```python
  >>> a = [1, 2, 3, ['a', 'b', 'c']]
  >>> a[-1][0]
  'a'
  >>> a[-1][1]
  'b'
  >>> a[-1][2]
  'c'
  ```
  ```python
  # 3중 리스트 인덱싱
  >>> a = [1, 2, ['a', 'b', ['Life', 'is']]]
  >>> a[2][2][0]
  'Life'
  ```
  2. 슬라이싱 (Slicing)
  ```python
  >>> a = [1, 2, 3, 4, 5]
  >>> b = a[:2]
  >>> c = a[2:]
  >>> b
  [1, 2]
  >>> c
  [3, 4, 5]
  ```
  ```python
  # 중첩 리스트 슬라이싱
  >>> a = [1, 2, 3, ['a', 'b', 'c'], 4, 5]
  >>> a[3][:2]
  ['a', 'b']
  ```
+ 리스트 연산자
  1. 더하기 (+)
  ```python
  >>> a = [1, 2, 3]
  >>> b = [4, 5, 6]
  >>> a + b
  [1, 2, 3, 4, 5, 6]
  ```
  2. 반복하기 (*)
  ```python
  >>> a = [1, 2, 3]
  >>> a * 3
  [1, 2, 3, 1, 2, 3, 1, 2, 3]
  ```
  ```python
  # 초보자가 범하기 쉬운 연산 오류 - 자료형 불일치 오류
  >>> a = [1, 2, 3]
  >>> a[2] + "hi"
  Traceback (most recent call last):
    File "<stuin>", line 1, in <module>
  TypeError: unspported operand type(s) for +: 'int' and 'str'
  >>> str(a[2]) + "hi"
  '3hi'
  ```
+ 리스트의 수정, 변경 및 삭제
  1. 하나의 값 수정
  ```python
  >>> a = [1, 2, 3]
  >>> a[2] = 4
  >>> a
  [1, 2, 4]
  ```
  2. 연속된 범위의 값 수정
  ```python
  >>> a = [1, 2, 4]
  >>> a[1:2]
  [2]
  >>> a[1:2] = ['a', 'b', 'c']
  >>> a
  [1, 'a', 'b', 'c', 4]
  ```
  ```python
  # 주의할 점
  # a[1] = ['a', 'b', 'c']는 두 번째 요소를 리스트 값으로 변경하는 것
  # a[1:2] = ['a', 'b', 'c']는 해당 리스트 범위의 값을 'a', 'b', 'c' 세 개의 값으로 변경하는 것
  >>> a = [1, 2, 4]
  >>> a[1] = ['a', 'b', 'c']
  >>> a
  [1, ['a', 'b', 'c'], 4]
  ```
  3. [] 를 통한 요소 삭제
  ```python
  >>> a = [1, 'a', 'b', 'c', 4]
  >>> a[1:3] = []
  >>> a
  [1, 'c', 4]
  ```
  4. del 함수를 통한 요소 삭제
  ```python
  >>> a = [1, 'c', 4]
  >>> del a[1]
  >>> a
  [1, 4]
  ```
+ 리스트 관련 함수
  1. 요소 추가 (append)
  ```python
  >>> a = [1, 2, 3]
  >>> a.append(4)
  >>> a
  [1, 2, 3, 4]
  ```
  ```python
  >>> a.append([5, 6])
  >>> a
  [1, 2, 3, 4, [5, 6]]
  ```
  2. 정렬 (sort)
  ```python
  >>> a = [1, 4, 3, 2]
  >>> a.sort()
  >>> a
  [1, 2, 3, 4]
  ```
  ```python
  >>> a = ['a', 'c', 'b']
  >>> a.sort()
  >>> a
  ['a', 'b', 'c']
  ```
  3. 뒤집기 (reverse)
  ```python
  >>> a = ['a', 'c', 'b']
  >>> a.reverse()
  >>> a
  ['b', 'c', 'a']
  ```
  4. 위치 반환 (index)
  ```python
  >>> a = [1, 2, 3]
  >>> a.index(3)
  2
  >>> a.index(1)
  0
  >>> a.index(0)
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  ValueError: 0 is not in list
  ```
  5. 요소 삽입 (insert)
  ```python
  >>> a = [1, 2, 3]
  >>> a.insert(0, 4)
  >>> a
  [4, 1, 2, 3]
  >>> a.insert(3, 5)
  >>> a
  [4, 1, 2, 5, 3]
  ```
  6. 요소 제거 (remove)
  ```python
  >>> a = [1, 2, 3, 1, 2, 3]
  >>> a.remove(3)
  >>> a
  [1, 2, 1, 2, 3]
  >>> a.remove(3)
  >>> a
  [1, 2, 1, 2]
  ```
  7. 요소 끄집어내기 (pop)
  ```python
  >>> a = [1, 2, 3]
  >>> a.pop()
  3
  >>> a
  [1, 2]
  ```
  ```python
  >>> a = [1, 2, 3]
  >>> a.pop(1)
  2
  >>> a
  [1, 3]
  ```
  8. 요소 x의 개수 세기 (count)
  ```python
  >>> a = [1, 2, 3, 1]
  >>> a.count(1)
  2
  ```
  9. 리스트 확장 (extend)
  ```python
  # extend(x)에서 x에는 리스트만 올 수 있음
  >>> a = [1, 2, 3]
  >>> a.extend([4, 5])
  >>> a
  [1, 2, 3, 4, 5]
  >>> b = [6, 7]
  >>> a.extend(b)
  >>> a
  [1, 2, 3, 4, 5, 6, 7]
  ```
+ 연습 문제
  1. 리스트 인덱싱
  ```python
  >>> a = ['Life', 'is', 'too', 'short', 'you', 'need', 'python']
  >>> b = a[4] + " " + a[2]
  >>> print(b)
  you too
  ```
  2. 리스트 조인
  ```python
  >>> a = ['Life', 'is', 'too', 'short']
  >>> b = " ".join(a)
  >>> print(b)
  Life is too short
  ```
  3. 리스트의 갯수
  ```python
  >>> a = [1, 2, 3]
  >>> len(a)
  3
  ```
  4. 리스트 append & extend
  ```python
  >>> a = [1, 2, 3]
  >>> a.append([4, 5])
  >>> a
  [1, 2, 3, [4, 5]]
  ```
  ```python
  >>> a = [1, 2, 3]
  >>> a.extend([4, 5])
  >>> a
  [1, 2, 3, 4, 5]
  ```
  ```python
  # append를 활용하면 [4, 5] 리스트 자체가 요소 값으로 삽입
  # extend를 활용하면 [4, 5] 리스트 내 값(4, 5)이 요소 값으로 삽입
  ```
  5. 리스트 정렬
  ```python
  >>> a = [1, 3, 5, 4, 2]
  >>> a.sort()
  >>> a
  [1, 2, 3, 4, 5]
  >>> a.reverse()
  >>> a
  [5, 4, 3, 2, 1]
  ```
  ```python
  >>> a = [1, 3, 5, 4, 2]
  >>> a.sort(reverse=True)
  >>> print(a)
  [5, 4, 3, 2, 1]
  ```
  6. 리스트 삭제
  ```python
  >>> a = [1, 2, 3, 4, 5]
  >>> a.remove(2)
  >>> a.remove(4)
  >>> a
  [1, 3, 5]
  ```
  ```python
  >>> a = [1, 2, 3, 4, 5]
  >>> a.pop(1)
  >>> a.pop(2)
  >>> a
  [1, 3, 5]
  ```
  ```python
  >>> a = [1, 2, 3, 4, 5]
  >>> del a[1]
  >>> del a[2]
  >>> a
  [1, 3, 5]
  ```
---
#### 02-4. 튜플 자료형
+ 튜플(tuple) 형태
```python
>>> t1 = ()
>>> t2 = (1,)
>>> t3 = (1, 2, 3)
>>> t4 = 1, 2, 3
>>> t5 = ('a', 'b', ('ab', 'cd'))
```
+ 튜플의 특징
튜플의 요소값은 한 번 정하면 지우거나 변경할 수 없음
  1. 튜플 요소값 삭제 시 오류
  ```python
  >>> t1 = (1, 2, 'a', 'b')
  >>> del t1[0]
  Traceback (most recent call last):
    File "<stdin>', line 1, in <module"
  TypeError: 'tuple' object doesn't support item deletion
  ```
  2. 튜플 요소값 변경 시 오류
  ```python
  >>> t1 = (1, 2, 'a', 'b')
  >>> t1[0] = 'c'
  Traceback (most recent call last):
    File "<stdin>', line 1, in <module"
  TypeError: 'tuple' object does not support item assignment
  ```
+ 튜플의 인덱싱과 슬라이싱, 더하기(+)와 곱하기(*)
  1. 인덱싱
  ```python
  >>> t1 = (1, 2, 'a', 'b')
  >>> t1[0]
  1
  >>> t1[3]
  'b'
  ```
  2. 슬라이싱
  ```python
  >>> t1 = (1, 2, 'a', 'b')
  >>> t1[1:]
  (2, 'a', 'b')
  ```
  3. 더하기
  ```python
  >>> t1 = (1, 2, 'a', 'b')
  >>> t2 = (3, 4)
  >>> t1 + t2
  (1, 2, 'a', 'b', 3, 4)
  ```
  4. 곱하기
  ```python
  >>> t2 = (3, 4)
  >>> t2 * 3
  (3, 4, 3, 4, 3, 4)
  ```
+ 연습 문제
  1. 튜플 작성
  ```python
  >>> t1 = (3,)
  >>> t1
  (3,)
  ```
  ```python
  >>> t1 = 3,
  >>> t1
  (3,)
  ```
  2. 튜플 변경
  ```python
  >>> a = (1, 2, 3)
  >>> a[1] = 4
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  TypeError: 'tuple' object does not support item assignment
  
  # 튜플 자료형은 요소값 변경을 지원하지 않음
  ```
  3. 튜플 추가
  ```python
  >>> t1 = (1, 2, 3)
  >>> t1 = t1 + (4,)
  >>> t1
  (1, 2, 3, 4)
  ```
  ```python
  >>> t1 = (1, 2, 3)
  >>> id(t1)
  5751512
  >>> t1 = t1 + (4,)
  >>> t1
  (1, 2, 3, 4)
  >>> id(t1)
  5728896
  ```
---
#### 02-5. 딕셔너리 자료형
+ 딕셔너리 작성법
```python
>>> dic = {'name':'pey', 'phone':'0119993323', 'birth':'1118'}
>>> a = {1: 'hi'}
>>> a = {'a': [1, 2, 3]}
```
+ 딕셔너리 요소 추가 & 삭제
  1. 추가
  ```python
  >>> a = {1: 'a'}
  >>> a[2] = 'b'
  >>> a
  {1: 'a', 2: 'b'}
  >>> a['name'] = 'pey'
  >>> a
  {1: 'a', 2: 'b', 'name': 'pey'}
  >>> a[3] = [1, 2, 3]
  >>> a
  {1: 'a', 2: 'b', 'name': 'pey', 3: [1, 2, 3]}
  ```
  2. 삭제
  ```python
  >>> del a[1]
  >>> a
  {2: 'b', 'name': 'pey', 3: [1, 2, 3]}
  ```
+ 딕셔너리 활용법
  1. Key 사용해 Value 얻기
  ```python
  >>> grade = {'pey': 10, 'julliet': 99}
  >>> grade['pey']
  10
  >>> grade['julliet']
  99
  ```
  ```python
  >>> a = {1: 'a', 2: 'b'}
  >>> a[1]
  'a'
  >>> a[2]
  'b'
  ```
  ```python
  >>> a = {'a': 1, 'b': 2}
  >>> a['a']
  1
  >>> a['b']
  2
  ```
  ```python
  >>> dic = {'name': 'pey', 'phone': '0119993323', 'birth': '1118'}
  >>> dic['name']
  'pey'
  >>> dic['phone']
  '0119993323'
  >>> dic['birth']
  '1118'
  ```
  2. 작성 시 주의사항
  ```python
  # Dictionary Key는 고유한 값이므로, 중복 설정 시 하나를 제외한 나머지 Value는 모두 무시된다.
  
  >>> a = {1: 'a', 1: 'b'}
  >>> a
  {1: 'b'}
  ```
  ```python
  # 특정 자료형의 Dictionary Key 사용 가능 여부는 해당 자료형이 변하는 값인지, 변하지 않는 값인지에 달려있다.
  # 그에 따라 리스트, 딕셔너리는 Key로 쓸 수 없는 반면, 튜플은 Key로 사용할 수 있다.
  
  >>> a  {[1, 2] : 'hi'}
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  TypeError: unhashable type: 'list'
  ```
+ 딕셔너리 관련 함수
  1. Key 리스트 만들기 (keys)
  ```python
  >>> a = {'name': 'pey', 'phone': '0119993323', 'birth': '1118'}
  >>> a.keys()
  dict_keys(['name', 'phone', 'birth'])
  ```
  ```python
  >>> for k in a.keys():
  ...   print(k)
  ...
  name
  phone
  birth
  ```
  ```python
  >>> list(a.keys())
  ['name', 'phone', 'birth']
  ```
  2. Value 리스트 만들기 (values)
  ```python
  >>> a = {'name': 'pey', 'phone': '0119993323', 'birth': '1118'}
  >>> a.values()
  dict_values(['pey', '0119993323', '1118'])
  ```
  3. Key, Value 쌍 얻기 (items)
  ```python
  >>> a = {'name': 'pey', 'phone': '0119993323', 'birth': '1118'}
  >>> a.items()
  dict_items([('name', 'pey'), ('phone', '0119993323'), ('birth', '1118')])
  ```
  4. Key: Value 쌍 모두 지우기 (clear)
  ```python
  >>> a = {'name': 'pey', 'phone': '0119993323', 'birth': '1118'}
  >>> a.clear()
  >>> a
  {}
  ```
  5. Key로 Value 얻기 (get)
  ```python
  >>> a = {'name': 'pey', 'phone': '0119993323', 'birth': '1118'}
  >>> a.get('name')
  'pey'
  >>> a.get('phone')
  '0119993323'
  ```
  ```python
  >>> a = {'name': 'pey', 'phone': '0119993323', 'birth': '1118'}
  >>> a.get('nokey')
  >>> a['nokey']
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  KeyError: 'nokey'
  ```
  ```python
  >>> a.get('foo', 'bar')
  'bar'
  ```
  6. 해당 Key가 딕셔너리 안에 있는지 조사하기 (in)
  ```python
  >>> a = {'name': 'pey', 'phone': '0119993323', 'birth': '1118'}
  >>> 'name' in a
  True
  >>> 'email' in a
  False
  ```
+ 연습 문제
  1. 딕셔너리 만들기
  ```python
  >>> a = {'name': '홍길동', 'birth': '1128', 'age': 30}
  >>> a
  {'name': '홍길동', 'birth': '1128', 'age': 30}
  ```
  ```python
  >>> a = dict()
  >>> a['name'] = '홍길동'
  >>> a['birth'] = '1128'
  >>> a['age'] = 30
  >>> a
  {'name': '홍길동', 'birth': '1128', 'age': 30}
  ```
  2. 딕셔너리 오류
  ```python
  >>> a = dict()
  >>> a
  {}
  
  # 오류가 발생하는 경우와 이유
  # a['name'] = 'python' > 작동
  # a[('a',)] = 'python' > 작동
  # a[[1]] = 'python' > 형 오류(TypeError) 발생, 리스트는 값이 변하는(mutable) 자료형이므로 Key로 사용할 수 없음.  
  # a[250] = 'python' > 작동
  ```
  3. 딕셔너리 값 추출1
  ```python
  >>> a = {'A': 90, 'B': 80, 'C': 70}
  >>> a.get('B')
  80
  >>> del a['B']
  >>> a
  {'A': 90, 'C': 70}
  ```
  4. 딕셔너리 값 추출2
  ```python
  >>> a = {'A': 90, 'B': 80}
  >>> a['C']
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  KeyError: 'C'
  ```
  ```python
  >>> a = {'A': 90, 'B': 80}
  >>> a.get('C', 70)
  70
  ```
  5. 딕셔너리 최소값
  ```python
  >>> a = {'A': 90, 'B': 80, 'C': 70}
  >>> min(a.values())
  70
  ```
  6. 딕셔너리 리스트 변환
  ```python
  >>> a = {'A': 90, 'B': 80, 'C': 70}
  >>> list(a.items())
  [('A', 90), ('B', 80), ('C', 70)]
  ```
