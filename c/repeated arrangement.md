# Today I learned
C, repeated arrangement

```
#include <stdio.h>

using namespace std;

int main()
{
    int n;

    int num = -1;

    scanf("%d", &n);

    for(int i=1; i<=n; i++){
        for(int j=1; j<=n; j++){
            if(num>8){
                num = (num + 2) % 10 -2;
                printf("%d ", num+=2);
            } else{
            printf("%d ", num+=2);
            }
        }
        printf("\n");
    }
}
```
연습장과 필기구 가지고 다니<br>
문제풀기전에 연습장에 먼저 규칙을 그려보기<br>
+내가 찾은 규칙을 없는 예제에 대입해 맞는지 보기<br>
표를 그려서 별을 찍고 행과의 연관성을 살펴보기<br>

```
  행  공백 별
   1  4    1
   2  2    3
   3  0    5
   4       7
   5       9
  
  *0+4-2(i-1) i*2-1

 행  출력  공백
1     1    n-출력값
2    12    n-
3   123    
4  1234
5 12345


행 공백       출력
1   n-출력값  1 2 3 
2               4 5
3                 6
4

행  공백 출력
1    xxxxxx 	   #
2    xxxxxx        # #
3    3-출력        # # #


4    3-출력          # #
5    3-출력            #

```

공백은 항상 뒤에 놓기<br>
앞에 놓으면 밀림
