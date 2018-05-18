# Today I learned 
function 1-2

# Question
- 3명 학생의 3과목 점수를 입력받아 각 과목별  학생별 총점을 출력하는 구조화된 프로그램을 작성하시오.
- error code
```
#include <stdio.h>

using namespace std;


int input()
{
    int i,j;
    int x=0;
    int score[4][4]={0};

    for(i=0; i<3; i++){
        for(j=0; j<3; j++){
            scanf("%d",&x);
            score[i][j]=x;
        }
    }
    return score[4][4];
}

int scoreall(int score[4][4])
{
    int i, j;
    int result[4][4]={0};

    for(i=0; i<4; i++){
        for(j=0; j<4; j++){
            result[0][3]+=score[i][j];
            result[3][0]+=score[i][j];
            result[3][3]+=score[i][j];
        }
        printf("\n");
    }

    return result[4][4];

}

void output(int score[4][4])
{
    int i, j;

    for(i=0; i<4; i++){
        for(j=0; j<4; j++){
            printf("%d ",score[i][j]);
        }
        printf("\n");
    }
}

main()
{
    int score[4][4]={0};


    score[4][4] = input();
    score[4][4] = scoreall(score[4][4]);
    output(score[4][4]);
}

```
