# Python-Basics  
점프 투 파이썬
-------------
Link: [점프 투 파이썬](https://wikidocs.net/book/1)
### 05장. 파이썬 날개달기
#### 05-1. 클래스
+ 클래스와 객체  
  + 클래스(class)는 특정한 것을 동일하게 계속 만들어낼 수 있는 설계 도면과 같은 것이다.  
  + 객체(object)는 클래스에 의해 만들어진 피조물을 뜻하며, 객체 별로 독립성을 갖는다.
  + 파이썬 클래스 예시
    ```python
    >>> class Cookie:
    ...     pass
    ...
    >>> a = Cookie()
    >>> b = Cookie()
    ```
+ 사칙연산 클래스 만들기
  1. 클래스 동작 방식 구상
  ```python
  # 클래스 구상 예시
  # 사칙연산을 수행하는 클래스(FourCal)를 객체 중심으로 접근
  
  a. 객체 생성
  >>> a = FourCal()
  b. 객체 데이터(4, 2) 입력
  >>> a.setdata(4, 2)
  c-1. 기능 수행 - 더하기(4 + 2)
  >>> print(a.sum())
  6
  c-2. 기능 수행 - 곱하기(4 * 2)
  >>> print(a.mul())
  8
  c-3. 기능 수행 - 빼기(4 - 2)
  >>> print(a.sub())
  2
  c-4. 기능 수행 - 나누기(4 / 2)
  >>> print(a.div())
  2
  ```
  2. 클래스 구조 만들기
  ```python
  # 클래스 생성
  >>> class FourCal:
  ...     pass
  ...
  >>>
  ```
  ```python
  # 객체 생성
  >>> a = FourCal()
  >>> type(a)  # type함수는 파이썬 내장 함수로 객체의 타입을 출력한다.
  <class '__main__.FourCal'>
  ```
  3. 객체 데이터 입력 (사칙연산용 숫자 지정)
  ```python
  >>> class FourCal:
  ...     def setdata(self, first, second):  # 메서드 매개변수
  ...         self.first = first             # 메서드 수행문
  ...         self.second = second           # 메서드 수행문
  ...
  >>>
  ```
    1. setdata 메서드의 매개변수  
    _**setdata 메서드의 첫 번째 매개변수 'self'에는 setdata를 호출한 객체 a가 자동으로 전달된다.**_  
    첫 번째 매개변수명은 관례적으로 `self`를 사용한다.
      ```python
      >>> a = FourCal()  # 객체 a 생성
      >>> a.setdata(4, 2)  # 객체 a를 통해 setdata 메서드 호출
      ```
      * 메서드의 또 다른 호출 방법
        ```python
        # 클래스명.메서드
        >>> a = FourCal()
        >>> FourCal.setdata(a, 4, 2)  # 객체 a를 입력 인수로 꼭 넣어줘야 한다.
        ```
    2. setdata 메서드의 수행문
    ```python
    # 객체 변수는 아래와 같이 만들어진다.
    객체.객체변수 = 값
    ```
    ```python
    # setdata 메서드의 객체변수
    self.first = first
    self.second = second
    ```
    ```python
    # 객체 a에 입력값 (4, 2)를 지정했을 때의 객체변수
    ```python
    a.first = 4
    a.second = 2
    ```
    ```python
    # 객체변수 생성 예시
    # 객체변수(instance variable)는 객체에 정의된 변수를 의미하며, 객체 간 서로 공유되지 않는다.
    >>> a = FourCal()
    >>> a.setdata(4, 2)
    >>> print(a.first)
    4
    >>> print(a.second)
    2
    >>> b = FourCal()
    >>> b.setdata(3, 7)
    >>> print(b.first)
    3   # 객체 a의 first 변수값(4)과 다르다.
    >>> print(b.second)
    7   # 객체 a의 second 변수값(2)과 다르다.
    ```
  4. 더하기 기능 만들기
  ```python
  # FourCal 클래스에 sum 메서드 추가
  >>> class FourCal:
  ...     def setdata(self, first, second):
  ...         self.first = first
  ...         self.second = second
  ...     def sum(self):
  ...         result = self.first + self.second
  ...         return result 
  ...
  >>>
  ```
  ```python
  >>> a = FourCal()
  >>> a.setdata(4, 2)
  >>> print(a.sum())
  6
  ```
  ```python
  # sum method 동작 구조
  def sum(self):      # 매개변수 self
      result = self.first + self.second
      return result   # 리턴값 result
  
  # 객체 a를 통해 sum 메서드 수행
  result = self.first + self.second
  result = a.first + a.second
  
  # sum 메서드 호출 전 a.setdata(4, 2) 선 호출
  result = a.first + a.second
  result = 4 + 2
  
  # 따라서 a.sum()을 호출하면 6을 리턴
  >>> print(a.sum())
  6
  ```
  5. 곱하기, 빼기, 나누기 기능 만들기
  ```python
  >>> class FourCal:
  ...     def setdata(self, first, second):
  ...         self.first = first
  ...         self.second = second
  ...     def sum(self):
  ...         result = self.first + self.second
  ...         return result
  ...     def mul(self):
  ...         result = self.first * self.second
  ...         return result
  ...     def sub(self):
  ...         result = self.first - self.second
  ...         return result
  ...     def div(self):
  ...         result = self.first / self.second
  ...         return result
  ...
  >>>
  ```
  ```python
  # 기능 별 정상 동작 여부 확인
  >>> a = FourCal()
  >>> b = FourCal()
  >>> a.setdata(4, 2)
  >>> b.setdata(3, 7)
  >>> a.sum()
  6
  >>> a.mul()
  8
  >>> a.sub()
  2
  >>> a.div()
  2.0
  >>> b.sum()
  10
  >>> b.mul()
  21
  >>> b.sub()
  -4
  >>> b.div()
  0.428571...
  ```
+ 생성자 (Constructor)
```python
# FourCal 클래스의 인스턴스 a에 setdata 메서드를 수행하지 않고 sum 메서드를 수행하면 오류 발생
# 객체 a 생성 후, setdata 메서드를 수행해야 객체변수 first와 second가 생성되기 때문
>>> a = FourCal()
>>> a.sum()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "<stdin>", line 6, in sum
AttributeError: 'FourCal' object has no attribute 'first'
```
```python
# 객체에 초기값을 설정할 필요가 있을 때는, 메서드 호출 방식보다는 생성자 구현이 안전한 방법
# 생성자(constructor)란 객체가 생성될 때 자동으로 호출되는 메서드를 의미
# 파이썬 메서드명으로 '__init__'을 사용하면 해당 메서드를 생성자로 인식
# FourCal 클래스에 생성자 추가
>>> class FourCal:
...     def __init__(self, first, second):
...         self.first = first
...         self.second = second
...     def setdata(self, first, second):
...         self.first = first
...         self.second = second
...     def sum(self):
...         result = self.first + self.second
...         return result
...     def mul(self):
...         result = self.first * self.second
...         return result
...     def sub(self):
...         result = self.first - self.second
...         return result
...     def div(self):
...         result = self.first / self.second
...         return result
...
>>>
```
```python
# __init__ 메서드 상세
# setdata 메서드와 수행문은 동일하지만, 생성자 메서드 이름(__init__)으로 인해 객체가 생성되는 시점에 메서드가 자동으로 호출된다.
def __init__(self, first, second):
    self.first = first
    self.second = second
```
```python
# 생성자 추가 후 기존 방법으로 객체 a 생성 시 오류 발생
# 생성자 매개변수인 fisrt, second에 해당되는 값이 전달되지 않았기 때문
>>> a = FourCal()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: __init__() missing 2 required positional arguments: 'first' and 'second'

# 객체 생성 시 first와 second에 해당되는 값을 전달함으로써 오류를 해결할 수 있다.
# 전달된 값을 토대로 first와 second라는 객체변수가 생성된다.
>>> a = FourCal(4, 2)
>>> print(a.first)
4
>>> print(a.second)
2
```
매개변수 별로 대입된 값들

**매개변수** | **값**
------------ | ------
self | 생성되는 객체(a)
first | 4
second | 2

```python
# sum, div 등의 사칙연산 메서드 동작 여부 확인
>>> a = FourCal(4, 2)
>>> a.sum()
6
>>> a.div()
2.0
```
+ 클래스의 상속
//
