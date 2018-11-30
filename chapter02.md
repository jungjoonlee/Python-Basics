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
