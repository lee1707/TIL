![image](https://user-images.githubusercontent.com/35374344/44097774-8487b914-a019-11e8-9338-7bf19c808954.png)
<br><br>
● 서블릿 : 동적으로 응답결과를 만들어내는 것<br>
● HTTP protocol :클라이언트가 요청하면 서버는 응답한다.<br>
클라이언트가 요청할 때 서버는 요청을 받아내는 객체와 응답을 하기 위한 객체를 자동으로 만들어냄. <br>
요청/응답에 대한 정보를 각 객체안에 추상화시켜서 가지고 있음. 요청/응답으로 뭔가를 만들어줘야 할때는 반드시 이 객체에다가 내용들을 넣어줘야함<br><br>
● setContentType 브라우저가 응답을 받았을 때 이 내용이 이미지인지 동영상인지 등 알려주는 것. <br>
ex:  setContentType(“text/html; charset=utf-8”) 내용은 text이고 html형식이에요. 이 character를 utf-8이라는 방식으로 보낼거예요<br>
● 진짜 보낼내용을 넣어줄 차례. <br>일단 보낼 내용을 넣어줄 통로를 만들자 => response.getWriter() 이 메서드를 수행하면 PrintWriter객체가 return됨.
이 통로 하나를 받아오는 것임. <br>
● 이제 out이라는 통로에다가 출력해주면됨<br><br>

● 서블릿은 서버에 서블릿 객체를 여러개 만들지 않음. 실제 요청된 객체가 메모리가 있어/없어 부분을 체크. 있다면 service메서드만 호출, 없으면 생성자와 init호출. 서블릿 객체가 수정되고 실행되면 destroy 메소드를 호출해 이전 객체를 없앰

