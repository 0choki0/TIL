# 문자열 메소드(함수)

- 문자열은 immutable하기 때문에 수정 불가능하다.
```python
a = 'hello my name is hong'
a[0] = 'H' #첫 문자를 H로 변경하고자 함'
```
> 문자열은 immutable이기에 이 방식으로는 불가능.

---

- .capitalize()
: 시작하는 문자를 대문자로 바꿔준다.
```python
a = 'hello my name is hong'
a = a.capitalize()
print(a)
```
> Hello my name is hong

- .title()
: 단어마다 시작하는 문자를 대문자로 바꿔준다.
```python
a = 'hello my name is hong'
a = a.title()
print(a)
```
> Hello My Name Is Hong

- .upper()
: 모든 문자를 대문자로 바꿔준다.
```python
a = 'hello my name is hong'
a = a.upper()
print(a)
```
> HELLO MY NAME IS HONG

- .lower()
: 모든 문자를 소문자로 바꿔준다.
```python
a = 'HELLO MY NAME IS HONG'
a = a.upper()
print(a)
```
> hello my name is hong

- '구분자'.join(문자열로만 이루어진 list or tuple)
: 문자열로만 이루어진 list 혹은 tuple을 '구분자'를 이용하여 나누어준다. 단, 원본은 바뀌지 않는다.
```python
my_list = ['hi', 'my', 'name', ]
print('/'.join(my_list))
print(my_list)
```
> hi/my/name  
['hi', 'my', 'name']

- strip([chars])
: 문자열에서 가장자리를 지워준다

1) strip([char]) : 양쪽의 [char]을 지워준다. [char]이 없을시 기본값은 띄어쓰기 or \n 이다.
2) lstrip([char]) : 왼쪽 [char]을 지워준다. [char]이 없을시 기본값은 띄어쓰기 or \n 이다.
3) rstrip([char]) : 오른쪽 [char]을 지워준다. [char]이 없을시 기본값은 띄어쓰기 or \n 이다.

```python
my_string = ' hello \n  '
print(my_string.strip())
```
>hello

```python
my_string2 = 'hihihihellohihihi'
print(my_string2.strip(hi))
print(my_string2.lstrip('hi'))
print(my_string2.rstrip('hi'))
```
>ello
>ellohihihi
>hihihihello

- replace(old, new[, count])
: 특정 문자를 원하는 문자로 바꿔준다.
```python
a = 'wooooow'
print(a.replace('o', '!'), end = ' / ')
print(a.replace('o', '!', 3))
```
> w!!!!!w / w!!!oow

- find(x)
: 특정 문자의 위치를 찾아주는 함수
```python
a = 'apple'
print(a.find('e'), end = ' / ')
print(a.find('z')) #찾는 문자가 없을 경우 -1을 반환
```
> 4 / -1

- index(x)
: 특정 문자의 위치를 찾아주는 함수. 단, find와 다르게 찾는 문자가 없을 경우 error가 난다.

```python
a = 'apple'
print(a.find('e'), end = ' / ')
print(a.find('z')) #error
```
> 4 / error

- split('구분')
:  문자열을 '구분' 기준으로 나누어 준다. 

```python
a = 'my_name is '
print(a.split(), end = ' / ')
print(a.split('_'))
```
>['my_name', 'is'] / ['my', 'name is ']

- count(x)
: 특정 문자의 갯수를 세어준다.

```python
'wooooow'.count('o')
```
>5

# 리스트 메소드

- .append(x)
: 리스트 끝에 요소를 추가한다.

```python
num = [1, 2, 3,]
num.append(5)
print(num)
```
>[1, 2, 3, 5]

- .extend(iterable)
: 리스트에 iterable한(시퀀스 등 반복가능한) 데이터를 연결한다.

```python
num1 = [1, 2, 3]
num2 = [9, 10]

num1.extend(num2) #<num1 + num2> 와 같다
print(num1)
```
>[1, 2, 3, 9, 10]

- insert(idx, x)
: 원하는 위치에 데이터를 넣는다.

```python
num = [1, 2, 3,]
num.insert(1, 4)
print(num)
```
>[1, 4, 2, 3]

- .remove(x)
: 원하는 데이터를 앞쪽부터 삭제한다. 

```python
num = [1, 2, 3, 2, 4]
num.remove(2)
print(num)
```
>[1, 3, 2, 4]

- .pop(idx)
: 원하는 위치의 데이터를 삭제한다. pop은 지워진 인덱스 값을 반환한다.

```python
num = [1, 2, 3, 2, 4]
num.pop(2)
print(num)
```
>[1, 2, 2, 4]

- del [idx:idx]
: 리스트를 원하는 위치와 범위의 데이터를 삭제한다. 인덱스를 반환하지 않는다.

```python
num = [1, 2, 3, 2, 4]
del num[1:3]
print(num)
```
>[1, 2, 4]

- slice #
: 원하는 범위의 리스트를 출력한다. 즉, 원본을 변화시키지 않는다.

```python
num = [1, 2, 3, 2, 4]
n = num[1:3]
print(n)
```
>[2, 3]

- .sort()
: 리스트를 오름차순으로 정렬한다. reverse 값을 넣어 역순으로 바꿀 수 있다.
```python
num = [1, 5, 3, 2, 4]
num.sort()
print(num, end = ' / ')
num.sort(reverse = True)
print(num)
```
>[1, 2, 3, 4, 5] / [5, 4, 3, 2, 1]

- sorted
: 리스트를 정렬하여 출력한다. 즉, 원본은 변화하지 않는다.
```python
num = [1, 5, 3, 2, 4]
n = sorted(num)
print(n)
```
>[1, 2, 3, 4, 5]

- .reverse()  / reversed()  / 역순으로 반환
: 요소들의 순서를 뒤집는다.
```python
num = [1, 2, 3, 4, 5]
num.reverse() # reverse는 원본이 변화한다.
print(num)

num = [1, 2, 3, 4, 5]
n = list(reversed(num)) #uncomfortable이므로 list로 감싸줬다.
print(n)

num = [1, 2, 3, 4, 5]
n = num[: -1: -1] #처음부터 끝까지 역순으로 출력
print(n)
```
> [5, 4, 3, 2, 1]

## list copy
: 리스트를 변수에 저장하여 복사할 때, **주소값을 저장하는 것인지 아닌지** 확인할 필요가 있다.

```python
a = [1, 2, 3]
b = a
# 위의 경우, b에 a의 주소를 저장한 것이다. 따라서 b를 수정하면 a값도 수정된다.
b[0] = 4
# print(a) >> [4, 2, 3]

#만약 리스트를 복사하고 싶으면 다음과 같이 하면된다.
a = [1, 2, 3]
b = list(a)
#이 경우에는 b는 새롭게 정의된다.
```

## list comprehension
: 반복문을 사용하여 만드는 list를 더 간단히 코드를 짜보자.

```python
#각 요소를 세제곱하기(1)
numbers = list(range(1, 4))
result = []
for number in numbers:
    result.append(number ** 3)

#각 요소를 세제곱하기(2)
numbers = list(range(1, 4))
result2 = [ number ** 3 for number in numbers ]
```
> [1, 8, 27]

```python
#짝수만 고르기(1)
numbers = list(range(1,5))
even_list = []
for number in numbers:
    if number % 2 == 0:
        even_list.append(number)

#짝수만 고르기(2)
numbers = list(range(1,5))
even_list2 = [ number for number in numbers if number % 2 == 0 ]
```
>[2, 4]

```python
# 자음만 추출하기 (1)
words = 'my name is hong'
vowels = 'aeiou'
result = [] 

for char in words:
    if char not in vowels:
        result.append(char)
print(''.join(result))

# 자음만 추출하기 (2)
words = 'my name is hong'
vowels = 'aeiou'
result = [char for char in words if char not in vowels]
print(''.join(result))

# 자음만 추출하기 (replace)
words = 'my name is hong'
vowels = 'aeiou'
for vowel in vowels:
    words = words.replace(vowel, '')

print(words)

```
>my nm s hng

# 딕셔너리 메소드

- .pop(<key>)
: 원하는 key를 삭제한다.
```python
info = {
    'name' : 'hong',
    'location' : 'seoul',
}

info.pop('name')
print(info)
```
>{'location': 'seoul'}

- .update(<key> = <value>)
: 원하는 key의 value값을 update한다.

```python
info = {
    'name' : 'hong',
}

info.update(name='gil') #name의 value를 바꿈
print(info)
```
>{'name' : 'gil'}

- .get(key, defalut)
: 딕셔너리의 key에 해당하는 value를 가져온다. 해당하는 key가 없을 경우 None 혹은 입력값을 출력한다.

```python
info = {
    'name' : 'hong',
    'location' : 'seoul',
}

print(info.get('name'), end = ' / ') #name의 value를 가져옴
print(info.get('phone', 'defalut')) #딕셔너리에 없는 key값을 가져와서 디폴트값을 출력
```
> hong / defalut


## dict comprehension

```python
# {1: 1, 2: 8, 3: 27} 만들기(1) 
result = {}
numbers = range(1, 4)
for number in numbers:
    result[number] = number ** 3

# {1: 1, 2: 8, 3: 27} 만들기(2)
result2 = { number: number ** 3 for number in range(1, 4)}

```
>{1: 1, 2: 8, 3: 27}


```python
# 미세먼지 50 이상만 남도록 표시
dust = {
    '서울' : 100,
    '대구' : 30,
    '부산' : 50,
    '광주' : 80,
    '제주' : 20,
}
# (1)
result = {}
for k, v in dust.items():
    if v >= 50:
        result[k] = v
# (2)
result2 = { k: v for k, v in dust.items() if v >= 50}
```
> {'서울': 100, '부산': 50, '광주': 80}

# 세트 메소드

- .add(x)
: 요소를 추가한다.
```python
fruits = {'apple', 'banana', 'melon'}

fruits.add('watermelon')
print(fruits)
```
>{'melon', 'watermelon', 'banana', 'apple'}

- .update({set})
: 요소를 업데이트한다.
```python
fruits = {'apple', 'banana', 'melon'}

fruits.update('grape') #문자로 나눠서 저장한다.
fruits.update({'lemon', 'orange'})
print(fruits)
```
>{'g', 'r', 'a', 'p', 'e' 'apple', 'banana', 'melon', 'lemon', 'orange'}

- .remove(x)
: 요소를 제거한다.
```python
fruits = {'apple', 'banana', 'melon'}
fruits.remove('melon')
print(fruits)
```
>{'apple', 'banana'}

- .pop()
: 요소를 제거한다.
```python
fruits = {'apple', 'banana', 'melon'}
fruits.pop()
print(fruits)
```

# map, filter, zip








