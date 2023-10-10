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








