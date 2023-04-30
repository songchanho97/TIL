1. 비트 연산자의 이해와 문자 자료형
- 입력받은 정수 값의 부호를 바꿔서 출력하는 프로그램을 작성해보자

```c
#include <stdio.h>

int main(void)
{	
	int num;
	
	printf("정수를 입력해주세요: ");
	scanf("%d", &num);
	num = ~num;   // 1의 보수를 만드는 것
	num = num + 1;
	printf("부호바꾼 결과 : %d \n", num);

	return 0;	
 } 
```

----
2. int num=15를 이용하여 왼쪽으로 1,2,3칸 이동하는 결과를 알아보자 .
```c
#include <stdio.h>

int main(void)
{	
	int num = 15;
	
	printf("비트연산전: %d\n", num);
	printf("1칸 이동한 결과: %d\n", num<<1);
	printf("2칸 이동한 결과: %d\n", num<<2);
	printf("3칸 이동한 결과: %d\n", num<<3);
	
	return 0;	
 } 
```

---
3. 사용자로부터 두 개의 실수를 입력 받아서 double형 변수에 저장하자 그리고 두 수의 사칙연산 결과를 출력하자. 
```c
#include <stdio.h>

int main(void)
{	
	double num1, num2;
	
	printf("두 개의 실수 입력 : ");
	scanf("%lf %lf",&num1, &num2) ;  // 실수를 입력받을 때는 lf  
	
	printf("두 수의 덧셈 : %f \n", num1+num2);  // 출력할 때는 f  
	printf("두 수의 뺄셈 : %f \n", num1-num2);
	printf("두 수의 곱셈 : %f \n", num1*num2);
	printf("두 수의 나눗셈 : %f \n", num1/num2);
	
	return 0;
 } 
```
