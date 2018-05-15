# Today I learned
function 1

- Question
두 점수를 입력받아 합과 곱을 출력하는 프로그램을 구조화하여 작성하시오.<br>
**핵심** : 전역변수와 지역변수, 참조에 의한 
```
#include <stdio.h>

using namespace std;


void input(int &a,int &b)
{
    printf("두 수를 입력하세요. ");
    scanf("%d %d",&a,&b);
}

int multi(int a, int b)
{
    return a*b;
}

int plus(int a, int b)
{
    return a+b;
}

void output(int a,int b)
{
    printf("합 : %d \n", a);
    printf("곱 : %d \n", b);
}

int main()
{
    int a,b;
    int hap, gop;

    input(a,b);
    hap = plus(a,b);
    gop = multi(a,b);
    output(hap,gop);

    return 0;
}

```
