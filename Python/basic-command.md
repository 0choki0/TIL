# basic-command  

python의 basic 문법을 학습해보자.  
[이곳](https://docs.python.org/ko/3/tutorial/index.html)에서 python의 문법을 확인할 수 있다.

---

## 기초  

- **python 사용시 유의해야 할 오탈자**  

&nbsp; *1. 대문자와 소문자의 구분*
> apple / Apple은 서로 의미가 다르다.

&nbsp; *2. 공백의 구분*
> git add. / git add . 은 서로 의미가 다르다.

&nbsp; *3. 문자의 구분*
> message / massage 는 서로 의미가 다르다.

- **저장 - 변수**  
&nbsp; 일반적으로 dirtionary는 *값(value)*를 *key*에 **저장**하여 사용한다. **`=`** 은 key에 value를 저장하는 역할을 수행한다.
> key = variable

*1. 숫자(int)*  
&nbsp; : key값으로 숫자(int)를 저장한다.
```python
a = 10
```

*2. 글자(string)*  
&nbsp; : key값으로 글자(string)를 저장한다.
```python
b = '5'
```

*3. 참/거짓(bloolean)*  
&nbsp; : key값으로 참/거짓을 저장한다. 
```python
c = True
d = False
```

*4. 리스트(list)*  
&nbsp; : key값으로 리스트(list)를 저장한다. 리스트의 항목은 [] 안에 입력한다. 
```python
age_list = [10, 20, 30]
age_list = {
    'a': 10
    'b': 20
    'c': 30
}
print(age_list['a'])
```
> 위 코드를 작성하면 **10** 이 나온다.  

- **조건**

*1. if문*  
&nbsp; 제어 흐름도구이다. if는 구문이 참일 경우 코드를 계속 실행한다. elif는 실행된 if 외의 구문이 참일 경우 코드를 계속 실행한다. else는 if 구문이 거짓일 경우 코드를 실행한다. 아래의 예시로 쉽게 이해하자.

```python
age = 10

if age >= 20:
    print('성인')
elif age > 8:
    print('청소년')
else:
    print('어린이')
```
> age가 10이므로 청소년이 print 될 것이다. 

변화하는 age의 값에 따라 20살 이상이면 성인, 20살 미만 8살 초과이면 청소년, 이외의 경우 어린이로 print 된다.


- **반복**

*1. while문*  
&nbsp; 조건문이 True인 경우 내부의 수행 부분을 진행하고, 조건문이 False인 경우 while문을 빠져나간다. 강제로 빠져나가고 싶을 땐 break문을 사용한다.

```python

menus = ['짜장', '짬뽕', '우동']

n = 0 
while n < 3:
    print(menus[n])
    n = n + 1
    if n == 3:
        print("더이상 메뉴가 없습니다.")
        break        
```

*2. for문*   
&nbsp; 순서열의 처음부터 끝까지 반복한다. 문자열, 리스트, 튜플 구성요소를 순회하다가 더 이상 순회할 것이 없다면 for문을 빠져나오거나, 순회를 끝내기 전에 return값이 나온다면 for문이 종료된다.  

```python
menus = ['짜장', '짬뽕', '우동']

for meu in menus:
    print(menu)

```

*참고*
for문은 새로운 변수를 만들 수 있다는 특징이 있고, while 참/거짓을 판별할 수 있다는 특징이 있다. 


## 함수 - 기초

함수를 통해 여러 코드를 작성할 수 있다. [이곳](https://docs.python.org/ko/3/tutorial/index.html)을 참고하여 원하는 함수의 학습을 하도록 하자.

- import  

&nbsp; import는 라이브러리 안에 이쓴 파일을 사용할 수 있게 해주는 명령어이다. 예를들어 calendar 함수를 사용하고 싶으면 
```python
import calendar
calendar.prompt(year, month)
```
을 입력하면 된다. from을 사용하면 파일명을 쓰지 않아도 된다.
```python
from calendar import prompt #모든 calendar를 사용하는 코드에 from을 적용하려면 import 뒤에 *을 입력하면 된다.
prompt(year, month)
```

- requests  
&nbsp; requests는 파이썬에서 HTTP를 사용하기 위해 쓰여지는 라이브러리이다.
    - status  
    : request의 상태를 나타낸다. 흔히 아는 *404 not found*에서 404가 코드명이고 not found가 상태이다. 코드명에 따른 상태는 [이곳](https://github.com/psf/requests/blob/c45a4dfe6bfc6017d4ea7e9f051d6cc30972b310/requests/status_codes.py)에서 확인할 수 있다.  

    - get
    : get method로 데이터를 보내는 법은 다음과 같다.
    ```python
    import requests
    # URL에 데이터를 입력해서 전송한다.
    URL = "<데이터 주소>"
    res = requests.get
    print(res.status_code)
    ```
