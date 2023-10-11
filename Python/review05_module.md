# 모듈
: 파이썬 파일을 불러온다. 
```python
import <모듈이 있는 파일 이름>
# print(<모듈이 있는 파일 이름>)를 통해서 파일이 어느 위치에 있는지 확인할 수 있다.

```
## 패키지
: 파이썬 모듈들의 집합체를 패키지라 한다. 

- 패키지 만들기

```python
    myPackage/ # 폴더
        __init__.py #파이썬 인식 파일
        math # 폴더
            __init__.py #파이썬 인식 파일
            fibo.py # 파이썬 코드 파일
            fomula.py  # 파이썬 코드 파일
```
- 패키지 가져오기

위의 패키지가 있는 상황에서 fibo 모듈을 꺼내와서 사용하고자 한다. *(fibo 파일에는 피보나치 수열을 정의한 함수가 들어있다.)*

```python
#방법(1)
import mPackage # 패키지 전부를 가져옴

#방법(2)
from myPackage.math import fibo # 폴더를 찾아서 fibo 모듈을 가져옴

#방법(3)
from myPackage.math.fibo import fib_loop # fibo 모듈에서 원하는 코드(함수)를 가져옴

#방법(4)
from myPackage.math.fibo import * # fibo 모듈에서 모든 코드(함수)를 가져옴
```
- 불러오는 파일의 이름을 바꾸면서 가져오기

```python
from myPackage.math.fibo import fib_loop as f # fib_loop를 불러오면서 이름을 f로 수정하였다.
```

### 파이썬 내장 패키지
: 파이썬에는 여러 내장 패키지가 있다. [여기](https://docs.python.org/ko/3.11/library/index.html)에서 확인할 수 있다. 아래는 자주 사용되는 파이썬 내장 패키지 몇 가지를 소개한다. 

- math
: 수학과 관련된 모듈이 있는 패키지
```python

import math

print(math.pi, end = ' / ') # 파이 값

print(math.e, end = ' / ') # 자연로그값

print(math.ceil(math.pi), end = ' / ') # 소숫점 올림

print(math.factorial(5)) # 팩토리얼

```
>3.141592653589793 / 2.718281828459045 / 4 / 120

- random
: 랜덤 추출과 관련된 모듈이 있는 패키지. 단, 완전 랜덤이 아니라 계산된 랜덤이라 보안에는 사용하기에 적합하지 않다.

```python
import random
random.random() # 0~1 사이의 랜덤 숫자
random.randint(1, 20) # 범위에서의 정수 랜덤

random.seed(2) # 기반으로 하는 것. 예시에서는 2를 기반으로 설정
random.random() # 2를 기반으로 계산한 랜덤값

a = [1, 2, 3, 4, 5]
random.shuffle(a) # 리스트 요소 순서를 무작위로 섞어줌

rps = ['가위', '바위', '보'] 
random.choice(rps) # 리스트 안에서 무작위로 하나를 선택

random.sample(range(1, 46), 6) #범위에서 원하는 만큼의 샘플을 뽑음
```

- datetime
: 시간과 관련된 모듈이 있는 패키지

```python
from datetime import datetime

datetime.now() # 현재 시간을 데이터로 반환

datetime.today() # 오늘을 데이터로 반환 (yy mm dd tt 형식)

datetime.utcnow() #세계 표준 시간

now = datetime.now()
now.strftime('%Y년 %m월 %d일 %a') # 시간을 str으로 format함
```

```python
# datetime은 연산도 가능하다
from datetime import datetime
from datetime import timedelta # 차이값

birth = datetime(2023, 1, 1)
future = timedelta(days=3) # 3일

birth + future #생일 3일 뒤의 날짜를 반환

```