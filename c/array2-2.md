# Today I learned
array2-2

# Question
- 문제<br>
3행 5열의 2차원 문자배열을 선언하고 차례로 대문자를 입력 받은 후 소문자로 바꾸어서 공백으로 구분하여 출력하는 프로그램을 작성하시오.
<br>

- 나의 답안<br>

```
#include <stdio.h>

using namespace std;

int main()
{
    int i, j;
    char c[3][5]={0};

    for(i=0; i<3; i++){
        for(j=0; j<5; j++){
            scanf(" %c",c[i][j]);
        }
    }

    for(i=0; i<3; i++){
        for(j=0; j<5; j++){
            printf(" %c",'c[i][j]'-32);
        }
    }
}




```
->오류.. 이유 알수없음. 고치는중.
