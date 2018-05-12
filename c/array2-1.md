# Today I learned
array 2-1


- 내 코드
```
#include <stdio.h>

using namespace std;

int main()
{
    int i, j;
    int score[4][4]={0};

    for(i=0; i<3; i++){
        printf("%d번째 학생의 점수 ",i+1);
        for(j=0; j<3; j++){
            scanf("%d",&score[i][j]);
        }
    }

    for(i=0; i<4; i++){
        for(j=0; j<3; j++){
            score[i][3]+=score[i][j];
            score[3][i]+=score[j][i];
        }
    }
    score[3][3]=score[3][3]/2;

    printf("    국어 영어 수학 총점\n");
    for(i=0; i<4; i++){
        if(i==3){
            printf("합계 ");
        }else{
            printf("%d번  ",i+1);
        }
        for(j=0; j<4; j++){
            printf("%3d  ",score[i][j]);
        }
     printf("\n");
    }
}

```
- 답
```
#include <stdio.h>

using namespace std;

int main()
{
    int i, j;
    int score[4][4]={0};

    for(i=0; i<3; i++){
        printf("%d번째 학생의 점수 ",i+1);
        for(j=0; j<3; j++){
            scanf("%d",&score[i][j]);
            score[i][3]+=score[i][j];
            score[3][j]+=score[i][j];
            score[3][3]+=score[i][j];
        }
    }

    printf("    국어 영어 수학 총점\n");
    for(i=0; i<4; i++){
        if(i==3){
            printf("합계 ");
        }else{
            printf("%d번  ",i+1);
        }
        for(j=0; j<4; j++){
            printf("%3d  ",score[i][j]);
        }
     printf("\n");
    }
}

```
