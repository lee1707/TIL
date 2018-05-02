# Today I learned
regex

# pages
[https://regexr.com](https://regexr.com)<br>
[https://regexper.com](https://regexper.com)

# 유효범위
```
var vscope = 'global';
function fscope(){
    vscope = 'local';
    alert('함수안'+vscope);
}
fscope();
alert('함수밖'+vscope);
```
- 결과는 둘다 local이다.
- 함수밖에서도 vscope의 값이 local인 이유는 무엇일까? 그것은 함수 fscope의 지역변수를 선언할 때 var를 사용하지 않았기 때문이다. 
**var를 사용하지 않은 지역변수는 전역변수가 된다.** 따라서 3행은 전역변수의 값을 local로 변경하게 된 것이다. <br>
전역변수는 사용하지 않는 것이 좋다. 여러가지 이유로 그 값이 변경될 수 있기 때문이다.

# 지역변수의 사용
```
function a (){
    var i = 0;
}
for(var i = 0; i < 5; i++){
    a();
    document.write(i);
}
```
실행결과 :01234
# 전역변수의 사용
**본 예제는 무한반복을 발생시킨다.**
```
function a (){
    i = 0;
}
for(i = 0; i < 5; i++){
    a();
    document.write(i);
}
```
출처 : [생활코딩](https://www.opentutorials.org/course/743/6495)
