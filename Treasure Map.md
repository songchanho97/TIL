# 유데미 Python 부트캠프 : 100개의 프로젝트로 Python 개발 완전 정복

```python

row1 = ["⬜️","⬜️","⬜️"]  
row2 = ["⬜️","⬜️","⬜️"]  
row3 = ["⬜️","⬜️","⬜️"]  
map = [row1, row2, row3]   
print(f"{row1}\n{row2}\n{row3}")    
position = input("Where do you want to put the treasure? ")  

#Write your code below this row 👇  
 
col = int(position[0])  
row = int(position[1])  
selected_row = map[row-1]  
selected_row[col-1] = 'X'  


#Write your code above this row 👆


print(f"{row1}\n{row2}\n{row3}")
```
