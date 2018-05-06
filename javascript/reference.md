# Today I learned
reference

# javascript 정리
자바스크립트는 예술가같은 언어. 자유로움<br>
객체내의 속성(프로퍼티)이 변수, 값<br>
객체내의 속성이 함수면 : 메소드<br> 
func라는 프로퍼티는 : 함수임<br>

```
var o = {
    func : function(){
        if(o === this){
            document.write("o === this");
        }
    }
}
o.func();   
```
```
var person = {
	'name' : 'egoing',
	'introduce' : function(){
		return 'My name is '+this.name;
	}
}
document.write(person.introduce());
```

- 이해x, 질문필요<br>
생성자는 빈 객체를 만든다. 그리고 이 객체내에서 this는 만들어진 객체를 가르킨다. 이것은 매우 중요한 사실이다. 생성자가 실행되기 전까지는 객체는 변수에도 할당될 수 없기 때문에 this가 아니면 객체에 대한 어떠한 작업을 할 수 없기 때문이다. 
```
function Func(){
    document.write(o);
}
var o = new Func();
```
결과는 아래와 같다.
```
1
undefined
```

# reference
다음은 참조 데이터 타입을 인자로 넘겼을 때 동작하는 장면이다. 
```
var a = {'id':1};
function func(b){
    b = {'id':2};
}
func(a);
console.log(a.id);  // 1
```
결과는 아래와 같다.
```
1	
1
```
함수 func의 파라미터 b로 전달된 값은 객체 a이다. (b = a) b를 새로운 객체로 대체하는 것은 (b = {'id':2}) b가 가르키는 객체를 변경하는 것이기 때문에 객체 a에 영향을 주지 않는다.
<br>
하지만 아래는 다르다.
```
var a = {'id':1};
function func(b){
    b.id = 2;
}
func(a);
console.log(a.id);  // 2
```
파라미터 b는 객체 a의 레퍼런스다. 이 값의 속성을 바꾸면 그 속성이 소속된 객체를 대상으로 수정작업을 한 것이 되기 때문에 b의 변경은 a에도 영향을 미치게 된다. 

[출처: 생활코딩](https://www.opentutorials.org/course/743/6507)
