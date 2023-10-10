# intro

### install and start jupyterLab
1. jupyter 홈페이지에서 jupyterLab의 설치 방법을 확인할 수 있다.
2. terminal을 열어서 **pip install jupyterlab**을 통해 설치한다.
3. terminal에서 **jupyter lab**을 입력하여 실행시킨다.
4. **<ctrl + c>** or **<ctrl + x>**로 실행중인 jupyter Lab을 *종료* 할 수 있다.

### 단축키
- **ctrl + enter** : 현재의 셀을 실행
- **shift + enter** : 현재의 셀을 실행 & 다음 셀로 이동 
- **alt + enter** : 현재의 셀을 실행 & 새로운 셀을 추가
- **m** : 입력 방식을 Markdown으로 변경
- **y** : 입력 방식을 Code로 변경

### tip
- jupyter에서 실행은 셀 좌측에 표기되는 번호 순서로 실행된다.
- kernel에서 실행 순서를 초기화 할 수 있다.
- `*`은 셀이 실행중임을 의미한다. 

## 0.0 데이터 타입
1. number
2. boolean
3. string

## 0.1 자료구조
- 시퀀스 자료형
1. [list] : mutable
2. (tuple) : immutable
3. range() : mutable
4. 'string' : mutable

- 시퀀스가 아닌 자료형
1. {set} : mutable
2. {dic:tionary} : mutable



---

## 1. 변수

<변수이름> = <값>
- <변수이름>은 어떤 이름이든 상관없음
- 영어, 숫자, `_` 를 이용하여 선언
- 키워드는 사용불가 ex) True, False ....

### 1.1 number

- int
: 정수

```python
a = 10
type(a)
```

- float
: 실수
```python
b = 1.1
type(b)
```

- complex
: 복소수, real은 실수부분 / imag는 허수부분

```python
c = 1.1-4j
type(c)
c.real
c.image
```

### 1.2 boolean
: `True`, `False`로 이루어진 변수 타입이다.  
- **0**은 **False**를 나타낸다.

### 1.3 none
: 데이터가 없음을 의미한다.

### 1.4 string
: 문자열. `'`, `"`를 이용하여 표현한다. `'''`를 사용하여 여러 줄을 작성할 수도 있다.
```python
a ='hello'
b = "world"
c = input() # input은 ()안의 데이터를 의미한다. 단, str 데이터로 입력된다.
```
- **string interpolation**
: 다음은 문자열 안에 변수를 넣는 방식이다. 

1. %-fomatting
```python
age = 10
print('홍길동은 %s살입니다.'%age)
```
2. str.format()
```python
print('홍길동은 {}살입니다.'.format(age))
```

3. f-string
```python
print(f'홍길동은 {age}살입니다.')
```

> 위 경우 모두 <홍길동은 10살입니다.> 가 print 된다.

## 2. 연산자

### 2.1 산술연산자

- **a + b** : 덧셈  
- **a - b** : 뺄셈  
- **a * b** : 곱셈  
- **a / b** : 나눗셈  
- **a ** b** : 지수 a^b  
- **a // b** : a를 b로 나눈 몫  
- **a % b** : a를 b로 나눈 나머지  
- **divmod(a, b)** : a를 b로 나눈 몫과 나머지

### 2.2 비교연산자

- **a > b** : 부등호 초과  
- **a < b** : 부등호 미만  
- **a >= b** : 부등호 이상  
- **a <= b** : 부등호 이하  
- **a == b** : 등호  
- **a != b** : 같지 않음

### 2.3 논리연산자

- **and** : 양쪽 모두 `True`일 때, True를 반환
- **or** : 양쪽 모두 `False`일 때, Fasle를 반환
- **not** : 값을 반대로 전환

```python
# 단축평가(and)
print(3 and 5) # 앞의 데이터가 True이고 뒤의 데이터가 True인데, 마지막 True를 반환.
print(3 and 0)
print(0 and 5) #앞의 데이터가 False이므로 False를 바로 반환. 뒤의 데이터 중요하지 않음.
print(0 and 0)
```
> 5  
0  
0  
0

```python
# 단축평가(or)
print(3 or 5) #앞의 데이터가 True이므로 True를 바로 반환. 뒤의 데이터 중요하지 않음
print(3 or 0) 
print(0 or 5)
print(0 or 0) #앞의 데이터가 False이고 뒤의 데이터가 False인데 마지막 False를 반환.
```
> 3  
3  
5  
0


### 2.4 복합연산자

```python
a = a + b
a = a - b
a = a * b
a = a / b
a = a ** b
a = a // b
a = a % b
```
> 위의 연산자는 다음과 같이 표현할 수 있다.
```python
a += b
a -= b
a *= b
a /= b
a **= b
a //= b
a %= b
```

### 2.5 기타연산자

- **str 끼리의 합** : *str1 + str2* 는 *str1str2*로 나타낸다.
```python
a = 'hi '
b = 'hello'
a + b
``` 
> hi hello

- **list 끼리의 합** : *list1 + list2*는 list1list2로 나타낸다.
```python
a = [1, 2, 3]
b = [3, 4, 5]
a + b
```
>[1, 2, 3, 3, 4, 5]

- **in** : 자료에 데이터가 있는지 확인한다.
```python
print('a' in 'apple') #앞의 문자가 뒤의 문자에 들어있는지 물음
print('z' in 'apple')
print(1 in [1, 2, 3])
print(0 in [1, 2, 3])
```
>True  
False  
True  
False

- **메모리에 관해**
: 메모리 주소가 다르면 값을 다르게 인식한다.

```python
a = 123123
b = 123123
print(a is b) # a와 b의 메모리 주소가 다르기 때문에 a와 b는 같지 않다.
```
> False
```python
a = 10
b = 10
print(a is b) # -5 ~ 256은 python에서 이미 할당 되어있기에 a와 b의 주소가 같아서 서로 같다.
```
> True

### 2.6 연산자의 우선순위
: 연산자의 우선순위는 다음과 같다.

0. ()를 통해 그룹
1. **
2. 산술연산자(*, /)
3. 산술연산자(+, -)
4. 비교연산자(is, in)
5. not
6. and, or 

## 3. 형변환

### 3.1 암시적 형변환
- **boolean -> int**
: boolean을 int와 연산하는 경우, True는 1로 False는 0으로 바뀐다.
```python
a = True
b = False
c = 1
print(a + c) #True는 1로 바뀜
print(b + c) #False는 0으로 바뀜
```
> 2  
1

- **int**, **float**, **complex**를 연산하는 경우에도 암시적 형변환이 이루어진다.

### 3.2 명시적 형변환
: type을 지정하여 형변환을 해주는 방식이다.
```python
a = 1
b = '번'
print(str(a) + b) #str()은 값을 string으로 변환해준다.
```
> 1번

```python
a = '100'
print(type(int(a))) #int() 값을 int로 변환해준다.
```
> <class 'int'>

```python
a = input()
print(type(a)) #input()에 값을 입력하면 그 값은 string으로 입력된다.
```
> <class 'str'>

```python
a = '1.2'
print(type(float(a)))
```
> <class 'float'>

```python
a = 1
b = 0
c = 100
print(bool(a))
print(bool(b))
print(bool(c))
```
> True  
False  
True

```python
print(bool('')) #공백이기 때문에 False 출력
print(bool('a'))
```
> False  
True

## 4.시퀀스(sequence) 자료형
: 시퀀스는 데이터의 순서대로 나열된 자료구조이다. 단, 순서대로 나열되어 있다는 것은 정렬된 것과는 다르다.

### 4.1 list(배열)
- 선언 : <변수이름> = [value1, value2, value3]
- 접근 : <변수이름>[index]

```python
location = ['서울', '대전', '부산']
print(location)
print(location[0]) # 왼쪽에서부터 셈
print(location[-1]) # 오른쪽에서부터 셈

location[2] = '제주'
print(location)
```
> ['서울', '대전', '부산']  
서울  
부산  
['서울', '대전', '제주']

### 4.2 tuple
- 선언 : <변수이름> = (value1, value2, value3)
- 접근 : <변수이름>[index]
- *list*와 유사하지만 *tuple*은 **수정불가능(immutable)**하다.

```python
t = (1, 2, 3)
print(t)
print(t[2])
```
> (1, 2, 3)  
3

- 변수의 데이터 스왑
```python
x, y = (1, 2)
print(x, y)

x, y = y, x
print(x, y) # 변수의 데이터를 스왑
```
> 1 2  
2 1

### 4.3 range
- range(n) : 0부터 n-1까지 범위
- range(n, m) : n부터 m-1까지 범위
- range(n, m, s) : n부터 m-1까지 범위, +s만큼 증가하는 범위
```python
print(range(3))
list(range(3))

list(range(3, 5))

list(range(0, 8, 2))
```
> range(3)  
[0, 1, 2]  
[3, 4]  
[0, 2, 4, 6]

### 4.4 string
기본 데이터 구조 참고

### 4.5 시퀀스에서 사용 가능한 연산/함수

```python
my_list = [1, 2, 3, 4, 5]
my_tuple = (11, 22, 33, 44, 55)
my_range= range(1, 10, 2)
my_string = '일이삼사오'
```

- **indexing** : 자료에서 원하는 반환한다.
```python
print(my_list[1])
print(my_tuple[1])
print(my_range[1])
print(my_string[1])
```
> 2  
22  
3  
이

- **slicing** : 자료를 원하는 만큼 자른다.
```python
print(my_list[1:3]) # 1번째 데이터 ~ (3-1)번째 데이터까지
print(my_tuple[1:3])
print(my_range[1:3])
print(my_string[1:3])
```
> [2, 3]  
(22, 33)  
range(3, 7, 2)  
이삼

```python
tip : 공백을 이용하여 리스트의 처음과 끝의 범위를 지정할 수 있다.
print(my_list[ :3]) # 앞의 공백은 처음부터를 의미
print(my_list[3: ]) # 뒤의 공백은 끝까지를 의미
```

- **in** : 데이터가 시퀀스 안에 존재하는지 확인할 수 있다.
```python
print(1 in my_list) # in 데이터가 시퀀스 안에 존재하는지 물음
print(1 in my_tuple)
print(1 in my_range)
print('일' in my_string)
```
> True  
False  
True  
True 

- **not in** : 데이터가 시퀀스 안에 존재하지 않는지 확인할 수 있다.
```python
print(1 not in my_list) # in 데이터가 시퀀스 안에 존재하지 않는지 물음
print(1 not in my_tuple)
print(1 not in my_range)
print('일' not in my_string)
```
> False  
True  
False  
False

- **시퀀스의 연산** : 시퀀스의 연산은 다음과 같다.
```python
# list와 tuple은 자료가 이어서 붙여진다. 
print(my_list + [1, 2, 3, 4, 5]) 
print(my_tuple + (1, 2, 3))
```
> [1, 2, 3, 4, 5, 1, 2, 3, 4, 5]  
(11, 22, 33, 44, 55, 1, 2, 3)

```python
# 시퀀스에서 곱셈은 다음과 같은 결과를 가져온다.
print(my_string * 2)
print(my_list * 2)
print([[0] * 2] * 2)
```
> 일이삼사오일이삼사오  
[1, 2, 3, 4, 5, 1, 2, 3, 4, 5]  
[[0,0], [0,0]]

- **기타** : 이외의 여러 명령어는 [여기](https://docs.python.org/ko/3/tutorial/index.html)에서 확인할 수 있다.

## 5. 시퀀스데이터가 아닌 자료구조

### 5.1 set
: 수학에서 사용하는 집합과 동일하게 처리(중복된 값이 없음)
- 선언 : <변수이름> = {value1, value2, value3}
```python
my_set_a = {1, 2, 3, 4, 5}
my_set_b = {1, 3, 5, 7, 9}

print(my_set_a - my_set_b) # 차집합. 앞의 집합에서 뒤의 집합과의 교집합을 뺌.
print(my_set_a | my_set_b) # 합집합
print(my_set_a & my_set_b) # 교집합
```
> {2, 4}  
{1, 2, 3, 4, 5, 7, 9}  
{1, 3, 5}

```python
my_list = [1, 2, 3, 1, 4, 1, 2, 3, 5, 6, 7, 8, 2, 2] 
print(set(my_list)) # 중복된 자료를 제외시킨다.
```
> {1, 2, 3, 4, 5, 6, 7, 8}

### 5.2 dictionary
- 선언 : <변수이름> = {key1 : value1, key2 : value2, key3 : value3}
- 접근 : <변수이름>[key]
- dictionary는 key와 value가 쌍으로 이뤄져있다.
- key에는 immutable한 모든 값을 사용가능. (불변값 : string, intger ...)
- value에는 모든 데이터 가능. (list, dict ...)

```python
my_dict = {'서울': '02', '경기': '031'}
my_dict['서울']
```
> '02'
- **dictionary 데이터를 불러오기 / 내부에 dictionary 설정**
```python
dict_a = {
    'name': 'jiho', 
    'age': 28,
    'location' : 'seoul',
    'numbers' : [1, 2, 3, 4, 5],
    'friends': {
        'a': 27,
        'b': 29,
    },
}

print(dict_a['age'])
print(dict_a['numbers'])
print(dict_a['numbers'][3])
print(dict_a['friends']['b'])
```
> 28  
[1, 2, 3, 4, 5]  
4  
29 

- **dictionary의 목록 확인하기**

```python
print(dict_a.keys()) #dict 안의 key 목록을 확인
print(dict_a.values()) # dict 안의 values 목록을 확인
```
> 
dict_keys(['name', 'age', 'location', 'numbers', 'friends'])  
dict_values(['jiho', 28, 'seoul', [1, 2, 3, 4, 5], {'a': 27, 'b': 29}])