# 객체 지향 프로그래밍(OOP)

- 클래스(clase) : 같은 종류의 집단에 속하는 속성과 행위를 정의한 것
- 인스턴스(instance) : 클래스를 실제로 메모리상에 할당한 것
- 속성(attribute) : 클래스/인스턴스가 가지고 있는 **데이터**/값
- 행위(method) : 클래스/인스턴스가 가지고 있는 **함수**/기능

## Class
> 클래스를 데이터를 입력받아 저장해주는 템플릿이라고 생각하자. 사람 A, B가 각각 템플릿에 데이터를 입력하면 A템플릿과 B템플릿이 생성된다. A템플릿과 B템플릿은 구조는 같으나 그 데이터는 서로 상이하다. 

- 클래스 선언
클래스 선언의 형식은 다음과 같다.
```python
class ClassName:
    atrribute = value

    def method_name(self):
        code
```
- 인스턴스화
인스턴스화는 다음과 같이 해준다.
    ClassName()

```python
# Class를 만들어보자(1)

#선언 (name속성을 kim으로 하고, hello를 반환하는 함수를 만들어보자)
class MyClass:
    name = 'kim'

    def hello(self):
        return 'hello'

#인스턴스화 (class를 a와 b 에 할당해보자)
a = MyClass() # class를 a에 인스턴스화
a.name #기본값인 kim을 가짐
a.hello #기본값인 hello를 반환

b = MyClass()
b.name = 'lee' # b의 클래스에서 name lee로 저장
```

```python
# Class를 만들어보자(2)

claas Phone:
    power = False
    number = '010-0000-0000'
    
    def on (self): 
        if self.power == False:
            self.power = True

    def off(self):
        if self.power == True:
            self.power = False

    def call(self, target):
        if self.power == True:
            print(f'제 번호는 {self.number}입니다.')
            print(f'{target}으로 전화 거는중입니다.')
        else:
            print('핸드폰을 켜주세요.')
```
```python
my_phone = Phone()

my_phone.number = '010-1234-5678' # my_phone의 클래스 number를 특정

my_phone.on() # my_phone의 클래스의 on 함수 실행
my_phone.call('112') # my_phone의 클래스의 call을 '112'를 받아서 실행
```

### 생성자, 소멸자

- 생성자
: 클래스를 생성하면서 바로 실행한다. **__init__**으로 쓴다.
```python
class MyClass:
    name = 'no_name'
    def __init__(self, name='익명이'): #MyClass를 호출하면 init이 실행 
        self.name = name

a = MyClass() #a에 클래스 호출
a.name # a는 익명이라는 name이 담김
MyClass.name #MyClass의 name은 no_name

a.location = 'seoul' #a클래스에 location이라는 새로운 변수를 입력
```

- 소멸자
: 클래스를 소멸시킨다.
```python
class MyClass:
    def __del__(self): #del을 이용하여 호출된 클래스를 소멸 시킨다.
        pass

a = MyClass() # 클래스 호출
del a # a클래스 소멸 

```

### 클래스 변수 / 인스턴스 변수
: 클래스 변수는 클래스 선언 블록 최상단에 위치하는 변수들을 의미한다. 인스턴 변수는 인스턴스 내부에서 생성한 변수를 의미한다.

```python
 class MyClass:
    a = 'hi' # 여기서 a가 클래스 변수이다.

    def __init__(self, name):
        self.b = 'hello' # 여기서 b가 인스터스 변수이다. 인스턴스 변수는 첫번째 인자로 self를 받는다.

    def c(self):
        c = 'wow' #c 또한 인스턴스 변수이다. (생성자일 필요 없음을 의미)
```

### 인스턴스메소드 / 클래스 메소드 / 스태틱메소드
- 인스턴스 메소드
: 일반적인 메소드로 첫번째 인자(self)로 자기 자신을 받는다.

- 클래스 메소드
: 첫번째 인자(cls)로 클래스 변수를 받는다. 자신의 클래스에 접근할 때 사용한다. 인스턴스 메소드와 구분하기 위해서 인자는 보통 cls로 쓴다.

- 스태틱 메소드
: 첫번째 인자를 필요한 인자로 받는다. 즉, 클래스에 소속된 함수가 아니라 일반 함수처럼 사용된다. 

```python
class MyClass:
    def instance_method(self): # 인스턴스 메소드
        pass
    @classmethod #데코레이트 클래스메소드로 클래스 메소드로 변환해줌
    def class_method(cls): # 자기 자신의 클래스에 접근할 때 사용한다. 
        return cls
    @staticmethod #데코레이트 스태틱메소드로 스태틱 메소드로 변환해줌
    def static_method(): # 클래스에 소속된 함수가 아니라 일반 함수처럼 정의해줌. 따라서 첫번째 인자부터 자기자신이 아닌 필요한 인자를 받음
        return 'hello'
```

```python
#활용 예시
class Puppy:
    num_of_puppy = 0 # 클래스 변수
    
    def __init__(self, name):  #생성자, 인스턴스 메소드
        self.name = name
        Puppy.num_of_puppy  += 1

    @classmethod 
    def get_status(cls):   # 클래스 메소드
        print(f'현재 강아지는 {cls.num_of_puppy}마리입니다.')

    @staticmethod
    def bark(msg): # 스태틱 메소드
        return msg

p1 = Puppy('흰둥이')
p2 = Puppy('시로')
p3 = Puppy('화이트')

print(Puppy.num_of_puppy) # 생성자를 3번 받았으므로 클래스 변수는 3

Puppy.get_status() # 클래스메소드는 클래스 변수를 받으므로 3
p1.get_status() # 클래스메소드는 클래스 변수를 받으므로 3

print(p1.bark('멍멍')) # 스태틱메소드는 필요한 인자를 받으므로 멍멍을 출력
print(p2.bark('그르릉')) # 스태틱메소드는 필요한 인자를 받으므로 그르릉을 출력
```

### 상속
: 클래스에 클래스를 덫씌우는, 즉 클래스 간의 상속이 가능하다.

```python
class Person:

    def __init__(self, name):
        self.name = name

    def greeting(self):
        print(f'안녕하세요. {self.name}입니다.')

class Student(Person): # Student 클래스가 Person 클래스를 상속했다. 
    def __init__(self, name, student_id): #기존에 상속한 것 외의 새로운 코드
        self.name = name
        self.student_id = student_id


s1 = Student('hong', '1234') #상속 받은 name 인자 외에도 Student 클래스에서 인스턴스 메소드가 추가되었으므로 새로운 인자를 적어줘야 한다. 
```

#### 다중상속
: 상속은 단일로만 이루어지는 것이 아닌 여러 클래스를 상속할 수 있다. 단, 피상속 클래스의 클래스 변수가 충돌하는 경우 먼저 상속 받은 클래스 변수를 상속받는다.

```python
class Person:
    def __init__(self, name):
        self.name = name

    def breath(self):
        print('후하')

class Mom(Person):
    gene = 'xx'

    def swim(self):
        print('어푸어푸')      

class Dad(Person):
    gene = 'xy'

    def run(self):
        print('다다다')         

class Baby(Dad, Mom): # Dad 클래스와 Mom 클래스를 상속 받음
    pass  

b = Baby('금쪽이') #피상속에 정보가 없으면 한번더 피상속으로 넘어감
print(b.name)
print(b.gene) # 여러개의 클래스를 상속할 경우 앞의 상속이 우선시 됨

b.swim() # Mom 클래스의 인스턴스 메소드인 swim을 받음
b.run() # Dad 클래스의 인스턴스 메소드인 run을 받음

```



