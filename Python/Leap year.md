# 윤년을 구하는 문제 풀기
- 윤년의 규칙
1)  4로 나눠지면 윤년이다. 
2) 4로 나눠지는 숫자에서 100으로 나눠지면 윤년이 아니다. 
3) 그 중에서도 400으로 나눠지면 윤년이다.

- 조건문 문제를 풀 때에는 흐름도를 그려보면서 문제에 접근하는 추천한다. 
```python
if year % 4 == 0:
  if year % 100 == 0:
    if year % 400 == 0:
      print("Leap year")
    else:
      print("Not leap year")
  else:
    print("Leap year")
else:
  print("Not leap year")
```
