# 학습/ 테스트 데이터 세트 분리- train_test_split()  

- 학습 데이터 세트로만 학습하고 예측하면 어떤 문제가 발생하는지 확인해보겠습니다. 
```python
from sklearn.datasets import load_iris
from sklearn.tree import DecisionTreeClassifier
from sklearn.metrics import accuracy_score

iris = load_iris()
dt_clf = DecisionTreeClassifier()
train_data = iris.data
train_label = iris.target
dt_clf.fit(train_data, train_label)

# 학습 데이터 세트로 예측 수행
pred = dt_clf.predict(train_data)
print('예측 정확도:', accuracy_score(train_label, pred))
```

![image](https://github.com/Solomon9702/TIL/assets/84561497/e43a1629-528e-45ba-b817-2947c34dd59d)

예측 정확도가 100%가 나오게 됩니다.  이미 학습한 학습 데이터 세트를 기반으로 예측했기 때문에 예측정확도가 100%가 나오게 되는데 이는 올바른 모델이라고 할 수 없습니다. 

따라서 예측을 수행하는 데이터 세트는 학습을 수행한 학습용 데이터 세트가 아닌 전용의 데이터 세트여야 합니다. 사이킷런의 train_test_split()를 통해 원본 데이터 세트에서 학습 및 테스트 데이터 세트를 쉽게 분리할 수 있습니다.   
먼저 sklearn.model_selection 모듈에서 train_test_split을 로드합니다. train_test_split()는 첫 번째 파라미터로 피처 데이터 세트, 두 번째 파라미터로 레이블 데이터 세트를 입력받습니다. 
- test_size : 전체 데이터에서 테스트 데이터 세트 크기를 얼마로 샘플링할 것인가를 결정합니다. 
- train_size : 학습용 데이터 세트 크기를 얼마로 샘플링할 것인가를 결정합니다. 
- shuffle : 데이터를 분리하기 전에 미리 섞을지를 결정합니다. 
