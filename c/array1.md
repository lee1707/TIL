# Today I learned
array1

c로 입력받을 땐 공백을 앞으로 꼭 놓기
배열 크기를 넘어가는 입력이 발생하면 런타임에러가 발생

```
int main()
{
    int i, a[100];
    int count = 0;

    for(i=0; i<100; i++){
        scanf("%d", &a[i]);
        if(a[i]==0) break;
        count++;
    }
    for(i=count-1; i>=0; i--){
        printf("%d ", a[i]);
    }
    printf("\n");
    return 0;
}
```

왜 count -1 부터 
=> 0부터 입력받기 때문

```
#include <stdio.h>

using namespace std;

int main()
{
    double classScore[] = {0, 85.6, 79.5, 83.1, 80.0, 78.2, 75.0};
    int class1, class2;

    scanf("%d %d", &class1, &class2);
    double plus = classScore[class1] + classScore[class2];
    printf("%.1lf", plus);

    return 0;
}
```
소수점 몇째자리까지 표시 %.nlf


