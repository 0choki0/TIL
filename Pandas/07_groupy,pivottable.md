### apply
- .apply()
함수를 적용하고자 할 때 사용한다.
```python
# 예를 위한 임시 함수
def fun(x):
    return 'x'

# 데이터 프레(df)의 특정 컬럼(col)에 함수(fun)를 적용하고자 할 때 apply를 사용하는 코드이다.
df['col'].apply(fun)

# 컬럼에도 함수를 적용할 수 있다.
df.apply(fun, axis=1)
```

### groupby
데이터를 특정 기준으로 그룹핑할 때 사용한다. 
```python
# 특정 컬럼을 기준으로 그룹핑하여 평균을 나타내는 코드 (컬럼 내의 데이터로 구분되어 다른 컬럼 들의 값을 보여준다.)
df.groupby('col').mean(numeric_only=True)

# 2개 이상의 컬럼으로 그룹핑 할 수 있다.
df.groupby(['col1', 'col2'])
```

- .agg()
여러 가지의 통계값을 적용할 때 사용한다.
```python
# df의 col1과 col2를 기준으로 보고싶은 데이터 col3와 col4의 평균(mean)과 합(sum)을 구하는 코드
df.groupby(['col1', 'col2'])[['col3', 'col4']].agg(['mean', 'sum'])
```

### pivot_table

- pivot_table()
필요한 자료만 뽑아서 다시 DataFrame을 만드는 기능.
```python
# index에 그룹을 표기 (행에 컬럼 데이터)
df.pivot_table(index='col1', values='col2')

# colums에 그룹을 표기 (열에 컬럼 데이터)
df.pivot_table(columns='col1', values='col2')

# 여러개의 컬럼 표기
df.pivot_table(index=['col1', 'col2'], values='col3')




```




