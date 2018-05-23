# Today I learned
array2-3

# Question
두 개의 실수를 입력받아 각각의 제곱근을 구하고 두 제곱근 사이에 존재하는 정수의 개수를 출력하는 프로그램을 작성하시오. 
단, 입력받는 두 실수는 양수이며 두 제곱근 사이라는 말은 두 제곱근을 포함한다.

-input example<br>
12.0 34.789<br>
-output example<br>
2<br><br>

-I tried.. and failed
```
int main()
{
    double a, b;
    int c,d,i;
    scanf("%lf %lf",&a,&b);
    c = (int)sqrt(a);
    printf("%d\n",c);
    d = (int)sqrt(b);
    printf("%d\n",d);

    for(i=c; i<=d; i++){
        printf("%d ",c++);
    }

    return 0;
}

```
