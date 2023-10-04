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

