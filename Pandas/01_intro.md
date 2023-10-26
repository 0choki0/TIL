## What is Pandas

- [Pandas](https://pandas.pydata.org/docs/index.html)란 데이터를 효과적으로 처리하고 보여줄 수 있도록 도와주는 라이브러리이다. index에 따라 데이터를 나열하므로 Dictionary 자료형에 가깝다고 보면되다. 

- 판다스는 별칭으로 pd를 사용한다.
> import pandas as pd

### Series
: 시리즈는 인덱스와 값으로 구성된다.

- 생성
1) **numpy array**로 생성한 경우  
구문은 다음과 같다  
: *pd.Series(<지정할 array>)*
```python
arr = np.arange(10, 15)
# array([10, 11, 12, 13, 14])로 arr 값 할당
s = pd.Series(arr)
s
```
> 0 10  
1 11  
2 12  
3 13  
4 14  
dtype : int32

데이터 타입을 따로 지정할 수 있다.
```python
s = pd.Series(arr, dtype='int64')
```

2) **list**로 생성한 경우  
구문은 다음과 같다.  
: *pd.Series([리스트])*
```python
s = pd.Series(['부장', '차장', '대리', '사원', '인턴'])
s
```
>0 부장  
1 차장  
2 대리  
3 사원  
4 인턴  
dtype: object

Series를 *다양한 타입*(str과 int가 같이 쓰이는 경우 등)의 데이터로 생성시, dtype은 *object*로 생성된다. 