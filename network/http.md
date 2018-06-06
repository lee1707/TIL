# Today I learned
HTTP

- 알아둘 것

1. http상태코드의 종류와 의미 status code
2. 주요 http요청/응답 헤더
3. http 메서드의 종류와 특징
4. set-cookie header

```
1. http 요청 구성요소
-(head)시작줄 : 실행해야할 요청
	1)http method(get/post or head)
	2)request target(url or protocol/port..)
	3)http version
-(head)헤더: 요청을 특정하거나 메세지내 포함되는 본문을 부연설명
-빈줄: 요청에 대한 모든 메타정보가 전송되었음을 가리킴

-(body)선택적본문: 요청과 연관된 데이터/응답과 연관된 문서를 포함하는 선택적 본문


2. 응답 상태코드 200, 400, 404, 500 의 의미
200:성공 -서버가 요청을 제대로 처리함
400:잘못된 요청, 서버가 요청의 구문을 인식하지 못함
404:찾을 수 없음, 서버가 요청한 페이지를 찾을수 없다
500:내부서버 오류.

2xx: 성공
4xx: 요청 정보가 잘못된 케이스(클라이언트의 잘못)
5xx: 서버쪽의 오류

3. 브라우저 쿠키를 설정하는 헤더는?
set-cookie header
```

[참고 : HTTP](https://developer.mozilla.org/ko/docs/Web/HTTP/Messages#HTTP_%EC%9A%94%EC%B2%AD)
[참고 : setcookie](https://developer.mozilla.org/ko/docs/Web/HTTP/Cookies)
