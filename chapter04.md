# Python-Basics
점프 투 파이썬
-------------
Link: [점프 투 파이썬](https://wikidocs.net/book/1)
### 04장. 프로그램의 입력과 출력은 어떻게 해야 할까?
#### 04-1. 함수
+ 파이썬 함수의 구조
```python
def 함수명(매개변수):
    <수행할 문장1>
    <수행할 문장2>
    ...
````
```python
>>> def sum(a, b):
...     return a + b
...
>>>
```
```python
>>> a = 3
>>> b = 4
>>> c = sum(a, b)
>>> print(c)
7
```
  + 매개변수와 인수
  ```python
  def sume(a, b):  # 매개변수는 함수에 입력으로 전달된 값을 받는 변수를 의미함. a,b는 매개변수(parameter).
      return a + b
      
  print(sum(3, 4))  # 인수는 함수를 호출할 때 전달하는 입력값을 의미함. 3, 4 는 인수(argument).
  ```
+ 입력값과 결과값에 따른 함수의 형태
  1. 일반적인 함수: 입력값과 결과값이 있는 함수
  ```python
  def 함수이름(매개변수):
      <수행할 문장>
      ...
      return 결과값
  ```
  ```python
  # 일반적인 함수 예시
  def sum(a, b):
      result = a + b
      return result
  ```
  ```python
  >>> a = sum(3, 4)
  >>> print(a)
  7
  ```
  ```python
  # 입력값과 결과값이 있는 함수의 사용법
  결과값을 받을 변수 = 함수명(입력 인수1, 입력 인수2, ...)
  ```
  2. 입력값이 없는 함수
  ```python
  >>> def say():
  ...     return 'Hi'
  ...
  >>> a = say()
  >>> print(a)
  Hi
  ```
  ```python
  # 입력값이 없고 결과값만 있는 함수의 사용법
  결과값을 받을 변수 = 함수명()
  ```
  3. 결과값이 없는 함수
  ```python
  >>> def sum(a, b):
  ...     print("%d, %d의 합은 %d입니다." % (a, b, a + b))
  ...
  >>> sum(3, 4)
  3, 4의 합은 7입니다.
  ```
  ```python
  # 입력값만 있고 결과값은 없는 함수의 사용법
  함수명(입력 인수1, 입력 인수2, ...)
  ```
  ```python
  >>> a = sum(3, 4)
  3, 4의 합은 7입니다.  # print문은 함수의 구성 요소인 <수행할 문장>에 해당하는 부분으로 결과값은 없음. 결과값은 return 명령어로만 돌려받을 수 있음.
  >>> print(a)
  None
  ```
  4. 입력값도 결과값도 없는 함수
  ```python
  >>> def say():
  ...     print('Hi')
  ...
  >>> say()
  Hi
  ```
  ```python
  # 입력값도 결과값도 없는 함수의 사용법
  함수명()
  ```
+ 매개변수 지정하여 호출하기
```python
>>> def sum(a, b):
...     return a + b
...
```
```python
>>> sum(a=3, b=7)  # a에 3, b에 7을 전달
10
```
```python
>>> sum(b=5, a=3)  # b에 5, a에 3을 전달
8
```
+ 입력값이 몇 개가 될지 모를 때는 어떻게 해야 할까?
```python
def 함수이름(*매개변수):
    <수행할 문장>
    ...
```
  1. 여러 개의 입력값을 받는 함수 만들기
  ```python
  # 예시1
  >>> def sum_many(*args):
  ...     sum = 0
  ...     for i in args:
  ...         sum = sum + i
  ...     return sum
  ...
  >>>
  ```
  ```python
  >>> result = sum_many(1, 2, 3)
  >>> print(result)
  6
  >>> result = sum_many(1, 2, 3, 4, 5, 6, 7, 8, 9, 10)
  >>> print(result)
  55
  ```
  ```python
  # 예시2
  >>> def sum_mul(choice, *args):
  ...     if choice == "sum":
  ...         result = 0
  ...         for i in args:
  ...             result = result + i
  ...     elif choice == "mul":
  ...         result = 1
  ...         for i in args:
  ...             result = result * i
  ...     return result
  ...
  >>>
  ```
  ```python
  >>> result = sum_mul('sum', 1, 2, 3, 4, 5)
  >>> print(result)
  15
  >>> result = sum_mul('mul', 1, 2, 3, 4, 5)
  >>> print(result)
  120
  ```
  2. 키워드 파라미터 kwargs
  ```python
  # 예시1
  >>> def func(**kwargs):
  ...     print(kwargs)
  ...
  >>> func(a=1)
  {'a': 1}
  >>> func(name='foo', age=3)
  {'name': 'foo', 'age': 3}
  ```
  ```python
  # 예시2
  >>> def func(*args, **kwargs):
  ...     print(args)
  ...     print(kwargs)
  ...
  >>> func(1, 2, 3, name='foo', age=3)
  (1, 2, 3)
  {'name': 'foo', 'age': 3}
  ```
  ```python
  >>> func(1, 2, 3, name='foo', age=3, 4, 5)
    File "<stdin>", line 1
  SyntaxError: positional argument follows keyword argument
  >>> func(1, 2, 3, 4, 5, name='foo', age=3)
  (1, 2, 3, 4, 5)
  {'name': 'foo', 'age': 3}
  ```
+ 함수의 결과값은 언제나 하나이다
```python
>>> def sum_and_mul(a, b):
...     return a+b, a*b
```
```python
>>> result = sum_and_mul(3, 4)
>>> result
(7, 12)
```
```python
>>> sum, mul = sum_and_mul(3, 4)
>>> sum, mul
(7, 12)
```
```python
>>> def sum_and_mul(a, b):
...     return a + b
...     return a * b
...
>>> result = sum_and_mul(2, 3)
>>> print(result)
5  # 두 번째 return문인 `return a * b`는 실행되지 않았음
```
```python
# 위 함수는 다음 함수와 완전히 동일함.
>>> def sum_and_mul(a, b):
...     return a + b
...
>>> result = sum_and_mul(2, 3)
>>> print(result)
5
```
  + return의 또 다른 쓰임새
  ```python
  >>> def say_nick(nick):
  ...     if nick == "바보":
  ...         return
  ...     print("나의 별명은 %s입니다." % nick)
  ...
  >>>
  ```
  ```python
  >>> say_nick('야호')
  나의 별명은 야호입니다.
  >>> say_nick('바보')
  >>>
  ```
+ 매개변수에 초깃값 미리 설정하기
```python
def say_myself(name, old, man=True):
    print("나의 이름은 %s입니다." % name)
    print("나이는 %d살입니다." % old)
    if man:
        print("남자입니다.")
    else:
        print("여자입니다.")
```
```python
say_myself("박응용", 27)
say_myself("박응용", 27, True)
# 두 가지 방법 모두 동일한 결과 출력
나의 이름은 박응용입니다.
나이는 27살입니다.
남자입니다.
나의 이름은 박응용입니다.
나이는 27살입니다.
남자입니다.
```
```python
say_myself("박응선", 27, False)
나의 이름은 박응선입니다.
나이는 27살입니다.
여자입니다.
```
  + 함수 매개변수에 초깃값을 설정할 때 주의할 사항
  ```python
  def say_myself(name, man=True, old):
      print("나의 이름은 %s입니다." % name)
      print("나이는 %d살입니다." % old)
      if man:
          print("남자입니다.")
      else:
          print("여자입니다.")
  
  say_myself("박응용", 27)
  SyntaxError: non-default arguments follows default argument
  ```
+ 함수 안에서 선언된 변수의 효력 범위
```python
# vartest.py
a = 1
def vartest(a):
    a = a + 1
    
vartest(a)  # vartest함수의 매개변수 a와 함수 밖의 변수 a는 전혀 상관이 없는 별개의 변수들임.
print(a)
1
```
```python
# vartest_error.py
def vartest(a):
    a = a + 1
    
vartest(3)
print(a)
Traceback (most recent call last):
  File "/vartest_error.py", line 7, in <module>
    print(a)
NameError: name 'a' is not defined
```
  + 함수 안에서 함수 밖의 변수를 변경하는 방법
  1. return 이용하기
  ```python
  # vartest_return.py
  a = 1
  def vartest(a):
      a = a + 1
      return a
      
  a = vartest(a)
  print(a)
  2
  ```
  2. global 명령어 이용하기
  ```python
  # vartest_global.py
  a = 1
  def vartest():
      global a  # global 명령어를 통해 함수 밖의 a변수를 직접 사용한다는 의미임.
      a = a + 1
  
  vartest()
  print(a)
  2
  ```
+ lambda
```python
# lambda 사용법
lambda 매개변수1, 매개변수2, ... : 매개변수를 이용한 표현식
```
```python
# 예제
>>> sum = lambda a, b: a+b
>>> sum(3, 4)
7
```
```python
# 위 예제는 def를 사용한 아래 함수와 동일한 일을 수행한다.
>>> def sum(a, b):
...     return a + b
...
>>> sum(3, 4)
7
```
```python
# lambda가 포함된 리스트 예제
>>> myList = [lambda a,b:a+b, lambda a,b:a*b]
>>> myList
[<function <lambda> at 0x00E99468>, <function <lambda> at 0x00E994F8>]
```
```python
>>> myList[0]
<function <lambda> at 0x00E99468>
>>> myList[0](3, 4)
7
```
```python
>>> myList[1]
<function <lambda> at 0x00E994F8>
>>> myList[1](3, 4)
12
```
+ 연습문제
  1. 홀수 짝수 판별
  ```python
  >>> def is_odd(a):
  ...     if a % 2 == 0:
  ...         print("%d는(은) 짝수이다." % a)
  ...     else:
  ...         print("%d는(은) 홀수이다." % a)
  ...
  >>> is_odd(3)
  3는(은) 홀수이다.
  >>> is_odd(4)
  4는(은) 짝수이다.
  ```
  ```python
  # 교재 풀이1
  >>> def is_odd(number):
  ...     if number % 2 == 1:
  ...         return True
  ...     else:
  ...         return False
  ...
  >>> is_odd(3)
  True
  >>> is_odd(4)
  False
  ```
  ```python
  # 교재 풀이2
  >>> is_odd = lambda number: True if number % 2 ==1 else False
  >>> is_odd(3)
  True
  ```
  2. 평균값 계산
  ```python
  >>> def avg_numbers(*args):
  ...     result = 0
  ...     for i in args:
  ...         result += i
  ...     return result / len(args)
  ...
  >>> avg_numbers(1, 2)
  1.5
  >>> avg_numbers(1, 2, 3, 4, 5)
  3.0
  ```
  3. 구구단 출력
  ```python
  >>> def multiplication(n):
  ...     N = []
  ...     for i in range(1, 10):
  ...         N.append(i * n)
  ...     return N
  ...
  >>> multiplication(2)
  [2, 4, 6, 8, 10, 12, 14, 16, 18]
  ```
  ```python
  # 교재 풀이
  ```python
  >>> def gugu(n):
  ...     for i in range(1, 10):
  ...         print(n * i)
  ...
  >>> gugu(2)
  2
  4
  6
  8
  10
  12
  14
  16
  18
  ```
  4. 피보나치
  ```python
  def fib(n):
      if n == 0 : return 0
      if n == 1 : return 1
      return fib(n-2) + fib(n-1)
  
  for i in range(10):
      print(fib(i))
  0
  1
  1
  2
  3
  5
  8
  13
  21
  34
  ```
  5. 5보다 큰 수만
  ```python
  >>> def myfunc(numbers):
  ...     result = []
  ...     for number in numbers:
  ...         if number > 5:
  ...             result.append(number)
  ...     return result
  ...
  >>> myfunc([2, 3, 4, 5, 6, 7, 8])
  [6, 7, 8]
  ```
  ```python
  # 위 함수를 lambda 함수로 변경
  >>> myfunc = lambda numbers: [number for number in numbers if number > 5]
  >>> myfunc([2, 3, 4, 5, 6, 7, 8])
  [6, 7, 8]
  ```
---
#### 04-2. 사용자 입력과 출력
+ 사용자 입력
  1. input의 사용
  ```python
  >>> a = input()
  Life is too short, you need python
  >>> a
  'Life is too short, you need python'  # input은 입력되는 모든 것을 문자열로 취급한다.
  >>>
  ```
  2. 프롬프트 띄워서 사용자 입력 받기
  ```python
  # prompt 사용법
  input("질문 내용")
  ```
  ```python
  # 예시
  >>> number = input("숫자를 입력하세요: ")
  숫자를 입력하세요: 3
  >>> print(number)
  3
  >>>
  ```
+ print 자세히 알기
  1. 큰따옴표(")로 둘러싸인 문자열은 + 연산과 동일하다
  ```python
  >>> print("life" "is" "too short")
  lifeistoo short
  >>> print("life"+"is"+"too short")
  lifeistoo short
  ```
  2. 문자열 띄어쓰기는 콤마로 한다
  ```python
  >>> print("life" "is" "too short")
  lifeistoo short
  >>> print("life", "is", "too short")
  life is too short
  ```
  3. 한 줄에 결과값 출력하기
  >>> for i in range(10):
  ...     print(i, end=' ')
  ...
  0 1 2 3 4 5 6 7 8 9 >>>
  ```
+ 연습문제
  1. 두 수의 합은?
  ```python
  input1 = input("첫번째 숫자를 입력하세요: ")
  input2 = input("두번째 숫자를 입력하세요: ")
  
  total = input1 + input2
  print("두 수의 합은 %s 입니다." % total)
  ```
  ```python
  # 프로그램 실행 결과
  첫번째 숫자를 입력하세요: 3
  두번째 숫자를 입력하세요: 6
  두 수의 합은 36 입니다  # 9가 아닌 36 리턴
  ```
  ```python
  # 프로그램 오류 수정
  input1 = input("첫번째 숫자를 입력하세요: ")
  input2 = input("두번째 숫자를 입력하세요: ")
  
  total = int(input1) + int(input2)
  print("두 수의 합은 %d 입니다." % total)
  ```
  ```python
  # 프로그램 실행 결과
  첫번째 숫자를 입력하세요: 3
  두번째 숫자를 입력하세요: 6
  두 수의 합은 9 입니다.
  ```
  2. 숫자의 총합
  ```python
  number = input("숫자를 입력하세요: ")
  
  number_list = number.split(',')
  total = 0
  for i in number_list:
      total += int(i)
  
  print("숫자들의 총합은 %d입니다." % total)
  ```
  ```python
  # 프로그램 실행 결과
  숫자를 입력하세요: 65,45,2,3,45,8
  숫자들의 총합은 168 입니다.
  ```
  3. 문자열 출력
  ```python
  # 3번이 출력결과가 다름
  >>> print("you", "need", "python")
  you need python
  # 1, 2, 4번은 출력결과가 동일함
  >>> print("you" "need" "python")  # 1번
  youneedpython
  >>> print("you"+"need"+"python")  # 2번
  youneedpython
  >>> print("".join(["you", "need", "python"]))
  youneedpython
  ```
  4. 한줄 구구단
  ```python
  n = input("구구단을 출력할 숫자를 입력하세요(2~9): ")
  for i in range(1, 10):
      print(int(n) * i, end=' ')
  ```
  ```python
  # 교재 풀이
  user_input = input("구구단을 출력할 숫자를 입력하세요(2~9): ")
  dan = int(user_input)
  for i in range(1, 10):
      print(i*dan, end=' ')
  ```
  ```python
  # 프로그램 실행 결과
  구구단을 출력할 숫자를 입력하세요(2~9): 2
  2 4 6 8 10 12 14 16 18
  ```
---
#### 04-3. 파일 읽고 쓰기
+ 파일 생성하기
```python
#파일 생성 방법
파일 객체 = open(파일 이름, 파일 열기 모드)
```
```python
# 파일 생성 예시
f = open('새파일.txt', 'w')
f.close()
```
  + 파일 열기 모드 종류
  
  파일 열기 모드 | 설명
  ------------- | ---
  r | 읽기모드 - 파일을 읽기만 할 때 사용
  w | 쓰기모드 - 파일에 내용을 쓸 때 사용
  a | 추가모드 - 파일의 마지막에 새로운 내용을 추가시킬 때 사용
  
+ 파일을 쓰기 모드로 열어 출력값 적기
```python
# writedata.py

f = open('C:/doit/새파일.txt', 'w')
for i in range(1, 11):
    data = "%d번째 줄입니다.\n" % i
    f.write(data)
f.close()
```
```python
# 비교 프로그램

for i in range(1, 11):
    data = "%d번째 줄입니다.\n" % i
    print(data)
```
+ 프로그램의 외부에 저장된 파일을 읽는 여러 가지 방법
  1. readline() 함수 이용하기
  ```python
  # readline.py
  
  f = open('C:/doit/새파일.txt', 'r')
  line = f.readline()
  print(line)
  f.close()
  ```
  ```python
  # 실행 결과
  1번째 줄입니다.
  
  ```
  ```python
  # readline_all.py
  
  f = open('C:/doit/새파일.txt', 'r')
  while True:
      line = f.readline()
      if not line: break
      print(line)
  f.close()
  ```
  ```python
  # 실행 결과
  1번째 줄입니다.
  
  2번째 줄입니다.
  
  3번째 줄입니다.
  
  4번째 줄입니다.
  
  5번째 줄입니다.
  
  6번째 줄입니다.
  
  7번째 줄입니다.
  
  8번째 줄입니다.
  
  9번째 줄입니다.
  
  10번째 줄입니다.
  
  ```python
  # 비교 프로그램
  while 1:
      data = input()  # readline_all.py와 비교 시 입력을 받는 방식만 다르다.
      if not data: break
      print(data)
  ```  
  2. readlines() 함수 이용하기
  ```python  
  f = open('C:/doit/새파일.txt', 'r')
  lines = f.readlines()
  for line in lines:
      print(line)
  f.close()
  ```
  3. read() 함수 이용하기
  ```python
  f = open('C:/doit/새파일.txt', 'r')
  data = f.read()  # f.read()는 파일의 내용 전체를 문자열로 리턴.
  print(data)
  f.close()
  ```
+ 파일에 새로운 내용 추가하기
```python
# adddata.py

f = open('C:/doit/새파일.txt', 'a')
for i in range(11, 20):
    data = "%d번째 줄입니다.\n" % i
    f.write(data)
f.close()
```
+ with문과 함께 사용하기
```python
# 지금까지 파일을 열고 닫아온 방식
f = open("foo.txt", 'w')
f.write("Life is too short, you need python")
f.close()
```
```python
# with문을 이용하여 재작성한 모습
with open("foo.txt", 'w') as f:  # with 블록을 벗어나는 순간 열려있던 파일 객체 f가 자동으로 close된다.
    f.write("Life is too short, you need python")
```
  + sys 모듈로 입력 인수 주기
  ```python
  # sys1.py
  import sys
  
  args = sys.argv[1:]
  for i in args:
      print(i)
  ```
  ```python
  # sys1.py 실행 결과 - window prompt 창으로 실행
  C:\doit>python sys1.py aaa bbb ccc
  aaa
  bbb
  ccc
  ```
  ```python
  # sys2.py
  import sys
  
  args = sys.argv[1:]
  for i in args:
      print(i.upper(), end=' ')
  ```
  ```python
  # sys2.py 실행 결과
  C:/doit>python sys2.py life is too short, you need python
  LIFE IS TOO SHORT, YOU NEED PYTHON
  ```
+ 연습문제
  1. 파일 읽고 출력하기
  ```python
  f1 = open("test.txt", 'w')
  f1.write("Life is too short")
  f1.close()  # 열려있는 파일 객체를 닫고 열어야 저장한 데이터를 읽을 수 있다.
  
  f2 = open("test.txt", 'r')
  print(f2.read())
  f2.close()
  ```
  ```python
  # 교재 풀이 - close를 명시할 필요가 없는 with구문 활용
  with open("test.txt", 'w') as f1:
      f1.write("Life is too short")
      
  with open("test.txt", 'r') as f2:
      print(f2.read())
  ```
  2. 파일저장
  ```python
  user_input = input("저장할 내용을 입력하세요: ")
  f = open("test.txt", 'a')  # 추가모드(a)로 파일을 열었을 때 해당 파일이 존재하지 않으면 새로운 파일이 생성된다.(쓰기모드(w)와 동일함) 
  f.write(user_input)
  f.write("\n")
  f.close()
  ```
  3. 역순 저장
  ```python
  # abc.txt 생성
  f = open("abc.txt", 'w')
  for factor in ["AAA", "BBB", "CCC", "DDD", "EEE"]:
      f.write(factor)
      f.write("\n")
  f.close()
  ```
  ```python
  # 역순 출력 프로그램
  f = open("abc.txt", 'r')
  lines = f.readlines()
  f.close
  
  lines.reverse() 
  
  f = open("abc.txt", 'w')
  for line in lines:
      line = line.strip()  # 포함되어 있는 줄바꿈 문자 제거
      f.write(line)
      f.write("\n")
  f.close()
  ```
  ```python
  # 역순 출력 프로그램 - 교재 풀이
  f = open("abc.txt", 'r')
  lines = f.readlines()
  f.close
  
  rlines = reversed(lines) 
  
  f = open("abc.txt", 'w')
  for line in rlines:
      line = line.strip()  # 포함되어 있는 줄바꿈 문자 제거
      f.write(line)
      f.write("\n")
  f.close()
  ```
  4. 파일 수정
  ```python
  # test.txt 생성
  with open('test.txt', 'w') as f:
      f.write("Life is too short\nyou need java")
  ```
  ```python
  # java => python 변경
  with open('test.txt', 'r') as f:
      content = f.read()
  
  content = content.reaplce('java', 'python')
  
  with open('test.txt', 'w') as f:
      f.write(content)
  ```
  5. 평균값 구하기
  ```python
  # sample.txt 생성
  f = open('sample.txt', 'w')
  for i in [70, 60, 55, 75, 95, 90, 80, 80, 85, 100]:
      f.write(i)
      f.write('\n')
  f.close()
  ```
  ```python
  # 평균값 산출 프로그램
  with open('sample.txt', 'r') as f:
      numbers = f.readlines()
  
  total = 0
  for number in numbers:
      total += int(number)
      # 교재 풀이 ==> 위 줄(853)을 두 단계로 구분하여 작성
      # score = int(number)
      # total += score
  avg_numbers = total / len(numbers)
  
  with open('result.txt', 'w') as f:
      f.write(str(avg_numbers))
  ```
  ```python
  # 실행 결과
  79.0
  ```
