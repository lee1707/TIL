# Today I learned
지역변수, closure, function

# 지역변수, 전역변수
```
function factory_movie(title){
    return {
        get_title : function (){
            return title;
        },
        set_title : function(_title){
            title = _title
        }
    }
}
ghost = factory_movie('Ghost in the shell');
matrix = factory_movie('Matrix');
 
alert(ghost.get_title());
alert(matrix.get_title());
 
ghost.set_title('공각기동대');
 
alert(ghost.get_title());
alert(matrix.get_title());
```
매개변수는 함수안에서 지역변수로 사용됨

# closure
```

var arr = []
for(var i = 0; i < 5; i++){
	arr[i] = function(id){
		return function(){
			return id;
		}
	}(i);
}
for(var index in arr){
	console.log(arr[index]());
}
```


# function
객체 Function의 메소드 apply의 첫번째 인자는 함수가 실행될 맥락이다. 이렇게 생각하자. sum.apply(o1)은 함수 sum을 객체 o1의 메소드로 만들고 sum을 호출한 후에 sum을 삭제한다. 아래와 비슷하다. (실행결과가 조금 다를 것이다. 그것은 함수 for in문으로 객체 o1의 값을 열거할 때 함수 sum도 포함되기 때문이다.)
```	
o1.sum = sum;
alert(o1.sum());
delete o1.sum();
```
sum의 o1 소속의 메소드가 된다는 것은 이렇게 바꿔 말할 수 있다. 함수 sum에서 this의 값이 전역객체가 아니라 o1이 된다는 의미다. 일반적인 객체지향 언어에서는 하나의 객체에 소속된 함수는 그 객체의 소유물이 된다. <br>하지만 **JavaScript에서 함수는 독립적인 객체로서 존재**하고, apply나 call 메소드를 통해서 다른 객체의 소유물인 것처럼 실행할 수 있다. 
<br>
만약 apply의 첫번째 인자로 null을 전달하면 apply가 실행된 함수 인스턴스는 전역객체(브라우저에서는 window)를 맥락으로 실행되게 된다.

[출처 : 생활코딩](https://www.opentutorials.org/course/743/6550)
