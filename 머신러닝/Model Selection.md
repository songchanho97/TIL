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


