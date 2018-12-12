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
