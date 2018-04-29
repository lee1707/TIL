# Today I learned
conditional statement <br><br>

이제 한글 제대로 써짐. 원인 알수없음 여튼 만세! <br><br>

- null : 값이 없다(의도적)<br>
  undefined : 값이 정의 x(의도x)<br><br>

- `==` : 내용이 같다<br>
 `===` : 내용과 형식이 완전히 같다(엄격하게) ** 이걸 더 추천함**<br><br>

- NaN : 성립x, 숫자x, 계산할수 없음을 의미. ex) 0/0<br><br>

# what is false
- 조건문에 사용될 수 있는 데이터 형이 꼭 불린만 되는 것은 아니다. 관습적인 이유로 0는 false 0이 아닌 값은 true로 간주된다. 아래의 예제는 2를 출력한다.
<br><br>
- 기타 false로 간주되는 데이터 형<br>
다음은 false와 0 외에 false로 간주되는 데이터형의 리스트다. <br>
if문의 조건으로 !(부정) 연산자를 사용했기 때문에 각 조건문의 첫번째 블록이 실행되는 것은 주어진 값이 false이기 때문이다.

```
if(!''){
    alert('빈 문자열')
}
if(!undefined){
    alert('undefined');
}
var a;
if(!a){
    alert('값이 할당되지 않은 변수'); 
}
if(!null){
    alert('null');
}
if(!NaN){
    alert('NaN');
}
```

[출처 : 생활코딩](https://www.opentutorials.org/course/743/4724)
