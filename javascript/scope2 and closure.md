# Today I learned
scope2, closure

# scope2 
```
var vscope = 'global';
function fscope(){
	vscope = 'local';
}
fscope();
alert(vscope);
```
=> local(var 안붙으면 전역변수)

```
var vscope = 'global';
function fscope(){
	var vscope = 'local';
	vscope = 'local';**
}
fscope();
alert(vscope);
```
=>**의 전역변수 vscope이 앞에 지역변수가 있으면 그걸 바꿔주게됨, 결과는 global<br><br>

- var을 함수 바깥에서 쓰면(=어떤 함수에 소속되어 있지 않으면) 전역변수가 되고, 함수 안에서 쓰면 지역변수가 됨<br>
javascript에서는 for문, if문에 안에서 선언된 변수는 지역변수 아님 

- 자바스크립트는 함수가 선언된 시점에서의 유효범위를 갖는다. 이러한 유효범위의 방식을 정적 유효범위(static scoping), 혹은 렉시컬(lexical scoping)이라고 한다. 
누구에게서 사용될지 알수 없기 떄문에.


- 자바스크립트는 함수도 객체이다(=값이다)<br>
function a(){}는 var a =function(){}과 같다. a에 담겨있는 함수임<br><br>

객체 안에 정의되어잇는 함수는 메소드임 
```
a = {
    b:function(){
    }
};
```
b의 function은 메소드


# closure
```
function outter(){
    var title = 'coding everybody';  
    return function(){        
        alert(title);
    }
}
inner = outter();
inner();
```
외부함수의 실행이 끝나서 **외부함수가 소멸된 이후에도** 내부함수가 외부함수의 변수에 접근 할 수 있다. <br>
**클로저**란 내부함수가 외부함수의 지역변수에 접근 할 수 있고, 외부함수는 외부함수의 지역변수를 사용하는 내부함수가 소멸될 때까지 소멸되지 않는 특성을 의미한다.
