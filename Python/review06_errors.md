# Error

## syntax error
: 문법에 오류 있을 경우 나오는 error이다.

![문법오류](../assets/syntax_error.JPG)

### exception
: 기타 다른 error 중 몇 가지를 소개한다.

- ZeroDivisionError
: 0으로 나눌 수 없을 때 (수학적 오류)

![ZeroDivisionError](../assets/ZeroDivisionError.JPG)

- NameError
: 변수 자체가 없는 등 오류

![NameError](../assets/NameError.JPG)

- TypeError
: 타입의 오류

![TypeError](../assets/TypeError.JPG)

- ValueError
: 값의 오류
![ValueError](../assets/ValueError.JPG)

- IndexError
: 문자 오류
![IndexError](../assets/IndexError.JPG)

- keyError
: 딕셔너리의 key 오류
![keyError](../assets/keyError.JPG)

- ModuleNotFoundError
: 모듈 오류
![ModuleNotFoundError](../assets/ModuleNotFoundError.JPG)


## 예외처리
: 에러가 나는 경우 예외 처리하도록 하는 코드이다.

```python
try:
    code
except 예외 :
    code
```
- 기본 사용 형식
![try_except1](../assets/try_except1.JPG)

- 한번에 적기
![try_except1](../assets/try_except3.JPG)

- 모든 에러 처리
![try_except1](../assets/try_except2.JPG)

- 에러 내용을 str로 출력하기
![try_except_as](../assets/error_fix_str.JPG)

- else
: except error가 발생하지 않을 경우 실행되는 코드
![try_except_else](../assets/error_else.JPG)

- finally
: 예외 상황과 무관하게 무조건 최종적으로 실행되는 코드
![try_except_finally](../assets/error_filnally.JPG)

- raise
: 예외를 강제로 발생시킴
![error_raise](../assets/error_raise.JPG)

```python
# 예외처리 연습

# 예외처리 연습

def my_div(num1, num2):
    try:
        result = num1 / num2
    except ZeroDivisionError:
        print('0이 아닌 값으로 나눠주세요.')
        # 파이썬이 return None을 자동으로 넣어줘서 None을 결과로 냄
    except TypeError:
        print('str형식이 아닌 float 형식으로 적어주세요.')
        # 파이썬이 return None을 자동으로 넣어줘서 None을 결과로 냄
    else:
        return result


print(my_div(5, 0),)
print(my_div('5', '0'))
print(my_div(5, 2))
```
> 0이 아닌 값으로 나눠주세요. / None / str형식이 아닌 float 형식으로 적어주세요. / None / 2.5 