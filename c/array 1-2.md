# Today I learned
array 1-2

```
int main()
{
    int a[10];
    int sum = 0;
    int sum2 = 0;
    double avg;

    for(int i = 0; i < 10; i++){
        scanf("%d", &a[i]);
    }
    for(int i = 0; i < 10; i++){
        if(i % 2 == 1){
            sum += a[i];
            printf("sum :%d \n", sum);
        } else {
            sum2 += a[i];
            printf("sum2 :%d \n", sum2);
        }
    }

    avg = (double) sum2 / 5;

    printf("sum : %d\n", sum);
    printf("avg : %.1lf\n", avg);
}
```

- 0,1,2,3으로 시작하기 때문에 0,2가 1,3과 마찬가지가 되어서 홀수와 짝수가 바뀌게 됨<br>

- 입력받을때는 .1lf처럼 소수점 찍지 않음. 무조건 다 받고 처리해야해서 그냥 lf라고 씀 

- sum은 int여야함, double이면 알수없는 이유로 0이나옴
