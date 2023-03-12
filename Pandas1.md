```python
# pandas 라이브러리 
import pandas as pd
```

### 1차원 Series 다루기 


```python
# Series 생성 
population = pd.Series([33323,2323,42534,3424])
population
```




    0    33323
    1     2323
    2    42534
    3     3424
    dtype: int64




```python
# index값 지정해주기
population = pd.Series([33323,2323,42534,3424], 
                      index = ['서울', '부산', '광주', '목포'])
population
```




    서울    33323
    부산     2323
    광주    42534
    목포     3424
    dtype: int64




```python
# 시리즈의 값 확인하기 
population.values
```




    array([33323,  2323, 42534,  3424], dtype=int64)




```python
# 시리즈의 인덱스 확인하기 
population.index
```




    Index(['서울', '부산', '광주', '목포'], dtype='object')




```python
# 시리즈의 타입보기 
population.dtype
```




    dtype('int64')




```python
# 시리즈 이름 지정
population.name = '인구'
population.index.name = '도시'
population
```




    도시
    서울    33323
    부산     2323
    광주    42534
    목포     3424
    Name: 인구, dtype: int64




```python
# Series 연산 
population / 10000
```


```python
population + population
## 이러한 것들이 모두 가능한 이유는 pandas는 넘파이 기반으로 만들어져있음.
```

### 인덱싱, 슬라이싱


```python
population[0]
```




    33323




```python
population['광주']
```




    42534




```python
# 여러분들 이전에 배웠던 dictionary 유사하다고 할 수 있습니다. 
popu_dic = {'부산':3332, '광주':3323}
```


```python
popu_dic['부산']
```




    3332




```python
# 광주 데이터 가져오기 
```


```python
population[1]
```




    2323




```python
population['광주']
```




    42534




```python
# 인덱싱을 이용해서 여러개의 값을 가져오기 
# 서울, 광주, 부산 순으로 가져오기
# 인덱싱을 하나의 값만 가져오기 때문에 리스트로 묶어줘야 한다. 
population[[0,3,1]]
```




    도시
    서울    33323
    목포     3424
    부산     2323
    Name: 인구, dtype: int64




```python
population[['서울','광주','부산']]
```




    도시
    서울    2324
    광주    3324
    부산    3332
    Name: 인구, dtype: int64




```python
# Series Boolean indexing
# Boolean Data 만들기
population[population > 10000]
```




    도시
    서울    33323
    광주    42534
    Name: 인구, dtype: int64




```python
# Q1. 인구수가 300만 이상인 도시는?
population[population >= 3899]
```




    도시
    서울    33323
    광주    42534
    Name: 인구, dtype: int64




```python
# Q2. 인구수가 250만이상 500만 이하의 도시는?
population[(population >= 250) & (population < 50000)]
```




    도시
    서울    33323
    부산     2323
    광주    42534
    목포     3424
    Name: 인구, dtype: int64




```python
# Series 슬라이싱 
population[1 : 3]
```




    도시
    부산     2323
    광주    42534
    Name: 인구, dtype: int64




```python
# 끝 값을 포함한다.
population['부산':'목포']
```




    도시
    부산     2323
    광주    42534
    목포     3424
    Name: 인구, dtype: int64



### 과제


```python
import pandas as pd
temp = pd.Series([27,14,10,17,19,18,16], 
                      index = ['3/11', '3/12', '3/13', '3/14', '3/15', '3/16', '3/17'])
```


```python
avg_temp = round((temp[0] + temp[1] + temp[2]+ temp[3]+ temp[4]+ temp[5]+ temp[6])/7,1)
max_temp = temp.max()
min_temp = temp.min()

```




    3/11    27
    dtype: int64




```python
print(f"최고 기온의 평균온도는 {avg_temp}이고 최고 기온인 날은 {temp[temp==max_temp].index[0]} 최저 기온인 날은 {temp[temp==min_temp].index[0]}이다.")
```

    최고 기온의 평균온도는 17.3이고 최고 기온인 날은 3/11 최저 기온인 날은 3/13이다.
    


```python
temp[temp==max_temp].index[0]
```




    '3/11'


