## 데이터 연결

- .concat()
단순하게 지정한 데이터프레임을 이어서 연결한다. 행 방향(axis=0) 연결이 기본이다. 

```python 
# df1과 df2를 행 방향으로 연결
pd.concat([df1, df2])

# 데이터의 갯수가 맞지 않는 것(index 값이 2개이므로)을 무시(index 초기화라고 생각하면 된다)하고 연결
pd.concat([df1, df2], ignore_index=True)

# df1과 df2를 열 방향으로 연결
pd.concat([df1, df2], axis=1)
```

## 데이터 병합

- .merge()
서로 다른 구성의 DataFrame이지만, **공통된 key(컬럼)값을 가지고 있다면** 병합할 수 있다.

merge의 옵션인 **how={'inner', 'left', 'right', 'outer'}**을 사용하여 기준을 달리할 수 있다.

```python
# 공통된 컬럼을 가진 df1과 df2의 병합
pd.merge(df1, df2)
```

병합하는 컬럼의 이름이 다른 경우 `left_on`과 `right_on` 옵션을 이용하여 drop되지 않을 컬럼의 명을 지정할 수 있다.