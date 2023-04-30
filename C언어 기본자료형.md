1. 비트 연산자의 이해와 문자 자료형
- 입력받은 정수 값의 부호를 바꿔서 출력하는 프로그램을 작성해보자

```c
#include <stdio.h>

int main(void)
{	
	int num;
	
	printf("정수를 입력해주세요: ");
	scanf("%d", &num);
	num = ~num;   // ~는 비트를 반전시켜주는 연산자
	num = num + 1;
	printf("부호바꾼 결과 : %d \n", num);

	return 0;	
 } 
```
