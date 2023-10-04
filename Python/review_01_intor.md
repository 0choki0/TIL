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


## 2. 연산자

### 2.1 산술연산자

### 2.2 비교연산자

### 2.3 논리연산자

### 2.4 복합연산자

### 2.5 기타연산자

### 2.6 연산자의 우선순위


## 3. 형변환

### 3.1 암시적 형변환

### 3.2 명시적 형변환


## 4.시퀀스(sequence) 자료형

### 4.1 list(배열)

### 4.2 tuple

### 4.3 range

### 4.4 string

### 4.5 시퀀스에서 사용 가능한 연산/함수


## 5. 시퀀스데이터가 아닌 자료구조

### 5.1 set

### 5.2 dictionary

