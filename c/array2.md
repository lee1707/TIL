# Today I learned
array2 

# 문제
100 미만의 양의 정수들이 주어진다. 입력받다가 0 이 입력되면 마지막에 입력된 0 을 제외하고 그 때까지 입력된 정수의 십의 자리 숫자가 각각 몇 개인지 작은 수부터 출력하는 프로그램을 작성하시오. (0개인 숫자는 출력하지 않는다.)

<br>

- 답 
```
#include <stdio.h>

using namespace std;

int main()
{
    int i, num;
    int count[10]={0};

    while(1){
        scanf("%d", &num);
        if(num==0) break;
        count[num/10]++;
    }

    for(i=0; i<10; i++){
        printf("%d : %d\n", i, count[i]);
    }
}
```
