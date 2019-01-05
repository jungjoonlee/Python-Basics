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
```python
# 상속이란 클래스 생성 시, 다른 클래스의 기능을 물려받을 수 있게 하는 기능
# 상속 방법: 클래스 이름 뒤 괄호 안에 상속할 클래스명 기입
class 클래스명(상속할 클래스명)
# 상속 예시
>>> class MoreFourCal(FourCal):
...     pass
...
>>> a = MoreFourCal(4, 2)
>>> a.sum()
6
>>> a.mul()
8
>>> a.sub()
2
>>> a.div()
2.0
```
```python
# 상속받은 클래스만의 새로운 기능 추가
>>> class MoreFourCal(FourCal):
...     def pow(self):
...         result = self.first ** self.second
...         return result
...
>>> a = MoreFourCal(4, 2)
>>> a.pow()
16
```
  + 메서드 오버라이딩 (Method Overriding)
  ```python
  # FourCal클래스의 div메서드 수행 시, 0으로 나누면 ZeroDivisionError 발생
  >>> a = FourCal(4, 0)
  >>> a. div()
  Traceback (most recent call last):
    File "<studin>", line 1, in <module>
    File "<stdin>", line 18, in div
  ZeroDivisionError: division by zero
  ```
  ```python
  # 메서드 오버라이딩(overriding, 덮어쓰기)이란 부모 클래스에 있는 메서드를 동일한 이름으로 다시 만드는 활동
  # 오버라이딩을 통해 0으로 나눴을 때, 오류가 아닌 0을 리턴하도록 div메서드 수정
  >>> class SafeFourCal(FourCal):
  ...     def div(self):
  ...         if self.second == 0:
  ...             return 0
  ...         else:
  ...             return self.first / self.second
  ...
  >>> a = SafeFourCal(4, 0)
  >>> a.div()
  0
  ```
+ 클래스 변수
```python
# 클래스 변수 선언
>>> class Family:
...     lastname = 'Kim'
...
# 클래스 변수 호출1
>>> print(Family.lastname)  # 클래스명.클래스변수
Kim
# 클래스 변수 호출2  # 클래스에 의해 생성된 객체를 통한 호출
>>> a = Family()
>>> b = Family()
>>> print(a.lastname)
Kim
>>> print(b.lastname)
Kim
```
```python
# 클래스 변수의 값을 변경하면 클래스에 의해 생성된 객체들의 클래스 변수(lastname) 값들도 모두 변경된다.
>>> Family.lastname = 'Park'
>>> print(a.lastname)
Park
>>> print(b.lastname)
Park
# 클래스 변수가 클래스에 의해 생성된 모든 객체에 공유된다는 특징은 id함수를 통해 확인할 수 있다.
>>> id(Family.lastname)
48336160
>>> id(a.lastname)
48336160
>>> id(b.lastname)
48336160
>>> id(Family.lastname) == id(a.lastname) == id(b.lastname)
True
```
+ 클래스의 활용
`홍길동|42|A`과 같이 이름, 나이, 성적이 파이프 문자`|`로 구분한 문자열을 처리하는 클래스를 만들어 본다.
```python
# 문자열에서 나이를 출력하는 함수
>>> def print_age(data):
...     tmp = data.split("|")
...     age = tmp[1]
...     print(age)
...
>>> data = "홍길동|42|A"
>>> print_aga(data)
42
# 문자열에서 이름과 점수를 출력하는 함수
>>> def print_grade(data):
...     tmp = data.split("|")
...     name = tmp[0]
...     grade = tmp[2]
...     print("%s님 당신의 점수는 %s입니다." % (name, grade))
...
>>> data = "홍길동|42|A"
>>> print_grade(data)
홍길동님 당신의 점수는 A입니다.
```
```python
# 함수 대신 클래스를 이용하여 개선된 코드 작성
>>> class Data:
...     def __init__(self, data):
...         tmp = data.split("|")
...         self.name = tmp[0]
...         self.age = tmp[1]
...         self.grade = tmp[2]
...
>>> data = Data("홍길동|42|A")
>>> print(data.age)
42
>>> print(data.name)
홍길동
>>> print(data.grade)
A
# 정형화된 객체를 활용하여 기존 함수(나이, 성적 출력) 개선
>>> def print_age(data):
...     print(data.age)
...
>>> def print_grade(data):
...     print("%s님 당신의 점수는 %s입니다." % (data.name, data.grade))
...
>>> data = Data("홍길동|42|A")
>>> print_age(data)
42
>>> print_grade(data)
홍길동님 당신의 점수는 A입니다.
```
```python
# pring_age, pring_grade 함수는 data객체에 의존적인 함수
# 그러므로 두 함수를 Data클래스의 메서드로 만들어 준다.
>>> class Data:
...     def __init__(self, data):
...         tmp = data.split("|")
...         self.name = tmp[0]
...         self.age = tmp[1]
...         self.grade = tmp[2]
...     def print_age(self):
...         print(self.age)
...     def print_grade(self):
...         print("%s님 당신의 점수는 %s입니다." % (self.name, self.grade))
...
>>> data = Data("홍길동|42|A")
>>> data.print_age()
42
>>> data.print_grade()
홍길동님 당신의 점수는 A입니다.
```
+ 연습문제
  1. Calculator 1
  ```python
  class Calculator:
      def __init__(self):
          self.value = 0
      
      def add(self, val):  # 메서드의 첫 번째 매개변수(self) 추가
          self.value += i
  
  cal = Calculator()
  cal.add(3)
  cal.add(4)
  
  print(cal.value)
  7
  ```
  2. Calculator 2
  ```python
  class Calculator:
      def __init__(self, init_value):
          self.value = init_value
          
      def add(self, val):
          self.value += val
          
  cal = Calculator(0)  # 생성자(constructor)의 매개변수인 init_value에 해당하는 값을 전달하지 않아 오류 발생. 해당 값(0)을 전달하여 해결
  cal.add(3)
  cal.add(4)
  
  print(cal.value)
  7
  ```
  ```python
  # 교재 풀이
  class Calculator:
      def __init__(self, init_value=0):  # 초기값 init_value를 0으로 디폴트로 지정
          self.value = init_value
          
      def add(self, val):
          self.value += val
          
  cal = Calculator()  # init_value 디폴트 값을 정함으로써 초기값 전달 없이 객체 생성 가능
  cal.add(3)
  cal.add(4)
  
  print(cal.value)
  7
  ```
  3. UpgradeCalculator
  ```python
  class Calculator:
      def __init__(self):
          self.value = 0
          
      def add(self, val):
          self.value += val
  
  class UpgradeCalculator(Calculator):
      def minus(self, val):
          self.value -= val
  
  
  cal = UpgradeCalculator()
  cal.add(10)
  cal.minus(7)
  
  print(cal.value)
  3
  ```
  4. MaxLimitCalculator
  ```python
  class Calculator:
      def __init__(self):
          self.value = 0
          
      def add(self, val):
          self.value += val
      
  class MaxLimitCalculator(Calculator):
      def add(self, val):
          self.value += val
          if self.value > 100:
              self.value = 100
  
  
  cal = MaxLimitCalculator()
  cal.add(50)
  cal.add(60)
  
  print(cal.value)
  100
  ```
  5. Calculator 3
  ```python
  class Calculator:
      def __init__(self, init_value):
          self.value = init_value
          self.a = 0
          self.b = 0
          
      def sum(self):
          for i in self.value:
              self.a += i
          return self.a  # 메서드 수행 후 self.a값이 초기화되지 않기 때문에 2회 이상 수행 시 self.a값이 누적되면서 의도와 다른 결과 획득
          
      def avg(self):
          for i in self.value:
              self.b += i
          return self.b / len(self.value)  # sum메서드와 마찬가지로 self.b값이 초기화되지 않으므로 반복 수행 시 값이 누적되면서 다른 결과 획득
  
  # 교재 풀이
  # class Calculator:
  #   def __init__(self, numberlist):
  #       self.numberlist = numberlist
          
  #   def sum(self):
  #       result = 0
  #       for num in self.numberlist:
  #           result += num
  #       return result
          
  #   def avg(self):
  #       total = self.sum()
  #       return total / len(self.numberlist)
            
  
  cal1 = Calculator([1, 2, 3, 4, 5])
  print(cal1.sum())
  print(cal1.avg())
  
  cal2 = Calculator([6, 7, 8, 9, 10])
  print(cal2.sum())
  print(cal2.avg())
  
  15
  3.0
  40
  8.0
  ```
---
#### 05-2. 모듈
+ 모듈 만들고 불러 보기  
  + 모듈이란 함수나 변수 또는 클래스를 모아 놓은 파일로, 다른 파이썬 프로그램에서 불러와 사용할 수 있게끔 만들어진 파이썬 파일이다.
    ```python
    # 모듈 생성
    # mod1.py
    def sum(a, b):
        return a + b
    ````
    ```python
    # 모듈 호출 (명령 프롬프트 창)
    C:\Users\Jungjoon>cd C:\doit
    C:\doit>dir
    ...
    2018-12-23 오후 02:38 49 mod1.py
    ...
    C:\doit>python
    >>> import mod1  # import는 파이썬 모듈을 불러오는 명령어로 'import 모듈이름'과 같이 사용한다. 모듈이름 기입 시 확장자명(.py)은 적지 않는다.
    >>> print(mod1.sum(3, 4))  # 모듈 내 함수 이용 방법: 모듈이름.함수이름
    7
    ```
    ```python
    # 기존 모듈(mod1.py)에 함수 추가
    def safe_sum(a, b):
        if type(a) != type(b):
            print("더할 수 있는 것이 아닙니다.")
            return  # return 단독으로 사용하여 None 값을 돌려주고 함수 종료
        else:
            result = sum(a, b)
            return result
            
    # 추가한 함수 실행
    >>> import mod1
    >>> print(mod1.safe_sum(3, 4))
    7
    >>> print(mod1.safe_sum(1, 'a'))
    더할 수 있는 값이 아닙니다.
    None
    
    # 기존 함수 실행
    >>> print(mod1.sum(10, 20))
    30
    ```
  + 모듈 함수를 사용하는 또 다른 방법
  ```python
  # 사용 방법
  from 모듈이름 import 모듈함수
  
  # 사용 예시1
  >>> from mod1 import sum
  >>> sum(3, 4)
  7
  >>> from mod1 import sum, safe_sum
  >>> sum(3, 5)
  8
  >>> safe_sum(4, 6)
  10
  
  # 사용 예시2
  >>> from mod1 import *
  >>> sum(10, 20)
  30
  >>> safe_sum(10, 'b')
  더할 수 있는 값이 아닙니다.
  ```
+ if__name__=="__main__":의 의미
```python
# mod1.py 업데이트
def sum(a, b):
    return a + b
    
def safe_sum(a, b):
    if type(a) != type(b):
        print("더할 수 있는 값이 아닙니다.")
        return
    else:
        result = sum(a, b)
        return result

# print문 추가
print(safe_sum('a', 1))
print(safe_sum(1, 4))
print(sum(10, 10.4))
```
```python
# mod1.py 실행
C:\doit>python mod1.py
더할 수 있는 값이 아닙니다.
None
5
20.4
```
```python
# mod1.py 호출
C:\doit>python
>>> import mod1
더할 수 있는 값이 아닙니다.  # import를 수행하는 순간 mod1.py가 실행되어 결과값 출력
None
5
20.4

# import 수행 시 모듈 실행 방지법
# mod1.py에 추가한 print문 상단에 if문 추가
if __name__ == "__main__":  # mod1.py 실행 시 __name__ 변수에 '__main__' 저장, 조건문이 참이 되면서 if문 다음 문장 수행. import 시에는 __name__ 변수에 모듈이름 'mod1'이 값으로 저장, 조건문이 거짓이 되면서 if문 다음 문장이 수행되지 않는다.
    print(safe_sum('a', 1))
    print(safe_sum(1, 4))
    print(sum(10, 10.4))

# if문 추가 후 import 실행 결과
>>> import mod1
>>>
```
+ 클래스나 변수 등을 포함한 모듈
```python
# 변수, 클래스, 함수를 모두 포함하는 모듈 생성
# mod2.py
PI = 3.141592

class Math:
    def solv(self, r):
        return PI * (r ** 2)
        
def sum(a, b):
    return a + b

if __name__=="__main__":
    print(PI)
    a = Math()
    print(a.solv(2))
    print(sum(PI, 4.4))
```
```python
# mod2.py 실행 결과
C:\doit>python mod2.py
3.141592
12.566368
7.541592
```
```python
# mod2.py 호출 결과
C:\doit>python
>>> import mod2
>>>              # __name__=="__main__" 조건문이 거짓이 되므로 아무 값도 출력되지 않는다.
```
  + 모듈에 포함된 변수, 클래스, 함수 사용하기
  ```python
  # 모듈 내 변수 사용법
  C:/doit>python
  >>> import mod2
  >>> print(mod2.PI)  # 모듈명.변수명 
  3.141592
  ```
  ```python
  # 모듈 내 클래스 사용법
  >>> a = mod2.Math()  # 모듈명.클래스명
  >>> print(a.solv(2))
  12.566368
  ```
  ```python
  # 모듈 내 함수 사용법
  >>> print(mod2.sum(mod2.PI, 4.4))  # 모듈명.함수
  7.541592
  ```
+ 새 파일 안에서 이전에 만든 모듈 불러오기
```python
# modtest.py
import mod2
result = mod2.sum(3, 4)
print(result)
7
```
  + 모듈을 저장한 디텍터리로 이동하지 않고 모듈을 불러와 사용하는 방법
    1. sys.path.append(모듈을 저장한 디렉터리명) 사용
    ```python
    >>> import sys   # sys 모듈 호출
    >>> sys.path   # 파이썬 라이브러리가 설치되어 있는 디렉터리 확인
    ['', ...]
    >>> sys.path.append("C:/doit/mymod")   # 'C:/doit/mymod' 디렉터리를 sys.path에 추가
    >>> sys.path
    ['', ..., 'C:/doit/mymod']   # 마지막 요소에 'C:/doit/mymod' 추가
    ```
    ```python
    # 모듈 호출 테스트
    >>> import mod2
    >>> print(mod2.sum(3, 4))
    7
    ```
    2. PYTHONPATH 환경 변수 사용
    ```python
    C:\Users\home>set PYTHONPATH=C:\doit\mymod  # set 명령어로 PYTHONPATH 환경 변수에 모듈이 있는 디렉토리 설정
    C:\Users\home>python
    >>> import mod2
    >>> print(mod2.sum(3, 4))
    7
    ```
+ 연습문제
  1. 모듈 사용하기 1
    ```python
    # 'C:\doit' 디렉토리로 이동하여 import
    C:\Users\Jungjoon>cd C:\doit
    C:\doit>python
    >>> import mymod
    >>>
    
    # sys.path에 'C:\doit' 추가
    C:\Users\Jungjoon>python
    >>> import sys
    >>> sys.path.append('C:\doit')
    >>> import mymod
    >>>
    
    # PYTHONPATH 설정
    C:\Users\home>set PYTHONPATH=C:\doit
    C:\Users\home>python
    >>> import mymod
    >>>
    ```
  2. 모듈 작성
    ```python
    # mymod.py
    
    def mysum(a, b):
        return a + b
    ```
  3. 모듈 사용하기 2
    ```python
    # mymod.py
    
    def mysum(a, b):
        return = a + b
      
    # test
    print(mysum(3, 7))   # 10 출력
    ```
    ```python
    # mymod.py 실행 결과
    >>> import sys
    >>> sys.path.append('C:\doit')
    >>> import mymod
    10   # '__name__' 변수를 이용한 조건문의 부재로 인해 모듈 실행/호출 두 경우 모두 print문 수행 
    ```
    ```python
    # mymod.py 수정
    
    def mysum(a, b):
        return a + b
      
    # test
    if __name__=="__main__":  # '__name__' 변수를 이용한 조건문 추가
        print(mysum(3, 7))    # 직접 실행 시에만 10 출력
    ```
---
#### 05-3. 패키지
+ 패키지(Package)란 무엇인가?
  + 파이썬 패키지는 디텍토리와 모듈로 구성되며, 도트(.)를 통해 모듈을 계층적(디렉토리 구조)으로 관리할 수 있게 해준다.
    ```python
    # 패키지 예시
    game/              # 디렉토리(root)
        __init__.py       # 모듈
        sound/         # 디렉토리(sub)
            __init__.py   # 모듈
            echo.py       # 모듈
            wav.py        # 모듈
        graphic/       # 디렉토리(sub)
            __init__.py   # 모듈
            screen.py     # 모듈
            render.py     # 모듈
        play/          # 디렉토리(sub)
            __init__.py   # 모듈
            run.py        # 모듈
            test.py       # 모듈
    ```
+ 패키지 만들기
  + 패키지 기본 구성 요소 준비하기
   1. 디렉토리 및 모듈(파일) 생성
     ```python
     C:/doit/game/__init__.py
     C:/doit/game/sound/__init__.py
     C:/doit/game/sound/echo.py
     C:/doit/game/graphic/__init__.py
     C:/doit/game/graphic/render.py
     ```
   2. 모듈 별 내용 작성
     ```python
     # 디렉토리 별로 있는 '__init__.py'의 내용은 일단 비워둔다.
     ```
     ```python
     # echo.py
     def echo_test():
         print("echo")
     ```
     ```python
     # render.py
     def render_test():
         print("render")
     ```
   3. 패키지 참조 설정
     ```python
     C:\>set PYTHONPATH=C:/doit
     C:\>python
     >>>
     ```
  + 패키지 안의 함수 실행하기
    ```python
    # 1. 모듈 import
    >>> import game.sound.echo
    >>> game.sound.echo.echo_test()
    echo
    ```
    ```python
    # 2. 모듈 from ... import
    >>> from game.sound import echo
    >>> echo.echo_test()
    echo
    ```
    ```python
    # 3. 함수 from ... import
    >>> from game.sound.echo import echo_test
    >>> echo_test()
    echo
    ```
+ __init__.py 의 용도
  + `__init__.py`는 해당 디렉토리가 패키지의 일부임을 알려주는 역할
  + 위 예시의 디렉토리인 game, sound, graphic에 `__init__.py`가 없다면 패키지로 인식되지 않는다.
  + python3.3 버전부터는 `__init__.py`가 없어도 패키지로 인식되지만, 하위 버전 호환을 위해 생성하는 것이 안전하다.
+ __all__ 의 용도
  + `*`로 디렉토리의 **모듈** import 시 해당 디렉토리 내 `__init__.py`에 `__all__` 변수를 설정하고 import할 모듈을 정의해주어야 한다.
    ```python
    # 현재의 패키지에서 * 사용 시 오류(NameError) 발생
    >>> from game.sound import *
    >>> echo.echo_test()
    Traceback (most recent call last):
      File "<pyshell#5>", line 1, in <module>
        echo.echo_test()
    NameError: name 'echo' is not defined
    ```
    ```python
    # C:/doit/game/sound/__init__.py
    # __all__ 변수 설정
    __all__ = ['echo']
    ```
    ```python
    >>> from game.sound import *
    >>> echo.echo_test()
    echo
    ```
  + _주의점: `from a.b.c. import *`의 마지막 항목 c가 모듈인 경우에는 `__all__`과 상관없이 무조건 import된다._
+ relative 패키지
  + `graphic 디렉토리>render.py 모듈`에서 `sound 디렉토리>echo.py 모듈`을 사용할 때는 절대 경로뿐만 아니라 상대 경로도 사용할 수 있다.
    ```python
    # 절대 경로 예시
    # render.py
    from game.sound.echo import echo_test   # import문 추가
    
    def render_test():
        print("render")
        echo_test()
    ```
    ```python
    # 절대 경로 예시 실행 결과
    >>> from game.graphic.render import render_test
    >>> render_test()
    render
    echo
    ```
    ```python
    # 상대 경로 예시
    # render.py
    from ..sound.echo import echo_test
    
    def render_test():
        print("render")
        echo_test()
    ```
    ```python
    # 상대 경로 예시 실행 결과
    >>> from game.graphic.render import render_test
    >>> render_test()
    render
    echo
    ```
  + `relative` 접근자
    
    접근자|위치
    ------|---
    `..`|부모 디렉토리
    `.`|현재 디렉토리
  
  + _relative 접근자는 모듈 안에서만 사용할 수 있다. 인터프리터에서 사용하면 오류(SystemError)가 발생한다._
+ 연습문제
  1. 패키지 사용 1
    ```python
    # 아래 game 패키지의 echo모듈에 있는 echo_test함수를 이용하려고 한다.
    game/
        __init__.py
        sound/
            __init__.py
            echo.py
            wav.py
        graphic/
            __init__.py
            screen.py
            render.py
        play/
            __init__.py
            run.py
            test.py
    ```
    ```python
    # 아래 호출(3번)은 동작하지 않는다. 모듈을 사용하기 위해서는 import문에 모듈을 포함해야 한다. 하지만 3번 import문은 디렉토리만 포함하고 있다.
    >>> import game
    >>> game.sound.echo.echo_test()
    ```
  2. 패키지 사용 2
    ```python
    # 아래는 game/graphic/screen.py 의 내용이다.
    
    # import가 필요하다. <<< game/sound/echo.py 모듈의 echo_test()함수를 사용하기 위한 import문을 삽입하시오.(단, relative 접근자 사용)
    echo_test()
    ```
    ```python
    # Answer
    
    from ..sound.echo import echo_test
    echo_test()
    ```
---
#### 05-4. 예외 처리
+ 자주 발생하는 오류
  1. 디렉토리에 없는 파일을 열 때 (FileNotFoundError)
  ```python
  >>> f = open('aaa', 'r')
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  FileNotFoundError: [Errno 2] No such file or directory: 'aaa'
  ```
  2. 숫자를 0으로 나누었을 때 (ZeroDivisionError)
  ```python
  >>> 4 / 0
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  ZeroDivisionError: division by zero
  ```
  3. 리스트에서 얻을 수 없는 값을 호출할 때 (IndexError)
  ```python
  >>> a = [1, 2, 3]
  >>> a[4]
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  IndextError: list index out of range
  ```
+ 오류 예외 처리 기법
  1. try .. **except**
    ```python
    # 기본 구조 - try블록 수행 중 오류가 발생하면 except블록 수행
    try:
        ...
    except [발생 오류[as 오류 메시지 변수]]:  # []는 괄호 안 내용을 생략할 수 있다는 관례적인 표기법. 따라서 except문은 3가지 방법으로 사용가능
        ...
    ```
    1. except만 쓰는 방법
      ```python
      # 종류에 상관없이 오류가 발생하면 except 블록 수행
      try:
          ...
      except:
          ...
      ```
    2. 발생 오류만 포함한 except문
      ```python
      # except문에 정해 좋은 오류가 발생하면 except 블록 수행
      try:
          ...
      except 발생 오류:
          ...
      ```
    3. 발생 오류, 오류 메시지 변수를 포함한 except문
      ```python
      # except문에 정해 좋은 오류가 발생하면 except 블록 수행, 2번과 달리 오류 메시지까지 출력
      try:
          ...
      except 발생 오류 as 오류 메시지 변수:
          ...
      ```
      ```python
      # 예시
      try:
          4 / 0
      except ZeroDivisionError as e:
          print(e)
      
      division by zero
      >>> 
      ```
  2. try .. **else**
    ```python
    # 기본 구조 - 예외(except)가 발생하지 않을 경우 else블록 수행
    try:
        ...
    except [발생 오류[as 오류 메시지 변수]]:
        ...
    else:   # else블록은 반드시 except블록 다음에 위치
        ...
    ```
    ```python
    # 예시
    try:
        f = open('foo2.txt', 'r') 
    except FileNotFoundError as e:
        print(e)
    else:
        data = f.read()
        f.close()
        
    [Errno 2] No such file or directory: 'foo2.txt'
    >>>
    ```
  3. try .. **finally**
    ```python
    # 기본 구조 - finally블록은 예외 발생 여부와 상관없이 항상 수행. 보통 사용한 리소스를 close해야하는 경우에 사용
    f = open('foo.txt', 'w')
    try:
        ...    # 수행 내용
    finally:
        f.close   # try블록 수행 후 열린 파일(foo.txt)을 닫을 수 있다.
    ```
  4. 여러 개의 오류 처리
    ```python
    # 기본 구조
    try:
        ...
    except 발생 오류1:
        ...
    except 발생 오류2:
        ...
    ```
    ```python
    # 예시1-1 - 0으로 나누는 오류와 인덱싱 오류 처리
    try:
        a = [1, 2]
        print(a[3])
        4 / 0
    except ZeroDivisionError:
        print('0으로 나눌 수 없습니다.')
    except IndexError:
        print('인덱싱 할 수 없습니다.')
    
    인덱싱 할 수 없습니다.  # 인덱싱 오류가 먼저 발생했으므로 ZeroDivisionError(4/0)는 발생하지 않았다.
    >>>
    ```
    ```python
    # 예시1-2 - 예시1 except문에 오류 메시지 추가
    try:
        a = [1, 2]
        print(a[3])
        4 / 0
    except ZeroDivisionError as e:
        print(e)
    except IndexError as e:
        print(e)
    
    list index out of range
    >>>
    ```
    ```python
    # 예시2 - ZeroDivisionError, IndexError 동시 처리
    try:
        a = [1, 2]
        print(a[3])
        4 / 0
    except (ZeroDivisionError, IndexError) as e:
        print(e)
    
    list index out of range
    >>>
    ```
+ 오류 회피하기
  ```python
  try:
      f = open('foo2.txt', 'r')
  except FileNotFoundError:  # FileNotFoundError 발생 시
      pass                   # 오류 회피
  
  >>>   # 파일이 없음에도 오류가 발생하지 않는다.
  ```
+ 오류 일부러 발생시키기
  ```python
  # 예시: Bird클래스를 상속받은 자식 클래스에서 반드시 fly함수를 구현하게 만들고 싶은 경우
  class Bird:
      def fly(self):
          raise NotImplementedError
  ```
  ```python
  # 자식 클래스(Eagle)에 fly함수 미구현
  class Eagle(Bird):
      pass
      
  eagle = Eagle()
  eagle.fly()
  
  Traceback (most recent call last):
    File "C:/doit/raise_error.py", line 11, in <module>
      eagle.fly()
    File "C:/doit/raise_error.py", line 5, in fly
      raise NotImplementedError
  NotImplementedError
  >>>
  ```
  ```python
  # 자식 클래스(Eagle)에 fly함수 구현
  class Eagle(Bird):
      def fly(self):
          print('very fast')
  
  eagle = Eagle()
  eagle.fly()
  
  very fast
  >>>
  ```
+ 예외 만들기
  + 파이썬 내장 클래스인 `Exception`을 상속하여 예외를 만들 수 있다.
    ```python
    # MyError가 발생하는 예시
    
    class MyError(Exception):
        pass
    
    def say_nick(nick):
        if nick == '바보':
            raise MyError()
        print(nick)
   
    say_nick("천사")
    say_nick("바보")
    
    
    천사
    Traceback (most recent call last):
      File "C:/doit/define_exceptions.py", line 13, in <moudle>
        say_nick("바보")
      File "C:/doit/define_exceptions.py", line 8, in say_nick
        raise MyError()
    MyError
    >>>
    ```
    ```python
    # MyError 발생 시 예외 처리 예시
    try:
        say_nikc("천사")
        say_nikc("바보")
    except MyError:
        print("허용되지 않는 별명입니다.")
    
    
    천사
    허용되지 않은 별명입니다.
    >>>
    ```
    ```python
    # MyError 발생 시 예외 처리 예시 - 오류 메시지 추가
    try:
        say_nikc("천사")
        say_nikc("바보")
    except MyError as e:
        print(e)
    
    
    천사
          # 오류 메시지가 출력되지 않는다. 오류 클래스에 __str__ 메서드(print문으로 오류 메시지 출력 시 호출되는 메서드) 구현 필요
    >>>
    ```
    ```python
    # 오류 클래스(MyError)에 __str__메서드 구현
    
    class MyError(Exception):
        def __str__(self):
            return "허용되지 않는 별명입니다."
    
    def say_nick(nick):
        if nick == '바보':
            raise MyError()
        print(nick)
    
    try:
        say_nick("천사")
        say_nick("바보")
    except MyError as e:
        print(e)
    
    
    천사
    허용되지 않는 별명입니다.  # __str__에서 정의한 오류 메시지가 출력된다. 
    >>>
    ```
    ```python
    # 오류 발생 시점에 오류 메시지를 전달하고 싶은 경우
    # 오류 클래스(MyError)에 생성자(constructor) '__init__'를 정의해야 한다.
    
    class MyError(Exception):
        def __init__(self, msg):
            self.msg = msg
            
        def __str__(self):
            return self.msg
    
    def say_nick(nick):
        if nick == '바보':
            raise MyError("허용되지 않는 별명입니다.")   # 오류 발생 시점에 오류 메시지를 전달한다.
        print(nick)
    
    try:
        say_nick("천사")
        say_nick("바보")
    except MyError as e:
        print(e)
    
    
    천사
    허용되지 않는 별명입니다.
    >>>
    ```
+ 연습문제
  1. 예외처리 1
    문제 1)
      ```python
      # 문제
      >>> "a" + 1
      Traceback (most recent call last):
        File "<stdin1>", line 1, in <module>
      TypeError: can only concatenate str (not "int") to str  # 문자열 자료에는 정수형 자료를 더할 수 없기 때문에 TypeError 발생
      ```
      ```python
      # 풀이
      >>> "a" + "1"  # 정수 1을 문자형으로 변경
      'a1'
      
      # 교재 풀이
      >>> "a" + str(1)
      'a1'
      ```
    문제 2)
      ```python
      # 문제
      >>> a = [1, 2, 3]
      >>> a[3]
      Traceback (most recent call last):
        File "<stdin1>", line 1, in <module>
      IndexError: list index out of range   # a의 요소 개수는 3개인 반면, a[3]은 4번째 요소값을 호출하는 명령어이므로 IndexError 발생
      ```
      ```python
      # 풀이
      >>> a= a + [4]   # 4번째 요소값(4)를 a리스트에 추가한다.
      [1, 2, 3, 4]
      >>> a[3]
      4
  
      # 교재 풀이
      >>> a= [1, 2, 3]
      >>> a[2]   # a리스트의 3번째 요소값을 호출한다.
      3  
      ```
  2. 예외처리 2
    ```python
    # 문제
    a = [1, 2, 3]
    
    try:
        result = a[-3]
    except:
        print("error")
    else:
        print("no error")
    ```
    ```python
    # 실행 결과
    no error - a[-3]은 a[0]을 의미하므로 오류가 발생하지 않는다.(음수 인덱싱은 시작점이 -1부터이기 때문)
  3. 예외처리 3
    ```python
    # 문제
    result = 3
    
    try:
        result += 1
    except:
        result += 2
    else:
        result += 3
    finally:
        result += 4
    
    print(result)
    ```
    ```python
    # 실행 결과
    11 - 1) try 수행(3+1=4) => 2) 오류가 없으므로 else 수행(4+3=7) => 3) finally 수행(7+4=11)
    ```
  4. 예외처리 4
    ```python
    # 문제
    result = 0
    
    try:
        [1, 2, 3][3]
        "a" + 1
        4 / 0
    except TypeError:
        result += 1
    except ZeroDivisionError:
        result += 2
    except IndexError:
        result += 3
    else:
        result += 4
    finally:
        result += 5
        
    print(result)
    ```
    ```python
    # 실행 결과
    8 - 1) try문 첫 번째 문장 수행 중 IndexError 발생(0+3=3) => 2) 오류 발생으로 나머지 try블록은 수행하지 않고 finally문 수행(3+5=8)
    ```
---
#### 05-5. 내장 함수
+ abs
  ```python
  # abs(x)는 숫자를 입력 받았을 때 절대값을 돌려준다.
  
  >>> abs(3)
  3
  >>> abs(-1)
  1
  >>> abs(-1.2)
  1.2
  ```
+ all
  ```python
  # all(x)는 반복 가능한 자료형을 인수로 받으며, 인수의 모든 요소가 참이면 True, 하나라도 거짓이면 False를 돌려준다.
  
  >>> all([1, 2, 3])
  True
  >>> all([1, 2, 3, 0])
  False   # 0이 거짓이므로 False를 돌려준다.
  ```
+ any
  ```python
  # any(x) 역시 반복 가능한 자료형을 인수로 받으며, 인수의 요소 중 하나라도 참이면 True, 모두 거짓이면 False를 돌려준다.
  # all(x)와 반대라고 할 수 있다.
  
  >>> any([1, 2, 3, 0])
  True
  >>> any([0, ""])
  False
  ```
+ chr
  ```python
  # chr(i)는 아스키 코드값을 입력으로 받아 해당하는 문자를 출력한다.
  
  >>> chr(97)
  'a'
  >>> chr(48)
  '0'
  >>> chr(111)
  'o'
  ```
+ dir
  ```python
  # dir함수는 객체가 자체적으로 갖고 있는 변수/함수를 보여준다.
  
  >>> dir([1, 2, 3])
  ['__add__', '__class__', '__contains__', ..., 'sort']
  >>> dir({'1':'a'})
  ['__class__', '__contains__', '__delattr__', ..., 'values']
  ```
+ divmod
  ```python
  # divmod(a,b)는 a를 b로 나눈 몫과 나머지를 튜플 형태로 돌려준다.
  
  >>> divmod(7, 3)
  (2, 1)
  # 몫을 구하는 연산자(//) 및 나머지를 구하는 연산자(%)
  >>> 7 // 3
  2
  >>> 7 % 3
  1
  ```
+ enumerate
  ```python
  # 순서가 있는 자료형을 입력으로 받아 인덱스 값을 포함하는 enumerate 객체를 돌려준다.
  
  >>> for i, name in enumerate(['body', 'foo', 'bar']):
  ...     print(i, name)
  ...
  0 body
  1 foo
  2 bar
  ```
+ eval
  ```python
  # 실행 가능한 문자열을 입력으로 받아 결과값을 돌려준다. 보통 입력받은 문자열로 함수나 클래스를 동적으로 실행하고 싶은 경우에 사용한다.
  
  >>> eval('1+2')
  3
  >>> eval("'hi' + 'a'")
  'hia'
  >>> eval('divmod(4, 3)')
  (1, 1)
  ```
+ filter
  ```python
  # 첫 번째 인수인 함수에, 두 번째 인수인 반복 가능한 자료형을 입력하여 결과값으로 참인 것만을 묶어서 돌려준다.
  # positive.py
  def positive(l):
      result = []
      for i in l:
          if i > 0:
              result.append(i)
      return result
      
  print(positive([1, -3, 2, 0, -5, 6]))
  
  
  [1, 2, 6]
  ```
  ```python
  # filter함수를 활용하여 위 positive함수를 보다 간략하게 만들 수 있다.
  # filter1.py
  
  def positive(x):
      return x > 0
      
  print(list(filter(positive, [1, -3, 2, 0, -5, 6])))
  
  
  [1, 2, 6]
  ```
  ```python
  # lambda를 이용해 filter1.py의 코드를 더욱 간략하게 만들 수 있다. 
  >>> list(filter(lambda x: x > 0, [1, -3, 2, 0, -5, 6]))
  [1, 2, 6]
  ```
+ hex
  ```python
  # 정수값을 입력받아 16진수로 변환한 값을 돌려준다.
  
  >>> hex(234)
  '0xea'
  >>> hex(3)
  '0x3'
  ```
+ id
  ```python
  # 입력받은 객체의 고유 주소값(reference)를 돌려준다.
  
  >>> a = 3
  >>> id(3)
  1854064800
  >>> id(a)
  1854064800
  >>> b = a
  >>> id(b)
  1854064800   # 3, a, b의 고유 주소값은 동일하다. 즉 3개 모두 같은 객체를 가리키고 있다.
  >>> id(4)
  1854064816   # 4를 입력하면 다른 고유 주소값이 출력된다. 
  ```
+ input
  ```python
  # 사용자 입력을 받는 함수로, 입력 인수로 문자열을 주면 해당 문자열은 프롬프트가 된다.
  
  >>> a = input()
  hi
  >>> a
  'hi'
  >>> b = input("Enter: ")
  Enter: hi   # 입력 인수 문자열("Enter: ")이 프롬프트로 동작한다.
  >>> b
  'hi'
  ```
+ int
  ```python
  # 문자열 형태의 숫자, 소수점이 있는 숫자를 정수 형태로 돌려준다.
  # 정수를 입력받으면 그대로 돌려준다.
    >>> int('3')
  3
  >>> int(3.4)
  3
  
  # int(x, radix)는 radix 진수로 표현된 문자열 x를 10진수로 변환하여 돌려준다.
  >>> int('11', 2)  # 2진수로 표현된 '11'의 10진수 값을 돌려준다
  3
  >>> int('1A', 16)  # 16진수로 표현된 '1A'의 10진수 값을 돌려준다.
  26
  ```
+ isinstance
  ```python
  # 입력으로 받은 인스턴스(첫 번째 인수)가 클래스(두 번째 인수)의 인스턴스이면 True, 아니면 False를 돌려준다.
  
  >>> class Person: pass
  ...
  >>> a = Person()
  >>> isinstance(a, Person)
  True
  >>> b = 3
  >>> isinstance(b, Person)
  False
  ```
+ len
  ```python
  # 입력값의 길이(요소의 총 개수)를 돌려준다.
  
  >>> len("python")
  6
  >>> len([1, 2, 3])
  3
  >>> len((1, 'a'))
  2
  ```
+ list
  ```python
  # 반복 가능한 자료형을 입력받아 리스트로 만들어 돌려준다.
  >>> list('python')
  ['p', 'y', 't', 'h', 'o', 'n']
  >>> list((1, 2, 3))
  [1, 2, 3]
  
  # 리스트를 입력값으로 주면 동일한 리스트를 복사하여 돌려준다.
  >>> a = [1, 2, 3]
  >>> b = list(a)
  >>> b
  [1, 2, 3]
  ```
+ map
  ```python
  # 입력받은 함수(첫 번째 인수)에 의해 반복 가능한 자료(두 번째 인수)의 각 요소가 수행된 결과를 묶어서 돌려준다.
  
  # two_times.py
  def two_times(numberList):
      result = []
      for number in numberList:
          result.append(number * 2)
      return result
      
  result = two_times([1, 2, 3, 4])
  print(result)
  
  
  [2, 4, 6, 8]
  ```
  ```python
  # map함수를 활용하여 위 two_times함수 예제를 다음과 같이 바꿀 수 있다.
  >>> def two_times(x):
  ...     return x * 2
  ...
  >>> list(map(two_times, [1, 2, 3, 4]))
  [2, 4, 6, 8]
  
  # lambda를 사용해 더욱 간략하게 만들 수 있다.
  >>> list(map(lambda a: a*2, [1, 2, 3, 4]))
  [2, 4, 6, 8]
  ```
+ max
  ```python
  # 반복 가능한 자료형을 인수로 입력받아 최대값을 돌려준다.
  >>> max([1, 2, 3])
  3
  >>> max('python')
  'y'
  ```
+ min
  ```python
  # 반복 가능한 자료형을 인수로 입력받아 최소값을 돌려준다.
  >>> min([1, 2, 3])
  1
  >>> min("python")
  'h'
  ```
+ oct
  ```python
  # 인수로 받은 정수 형태의 숫자를 8진수 문자열로 돌려준다.
  
  >>> oct(34)
  '0o42'
  >>> oct(12345)
  '0o30071'
  ```
+ open
  + '파일 이름'(첫 번째 인수)와 '읽기 방법'(두 번째 인수)을 입력받아 파일 객체를 돌려준다.
  + 두 번째 인수인 '읽기 방법'이 생략되면 기본값인 읽기 전용 모드(r)로 파일 객체를 돌려준다.
  
    mode (두 번째 인수) | 설명
    ----------------- | -----
    w | 쓰기 모드로 파일 열기 
    r | 읽기 모드로 파일 열기
    a | 추가 모드로 파일 열기
    b | 바이너리 모드로 파일 열기
  
    ```python
    # 모드(두 번째 인수)가 생략되면 기본값으로 읽기 모드(r)를 갖기 때문에 fread와 fread2는 동일한 결과를 돌려준다.
    >>> fread = open("read_mode.txt", 'r')
    >>> fread2 = open("read_mode.txt")
  
    # 추가 모드 예시
    >>> fappend = open("append_mode.txt", 'a')
  
    # 바이너리 모드(b)는 다른 모드(w, r, a)와 함께 사용한다.
    >>> f = open("binary_file", 'rb')  # 'rb'는 '바이너리 읽기 모드'를 의미한다.
    ```
+ ord
  ```python
  # 입력값의 아스키 코드값을 돌려준다. chr함수와 반대 기능을 수행한다.
  
  >>> ord('a')
  97
  >>> ord('0')
  48
  ```
+ pow
  ```python
  # pow(x, y)는 x의 y제곱 값을 돌려준다.
  
  >>> pow(2, 4)
  16
  >>> pow(3, 3)
  27
  ```
+ range
  ```python
  # range([start], stop, [step])
  # for문과 함께 자주 사용하며, 입력받은 숫자들 범위의 값을 반복 가능한 객체로 만들어 돌려준다.
  
  # 1. 입력 인수가 하나일 경우(stop) - 시작 숫자를 생략하면 0부터 시작한다.
  >>> list(range(5))
  [0, 1, 2, 3, 4]
  # 2. 입력 인수가 두 개일 경우(start, stop)
  >>> list(range(5, 10))
  [5, 6, 7, 8, 9]
  # 3. 입력 인수가 세 개일 경우(start, stop, step) - step인수는 숫자 간의 거리를 의미한다.
  >>> list(range(1, 10, 2))
  [1, 3, 5, 7, 9]
  >>> list(range(0, -10, -1))
  [0, -1, -2, -3, -4, -5, -6, -7, -8, -9]
  ```
+ round
  ```python
  # 입력값을 반올림하여 돌려준다.
  >>> round(4.6)
  5
  >>> round(4.2)
  4
  
  # 두 번째 파라미터는 표시하고 싶은 소수점 자리수(ndigits)를 의미한다.
  >>> round(5.678, 2)
  5.68
  >>> round(6.1432, 3)
  6.143
  ```
+ sorted
  ```python
  # 입력값을 정렬한 결과를 돌려준다.
  
  >>> sorted([3, 1, 2])
  [1, 2, 3]
  >>> sorted(['a', 'c', 'b'])
  ['a', 'b', 'c']
  >>> sorted("zero")
  ['e', 'o', 'r', 'z']
  >>> sorted((3, 2, 1))
  [1, 2, 3]
  
  # 리스트 자료형의 sort함수는 리스트 객체를 정렬할 뿐, 정렬된 결과를 돌려주진 않는다.
  >>> a = [3, 2, 1]
  >>> a.sort()   # 정렬된 결과를 돌려주지는 않는다.
  >>> a
  [1, 2, 3]
  ```  
+ str
  ```python
  # 입력값을 문자열 형태로 변환하여 돌려준다.
  
  >>> str(3)
  '3'
  >>> str('hi')
  'hi'
  str('hi'.upper())
  'HI'
  ```
+ sum
  ```python
  # 입력받은 리스트/튜플의 모든 요소의 합을 돌려준다.
  
  >>> sum([1, 2, 3])
  6
  >>> sum((4, 5, 6))
  15
  ```
+ tuple
  ```python
  # 반복 가능한 자료형을 입력받아 튜플 형태로 돌려준다. 만약 튜플을 입력하면 그대로 돌려준다.
  
  >>> tuple('abc')
  ('a', 'b', 'c')
  >>> tuple([1, 2, 3])
  (1, 2, 3)
  >>> tuple((1, 2, 3))
  (1, 2, 3)
  ```
+ type
  ```python
  # 입력값의 자료형을 알려준다.
  
  >>> type("abc")
  <class 'str'>
  >>> type([ ])
  <class 'list'>
  >>> type(open("C:/doit/acb.txt", 'r'))
  <class '_io.TextIOWrapper'>
  ```
+ zip
  ```python
  # 동일한 개수로 이루어진 반복 가능한 자료형을 2개 이상 입력받아, 요소 순서 별로 묶어서 돌려준다.
  
  >>> list(zip([1, 2, 3], [4, 5, 6]))
  [(1, 4), (2, 5), (3, 6)]
  >>> list(zip([1, 2, 3], [4, 5, 6], [7, 8, 9]))
  [(1, 4, 7), (2, 5, 8), (3, 6, 9)]
  >>> list(zip('abc', 'def'))
  [('a', 'd'), ('b', 'e'), ('c', 'f')]
  ```
+ 연습문제
  1. 내장함수
    ```python
    # 문제 1):
    >>> all([1, 2, abs(-3)-3]) 
    False
    # 문제 2):
    >>> chr(ord('a')) == 'a'
    True
    ```
  2. filter와 lambda
    ```python
    # 문제: filter와 lambda를 이용하여 [1, -2, 3, -5, 8, -3]에서 음수를 모두 제거하시오.
    # 풀이
    >>> list(filter(lambda x: x >= 0, [1, -2, 3, -5, 8, -3]))
    [1, 3, 8]
    ```
  3. 16진수를 10진수로 변환
    ```python
    # 10진수 234의 16진수 값은 hex를 사용해 구할 수 있다.
    >>> hex(234)
    '0xea'
    # 문제: 16진수 문자열 '0xea'을 10진수로 변경해 보시오.
    >>> int('0xea', 16)
    234
    ```
  4. map과 lambda
    ```python
    # 문제: map과 lambda를 이용하여 [1, 2, 3, 4]의 각 요소값에 3이 곱해진 [3, 6, 9, 12]를 만드시오.
    >>> list(map(lambda x: x*3, [1, 2, 3, 4]))
    [3, 6, 9, 12]
    ```
  5. 최대값과 최소값
    ```python
    # 문제: [-8, 2, 7, 5, -3, 5, 0, 1]의 최대값과 최소값의 합을 구하시오.
    >>> a = [-8, 2, 7, 5, -3, 5, 0, 1]
    >>> max(a) + min(a)
    -1
    ```
  6. 소수점 반올림
    ```python
    # 문제: 아래 17/3의 결과값을 소수점 4자리까지만 반올림하여 표시하시오.
    >>> 17 / 3
    5.666666666666667
    >>> round(17/3, 4)
    5.6667
    ```
---
#### 05-6. 외장 함수
1 sys
  + sys모듈은 파이썬 인터프리터가 제공하는 함수/변수들을 직접 제어할 수 있게 해준다.
    1. 명령 행에서 인수 전달하기 (sys.argv)
      ```python
      # argv_test.py
      import sys
      print(sys.argv)
      
      # 명령 프롬프트 창에서 실행
      C:\doit>python argv_test.py you need python
      ['argv_test.py', 'abc', 'pey', 'guido']   # python이라는 명령어 뒤의 모든 것들이 공백을 기준으로 나뉘어서 sys.argv의 요소가 된다.
      ```
    2. 강제로 스크립트 종료하기 (sys.exit)
      ```python
      >>> import sys
      >>> sys.exit()   # 'Ctrl+Z' 또는 'Ctrl+D' 와 같이 인터프리터(또는 프로그램)을 종료시킨다.
      ```
    3. 자신이 만든 모듈 불러와 사용하기 (sys.path)
      ```python
      >>> import sys
      >>> sys.path   # sys.path는 파이썬 포듈이 저장되어 있는 위치를 나타낸다.
      ['', 'C:\\Users\\Jungjoon ...]   # 첫 번째 요소 ''는 현재 디렉토리를 의미한다.
      
      # sys.path.append를 통해 경로명을 추가해 파이썬 모듈을 사용할 수 있다. 다만 파이썬을 종료하면 sys.path가 초기화된다.  
      >>> sys.path.append("C:/doit")
      >>> sys.path
      ['', 'C:\\Users\\Jungjoon ... , 'C:\\doit']
      ```
2. pickle
  + pickle모듈은 객체의 형태를 유지한 채 파일에 저장하고 물러올 수 있게 한다.
    ```python
    # pickle.dump를 이용해 객체(data)를 파일에 저장한다.
    >>> import pickle
    >>> f = open("test.txt", 'wb')
    >>> data = {1: 'python', 2: 'you need'}
    >>> pickle.dump(data, f)
    >>> f.close
    
    # 위에서 저장한 파일을 pickle.load를 통해 원래의 객체 상태 그대로 불러온다.
    >>> import pickle
    >>> f = open("test.txt", 'rb')
    >>> data = pickle.load(f)
    >>> print(data)
    /
    ```
3. os
  + os모듈은 환경 변수, 디렉토리, 파일 등의 OS자원을 제어할 수 있게 해준다.
    1. 내 시스템의 환경 변수값을 알고 싶을 때 (os.environ)
      ```python
      >>> import os
      >>> os.environ
      environ({'...': '...', ...})   # 환경 변수 정보를 딕셔너리 객체로 돌려준다.
      
      # 딕셔너리 형태로 돌려받기 때문에 파이썬 문법에 따라 아래와 같이 호출할 수 있다.
      >>> os.environ['PATH']
      'C:\\Program Files ...'
      ```
    2. 디렉토리 위치 변경하기 (os.chdir)
      ```python
      >>> os.chdir('C:/Users/Jungjoon')
      >>> os.chdir('C:/doit')
      ```
    3. 현재 디렉토리 위치 돌려받기 (os.getcwd)
      ```python
      >>> os.getcwd()
      'C:\\doit'
      ```
    4. 시스템 명령어 호출하기 (os,system)
      + `os.system("명령어")`와 같이 사용하며, 시스템 자체의 프로그램이나 명령어를 호출할 수 있다.
        ```python
        >>> os.system("dir")
        C:\doit 디렉터리
        
        ...
        ```
    5. 시스템 명령어 결과값 파일로 돌려받기 (os.popen)
      + `os.popen("명령어")`는 결과값을 읽기 모드의 파일 객체로 돌려준다.
        ```python
        >>> f = os.popen("dir")
        >>> print(f.read())
        C:\doit 디렉터리
        
        ...
        ```
    6. 기타
    
        함수 | 설명
        ---- | ----
        os.mkdir("디렉토리") | 디렉토리를 생성한다.
        os.rmdir("디렉토리") | 디렉토리를 삭제한다. 단 디렉토리가 비어있어야 가능하다.
        os.unlink("파일") | 파일을 삭제한다.
        os.rename("파일", "새로운 파일명") | "파일" 이름을 "새로운 파일명"으로 바꾼다.
      
4. shutil
  + shutil모듈은 파일을 복사해준다.
    ```python
    >>> import shutil
    >>> shutil.copy("abc.txt", "def.txt")   # abc파일을 def파일에 복사한다. def가 디렉토리면 그 안에 abc파일을 생성하거나 덮어쓴다. 
    >>> f = open("abc.txt". 'r')
    >>> f_copy = open("def.txt". 'r')
    >>> print(f.read())
    EEE
    DDD
    CCC
    BBB
    AAA
    
    >>> print(f_copy.read())   # abc파일을 복사했으므로 내용이 동일하다.
    EEE
    DDD
    CCC
    BBB
    AAA
    
    ```
5. glob
  + glob모듈은 디렉토리에 있는 파일을 읽어서 리스트로 돌려주며, 메타 문자를 사용해 원하는 파일만 읽어올 수도 있다.
    ```python
    # 메타 문자 '*'를 활용해 a로 시작하는 파일만 읽을 수 있다.
    >>> import glob
    >>> glob.glob("C:/doit/a*")
    ['C:/doit\\abc.txt', 'C:/doit\\adddata.py', 'C:/doit\\argv_test.py']
    ```
6. tempfile
  + tempfile모듈을 활용해 임시 파일을 만들 수 있다.
    ```python
    # tempfile.mktemp()는 중복되지 않는 이름(무작위 생성)의 임시 파일을 만들어 돌려준다.
    >>> import tempfile
    >>> filename = tempfile.mktemp()
    >>> filename
    'C:\\Users\\Jungjoon ... \\Temp\\ ~73il4x5'
    
    # temp.TemporaryFile()은 임시 저장 공간용 파일 객체를 돌려준다. 바이너리 쓰기 모드(wb)가 기본이며, f.close()를 호출하면 파일은 사라진다.
    >>> f = tempfile.TemporaryFile()
    >>> f.close
    <bound method ... >
7. time
      1. time.time()  
         UTC를 이용하여 현재 시간을 실수 형태로 돌려준다. 1970년 1월 1일 0시 0분 0초를 기준으로 지난 시간을 초 단위로 돌려준다.
          ```python
          >>> import time
          >>> time.time
          1546655861.8563187
          ```
      2. time.localtime()  
         time.time()의 결과값을 '연, 월, 일, 시, 분, 초' 형태로 변환해 돌려준다.
          ```python
          >>> time.localtime()
          time.struct_time(tm_year=2019, tm_mon=1, tm_mday=5, tm_hour=11, tm_min=39, tm_sec=56, tm_wday=5, tm_yday=5, tm_isdst=0)
          ```
      3. time.asctime()  
         time.localtime()의 결과값을 날짜와 시간을 알아보기 쉬운 형태로 돌려준다.
          ```python
          >>> time.asctime()
          'Sat Jan 5 11:55:39 2019'
          ```
      4. time.strftime(포맷코드, 시간)  
         strf함수의 포맷코드를 사용해 시간을 여러 형태로 표현할 수 있다.
          ```python
          >>> time.strftime('%x', time.localtime())
          '01/05/19'   # '%x'는 설정된 local을 기준의 날짜를 출력한다. 
          >>> time.strftime('%X', time.localtime())
          '12:12:41'   # '%X'는 설정된 local을 기준의 시간을 출력한다. 
          >>> time.strftime('%c', time.localtime())
          'Sat Jan  5 12:12:53 2019'   # '%c'는 설정된 local을 기준의 요일, 날짜, 시간을 출력한다. 
          ```
      5. time.sleep(시간 간격)  
         인수로 받은 시간 간격을 두고 명령을 수행한다. 주로 루프(loop) 안에 사용한다. 
          ```python
          # sleep1.py
          import time
          for i in range(10):
              print(i)
              time.sleep(1)  # 인수의 시간 단위는 초이며 형태는 실수이다. 반복문을 수행하면 1초 간격으로 0부터 9까지 출력한다.
          ```
8. calendar
  + 달력을 볼 수 있게 해주는 모듈이다.
      1. calendar.calendar(연도)  
         입력값으로 받은 연도의 전체 달력을 돌려준다.
          ```python
          >>> import calendar
          >>> print(calendar.calendar(2019))
          '    2019\n\n ... 30 31\n'
          ```
      2. calendar.prcal(연도)  
         calendar.calendar()와 같이 입력한 해의 전체 달력을 돌려주며, 결과값이 calendar함수보다 보기 편하다.(일반 달력과 동일함)
          ```python
          >>> calendar.prcal(2019)
          # 결과값으로 일반 달력과 동일한 형태의 2019년 달력을 돌려준다.
          ```
      3. calendar.prmonth(연도, 월)  
         입력한 연도의 해당 월 달력을 돌려준다.
          ```python
          >>> calendar.prmonth(2019, 1)
          # 결과값으로 일반 달력과 동일한 형태의 2019년 1월 달력을 돌려준다.
          ```
      4. calendar.weekday(연, 월, 일)  
         입력받은 날짜에 해당하는 요일을 돌려준다. 결과값은 0부터 6까지의 숫자이며, 각 숫자는 순차적으로 월요일부터 일요일까지를 의미한다.
          ```python
          >>> calendar.weekday(2019, 1, 5)
          5  # 토요일을 의미한다.
          >>> calendar.weekday(2019, 1, 7)
          0  # 월요일을 의미한다.
          ```
      5. calendar.monthrange(연, 월)  
         입력받은 달 1일의 요일 정보와 해당 월의 총 일수를 튜플 형태로 돌려준다.
          ```python
          >>> calendar.monthrange(2019, 1)
          (1, 31)  # 2019년 1월 1일은 화요일(1)이며, 총 일수는 31일이다.
          ```
9. random
  + _To be completed_
