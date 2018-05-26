# Today I learned
make background source to file, and do include in jsp page.
```
html->jsp
1.make html page to jsp
2.use jsp include
<%@include file="theJspToInclude.jsp" %>

-should include html in jsp.
1.인코딩깨짐
2. 아예 jsp page도 안됨

1. 일단 원래 jsp인 페이지만 고치기
2. boardinput.jsp 이거 getcalender 다시 질문
3.boradItemView는원래 서블릿으로 봐야하는게 맞음
4.title새로 설정해야하는것 확인하기->아리보코딩클럽으로함
 
1. header와 footer재작업 완료, 그러나 알고보니 서버에 연결되지 않음
2. 서버에 연결시키려다 실수로 팝업창에서 remove를 보지 않고 눌러서 다 리셋됨
3. 새로 만들고(acc-attendance-website) 서버에 연결하자 오류난거 고침
(path문제)
http://blog.naver.com/PostView.nhn?blogId=lge920904&logNo=220252157488&parentCategoryNo=&categoryNo=1&viewDate=&isShowPopularPosts=false&from=section
4. header와 footer다시 다 재작업
1)인코딩문제로 html을 jsp로 고치면 한글깨짐
->원래 프로젝트에 있는 해당 페이지 전체 복붙->header와 footer작업하면됨
(글자 컬러로 안되도 정상적으로 작동함)

#class 첫글자를 대문자로 바꾸면 오류
https://stackoverflow.com/questions/17973970/how-to-solve-java-lang-noclassdeffounderror
이해못하겠음

#BoardInput 이거 db랑 연동이라
다시해야함
BoardItemView,BoardItemViewOrigin
#BoardInputResult =작성되었습니다
이부분은 팝업 띄우는 걸로 변경하기
(#)BoardListView는 header를 고치면 안됨 .. 왜? ㅠㅠ에라이
-밑에 servlet불러오는거 하나 더있어서. 이거 덧붙여주면 잘 됨
-Header.jsp에 있는거 숮ㅇ해야함
choose안됨
-Main에 로그인하나뜨는거..
The prefix  specified in this tag directive has been previously used by an action in file
--><%@taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core"%>
이걸 다른태그 아래에 붙여줬을때 생김
그럼 우선순위가 더 높아지나봄
아래에 있을때..
-board-list도 마찬가지임.

#playground에서는 학습활동 list가 안눌러짐

아 소스트리 다 날라감 
- 


```
