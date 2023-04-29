C언어의 연산자

- 복합 대입 연산자
```c
#include <stdio.h>

int main(void) {
	int num1 = 2, num2 = 4, num3 = 6;
	num1 += 3;   //num1 = num1  + 3;
	num2 *= 4;  //num2 = num2 * 4;
	num3 %= 5; //num3 = num3 % 5;
	printf("Result : %d, %d, %d\n", num1, num2, num3);
	
	return 0;
};
```
실행결과 
Result : 5, 16, 1  

---
num1 = -num2; //부호 연산자의 사용   
num1 -= num2; //복합 대입 연산자의 사용   
-> 두 연산자를 혼동하지 않도록 주의한다.   

```c
#include <stdio.h>

int main(void) {
	int num1 ,num2;
	int num3 = 30, num4 = 40;
	
	printf("num1 : %d, num2 : %d \n", num1,num2) ;
	num1 = 10;
	num2 = 20;
	printf("num1 : %d, num2 : %d \n", num1, num2);
	printf("num3 : %d ,num4 : %d \n" ,num3, num4);
};
```
