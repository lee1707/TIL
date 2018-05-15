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

- Question2
알수없는 부분
```
#include <stdio.h>

using namespace std;

void input(int &x, int &y)
{
    int tmp;

    scanf("%d %d",&x,&y);

    if(x<y){
        tmp = x;
        x = y;
        y = tmp;
    }
}


void output(int x, int y)
{
    int i,j;

     for(i=y; i<=x; i++){
     /*왜 i++는 동작하지 않는가 */
        printf("== %ddan ==\n",y);
        for(j=1; j<10; j++){
            printf("%d * %d = %2d\n",y,j,y*j);
        }
        y+=1;
        printf("\n");
    }
}
int main()
{
    int a, b;

    input(a,b);
    output(a,b);

    return 0;
}

```
