# Today I learned
string

# Question
문자열(100자 이하)을 입력받은 후 정수를 입력받아 해당위치의 문자를 제거하고 출력하는 작업을 반복하다가 문자 1개가 남으면 종료하는 프로그램을 작성하시오.<br>
첫 번째 문자의 위치는 1이며 만약 입력받은 번호가 문자열의 길이 이상이면 마지막 문자를 제거한다.<br><Br>

-**input**&output<br>
**word**<br>
**3**<br>
wod<br>
**1**<br>
od<br>
**10**<br>
o<br><br>

- I tried.. and failed
```
#include <stdio.h>
#include <string.h>

int main()
{
    int i,len,n;
    char str[101]={0};

    scanf("%s",str);

    while(1){
       scanf("%d",&n);
       len=strlen(str);
       if(len==1) break;
       str[n+1]='\0';

       for(i=0; i<len; i++){
           if(str[i]=='\0');
           else{str[i+1]=str[i];}
           printf("%c",str[i+1]);
       }
       printf("\n");
    }
    return 0;
}


```
