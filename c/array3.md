# Today I learned
array3

# Question
10 이하의 자연수 N을 입력받아 주사위를 N번 던져서 나올 수 있는 모든 경우를 출력하되 중복되는 경우에는 앞에서부터 작은 순으로 1개만 출력하는 프로그램을 작성하시오.

-input example<br>
3<br>
-output emample
```
1 1 1
1 1 2
...
1 1 6
1 2 2
1 2 3
...
5 6 6
6 6 6
```
-I tried.. and failed
```
#include <stdio.h>
#include <stdlib.h>
#define SWAP(x,y) {int z=x, x=y, y=z;}

int arr[101]={0};
int a;

void output(int n)
{
    int i,j;
    for(i=n-1; i>0; i--){
        for(j=0; j<i; j++){
            if(arr[j]>arr[j+1]){
                    SWAP(arr[j],arr[j+1]);
            }
        }
    }
    for(i=0; i<n; i++){
        printf("%d ",a[i]);
    }

    printf("\n");
}

void dice(int n)
{
    int i;
    if(n>a){
        output(n);
        return;
    }
    for(i=1; i<=6; i++){
        arr[n]=i;
        dice(n+1);
    }
}

int main()
{
    scanf("%d",&a);
    dice(1);
    return 0;
}
```
