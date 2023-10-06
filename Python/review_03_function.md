# 함수(function)
- dir(__builtins__) : 파이썬 내장함수 리스트를 볼 수 있다. 
## 함수의 선언과 호출

- 함수의 선언 :  
```python
def func_name(parameter1, parameter2):
    code1
    cod2
    ...
    return value
```

- 함수의 실행:
```python
func_name(parameter1, parameter2)
```

```python
# 사각형의 면적과 둘레를 구하는 함수를 만들어보자
def rectangle(height, width):
    area = height * width
    perimeter = (height + width) * 2
    print(area, perimeter)

rectangle(2, 3)
rectangle(4, 5)
```
> 6 10  
20 18

```python
# 두개의 정수를 받아서 큰 수를 출력하는 함수 만들기
def my_max(num1, num2):
    if num1 > num2:
        print(num1)
    elif num1 < num2:
        print(num2)
    else:
        print(num1)

my_max(1, 2)
my_max(3, 2)
```
> 2  
3

## 함수의 return

- 함수가 **return을 만나면 해당 값을 반환**하고 함수를 종료
- 만약 **return이 없다면 None을 자동으로 반환** *ex)위의 예시 중 함수 내에 print만 있는 경우는 None이 반환 된 상태*
- return은 오직 **하나의 객체만을 반환**

```python
# 두개의 정수를 받아서 큰 수를 반환하는 함수 만들기
def my_max2(num1, num2):
    if num1 > num2:
        return num1
    elif num1 < num2:
        return num2
    else:
        return num1

my_max2(1, 2)
```
>2

```python
# list1과 list2의 각 자료의 총합이 더 큰 list를 반환하는 함수 만들기

def my_list_max(list1, list2):
    if sum(list1) > sum(list2):
        return list1
    elif sum(list1) < sum(list2):
        return list2
    else:
        return list1

my_list_max([1, 2, 3,], [3, 4, 5])

```
> [3, 4, 5]

## 함수의 인수

### 위치인수
: 기본적으로 함수는 인수의 위치로 판단한다.
```python
# 원통의 부피를 구하는 과정에서 인수의 위치가 다를 경우 다른 결과를 내게된다.
def cylinder(r, h):
    return 3.14 * r**2 * h


print(cylinder(10, 5))
print(cylinder(5, 10))

```
>1570.0  
785.0

### 기본값
: 변수의 위치에 기본값을 할당할 수 있다.
```python
def func(p1=v1): #p1 변수에 v1 기본값 할당
    code
    ...
    return p1
```
```python
# ex)
def greeting(name='익명'): # 데이터가 없을 경우 기본값 데이터를 사용함
    return f'{name}님 안녕하세요!'

print(greeting())
print(greeting('길동'))
```
>익명님 안녕하세요!  
길동님 안녕하세요!


**※주의**
: 입력값과 기본값의 위치에 주의를 하여야한다. 
```python
def greeting(name='익명', age):
    return f'{name}님은 {age}살 입니다'
greeting(25)
```
> 위의 코드는 age에 기본값이 없기 때문에 입력값이 어느 위치에 들어가야 하는지 정해지지 않아 오류가 남.
```python
def greeting(age, name='익명'):
    return f'{name}님은 {age}살 입니다'
greeting(25)

# age가 먼저 입력이 되고 name에는 기본값이 나온다. (입력 위치가 정해짐)
```
> '익명님은 25살 입니다.' 

### 키워드 인자
함수를 호출(실행)할 때 내가 원하는 위치에 직접적으로 특정인자를 전달 가능

```python
def greeting(name='익명', age):
    return f'{name}님은 {age}살 입니다'

print(print(greeting(20, '길동')))
print(greeting(age=30, name='길동'))
```
>길동님은 20살입니다.  
길동님은 30살입니다.

## 가변 인자 리스트
: 변수의 갯수가 정해지지 않았을 때 `*`을 사용함
```python
def func(*word):
    code
    ...
```

```python
def my_print(*words):
    print(words)
    print(type(words))

my_print('a', 'b', 'c', 'd')
```
> ('a', 'b', 'c', 'd')

```python
# 여러개의 숫자를 받아 그중 가장 큰 수를 반환(1)
def my_max1(*numbers):
    return max(numbers)
# 여러개의 숫자를 받아 그중 가장 큰 수를 반환(2)
def my_max2(*numbers):
    result = numbers[0] #첫번째 자료를 저장

    for number in numbers: #나머지 자료와 비교
        if result < number:
            result = number

    return result

print(my_max1(1, 2, 3))
print(my_max1(-1, -2, -3))
print(my_max2(-1, -2, -3))
```
> 3  
-1   
-1

### 정의되지 않은 키워드 인자 처리하기

```python
def func(**kwargs):
    code
    ...
```

```python
def fake_dict(**kwargs): #**로 정의되지 않은 키워드 인자를 처리할 수 있게 함.
    for key, value in kwargs.items():
        print(f'{key}는 {value}입니다.')

fake_dict(a=10, b=20) #key값에 a,b / value값에 10, 20
```

### dictionary를 인자로 넣기(unpacking)

```python
# 회원가입 시 비밀번호 재확인이 일치하는지 출력하는 코드를 만들어보자. 
def sign_up(pw, pw_confirmation):
    if pw == pw_confirmation:
        print('일치합니다.')
    else:
        print('일치하지 않습니다.')

sign_up('1234', '1234',)
sign_up('1234', '4321',)
```
> 일치합니다.  
일치하지 않습니다. 

### lambda 표현식
: 주로 일회용 함수를 만들 때 사용

```python
# 아래의 두 코드는 동일한 코드이다.
(lambda x, y: x + y)(1, 2)

def my_sum(x, y):
    return x + y
my_sum(1, 2)
```
> 3

### type hint

함수 데이터 입력값에 오류가 있을 경우 hint를 남길 수 있다.
```python
def my_sum(a: int, b: int) -> int: #데이터 입력을 할 때, int가 아니면 int를 입력하라는 힌트를 남김.
    return a + b
```

### 이름공간(scope)

python에서 사용되는 이름들은 이름공간(namespace)에 저장되어 있다. 중복되는 이름이 있을 경우 아래의 순서(L, E, G, B)에 저장된 이름을 사용한다.

- Local scope : 정의된 함수 내부
- Enclosed scope : 상위 함수
- Global scope : 함수 밖의 변수 혹은 import된 모듈
- Built-in scope : python이 기본적으로 가지고 있는 함수 혹은 변수

## 재귀
: 재귀 함수는 함수 내부에서 자기 자신을 호출하는 함수를 의미한다.

- 팩토리얼(n!) 만들기
```python
# n! = (n-1)! (단, n>1인 정수)이라고 할 수 있다. 따라서 재귀 함수를 이용하면 다음과 같이 팩토리얼 함수를 만들 수 있다. 

def factorial(n):
    if n <= 1: # n이 1인 경우를 제외하기 위해 작성
        return 1
    else:
        return factorial(n-1) * n 

print(factorial(5))
```
>120

- 피보나치 수열 만들기
```python
# 피보나치 수열을 정리하면 다음과 같다.
# f(n) = f(n-1) + f(n-2) (단,n>2 인 정수이고 f(0) = f(1) = 1 )

def fib_rec(n):
    if n == 0 or n == 1: 
        return 1 #f(0) = f(1) = 1
    else:
        return fib_rec(n-1) + fib_rec(n-2) #f(n) = f(n-1) + f(n-2)

print(fib_rec(10))
```
> 89