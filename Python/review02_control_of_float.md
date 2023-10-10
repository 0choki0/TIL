# 제어문

## 조건문(if문)

```python
if <조건식>:
    if의 조건식이 참인 경우 실행하는 코드
else:
    if의 조건식이 거짓인 경우 실행하는 코드 
```
1. `if`문은 반드시 참/거짓을 판단 할 수 있는 `조건식`과 함께 사용한다.
2. `조건식`이 참인 경우 `:` 이후의 문장을 실행한다.
3. `조건식`이 거짓인 경우 `else:` 이후의 문장을 실행한다. 

---

다음은 if를 사용하여 input으로 mm/dd 를 입력하였을 때 그 값이 참이면 '크리스마스입니다.'를 출력하고 거짓이면 '크리스마스가 아닙니다.'를 출력하는 코드이다.

```python
my_string = input()

if my_string == '12/25':
    print('크리스마스입니다.')
else: 
    print('크리스마스가 아닙니다.')

```

---
다음은 두가지의 input 값의 홀수/짝수를 판별하는 방법이다.

```python
num = input('숫자를 입력해주세요 : ')
num = int(num)

if num % 2 == 1:
    print(f'{num}은(는) 홀수입니다.')
else:
     print(f'{num}은(는) 짝수입니다.')

```

```python
# if 조건식에 0, 1은 자동형변환이 일어나 False, True로 변환된다.
num = input('숫자를 입력해주세요 : ')
num = int(num)

if num % 2:
    print(f'{num}은(는) 홀수입니다.')
else:
     print(f'{num}은(는) 짝수입니다.')
```

### elif

```python
if <조건식>:
    if 조건이 참인 경우 실행
elif <조건식>:
    elif 조건이 참인 경우 실행
else:
    위의 조건식에 하나도 부합하지 않는 경우 실행
```

---

성적을 입력하면 성적에 따른 점수를 부여 코드를 짜보자.

```python
# # 90점 이상이면 A 
# 80점 이상이면 B
# 70점 이상이면 C
# 나머지는 F
# 단, 95점 이상일 경우 good을 추가로 입력해줌.

score = int(input('점수를 입력해주세요. :'))
m1 = '당신은'
m2 = '학점입니다.'
grade = ''
message = ''

if score >= 90:
    grade = 'A'
    if score >= 95:
        message = 'good'
elif score >= 80:
    grade = 'B'
elif score >= 70:
    grade = 'C'
else:
    grade = 'F'

print(m1, grade, m2, message)
```
### 조건표현식
```python
true_value if <조건식> else false_value
```
- 아래의 두 코드는 완전히 동일한 코드이다.

```python
if 1 < 2:
    print('True')
else:
    print('False')
```
> True

```python
print('True') if 1 <2 else print('False')
```
> True

```python
#다만 한줄로 적은 코드는 하나의 값으로 취급할 수 있다는 점에서 여러 줄의 코드와 차이를 보인다.
num = 5
value = num if num >= 0 else 0 
print(value)
```
> value

## 반복문
: 반복 실행을 하는 명령어이다.
### while문
*범위가 지정되어 있지 않는 것이 for문과 차이점이다.*
```python
    while <조건식>:
        실행할 코드
```

```python
a = 0

while a < 5:
    print(a, end = '')
    a += 1
```
> 01234

### for문
*범위가 지정되어 있는 것이 while문과 차이점이다.*
```python
    for vaiable in sequence:
        실행할 코드
```

```python
numbers = [1, 2, 3, 4, 5] #구조형 자료(list)

for number in numbers: #자료를 가져다 씀(범위가 지정되어 있음)
    print(number, end = '')
```
> 12345

- **practice** : 1~30까지 숫자 중에서 홀수를 모아서 리스트로 출력해보자

```python
my_list = []

for i in range(1, 31):
    if i % 2 == 1:
        my_list.append(i)

print(my_list)

```
> [1, 3, 5, 7, 9, 11, 13, 15, 17, 19, 21, 23, 25, 27, 29]

- **practice2** : 자료에 따라 범위 변경하기(len)

```python
menus = ['라면', '김밥', '떡볶이', '돈까스']
for menu in range(len(menus)):
    print(menus[menu], end = ', ')
```
> 라면,김밥,떡볶이,돈까스,

- **enumerate** : 구조형 자료의 원소에 순서값을 부여해주는 함수.

```python
my_list = ['a', 'b', 'c']
for i in enumerate(my_list):
    print(i)
```
>(0, 'a')  
(1, 'b')  
(2, 'c')

```python
my_list = ['a', 'b', 'c']
for i, l in enumerate(my_list):
    print(i, l)
```
>0 a  
1 b  
2 c

### dictionary 반복
1. for key in dict:
2. for key in dict.keys():
3. for value in dict.valuse():
4. for key, value in dict.item():

**- for key in dict:**  
&nbsp;&nbsp;&nbsp;: dictionary에 저장된 key를 순서대로 반복한다.  
**- for key in dict.keys():**  
&nbsp;&nbsp;&nbsp;: dictionary의 **key**값만을 추출한다.  
**- for value in dict.valuse():**  
&nbsp;&nbsp;&nbsp;: dictionary의 **value**값만 추출한다.  
**- for key, value in dict.item():**  
&nbsp;&nbsp;&nbsp;: dictionary의 **key값과 value값을 모두** 추출한다.

#### break
: 반복문을 종료시키는 키워드

```python
# 0~99까지 반복하는 코드에서 i 가 10이 넘을 경우 반복을 종료 시키게 하는 break 작성
for i in range(100):
    print(i)
    if i > 10:
        print('over 10!!')
        break
```
> over 10!!

#### continue
: continue 이후의 코드를 실행하지 않고 다음 반복을 실행

```python
# 1~9까지 반복하는 코드에서 짝수만을 출력하도록 continue 작성
for i in range(1, 10):
    if i % 2: # i를 2로 나눈 나머지가 True일 경우
        continue # 다음 반복문을 진행
    
    print(i, end='')

```
> 2468

#### else
: break를 만나지 않은 경우 반복이 진행된 후 실행
```python
# numbers를 반복하다가 4를 만나면 target을 출력하는 코드

numbers = [1, 2, 3, 4, 5]
target = 4

for i in numbers:
    if i != target:
        continue
    else:
        print('target')

```
>target

#### pass
: 코드 블럭을 임의로 완성시킴
```python
#임시로 오류가 생기지 않게 코드 블럭을 처리하는 용도. 주석으로 대체해도 됨.
if True:
    pass
```

### match
: 입력값에 따라 다른 코드를 실행하게 해줌
```python
match value:
    case 조건:
        실행할 코드
    case 조건:
        실행할 코드
    case _: #상기 조건 이외의 경우
        실행할 코드

```

```python
#상태가 400, 404 등등 상태에 따라 다른 실행을 하는 match 코드
status = 404
match status:
    case 400:
        print('bad request')
    case 404:
        print('not found')
    case _:
        print('something is wrong')  # 위의 case 외의 경우
    
```