# MarkDown
```
# 제목1 (에이치1)
## 제목2 (에이지2 태그랑 동일)
### 제목3
#### 제목4
[링크](https://www.daum.net)
- List Item
- List Item
  - List Item 
  - List Item4
  
1. Ordered Item.
2. Ordered Item2.

This is `code`.  
```
# 제목1 (에이치1)
## 제목2 (에이지2 태그랑 동일)
### 제목3
#### 제목4
[링크](https://www.daum.net)
- List Item
- List Item
  - List Item 
  - List Item4
  
1. Ordered Item.
2. Ordered Item2.

This is `code`.  

# Error
뇌를 자극하는 서블릿 책에서 태그라이브러리 예제를 따라하던 중...
404 낫 파운드가 뜸.
톰캣 실행 로그를 보니 에러가 표시되고 있었음
```
IllegalArgumentException: taglib ...
```

# 해결 방법
메시지로 구글링 해보니 톰캣 7부터 태그라이브러리 설정 시 웹.엑스엠엘 의 형식이 바뀜  
- 기존 방식
```
<web-app xmlns="http://java.sun.com/xml/ns/javaee" version="3.1">
		<taglib>
			<taglib-uri>/taglibs/tools.tld</taglib-uri>
			<taglib-location>/WEB-INF/tlds/tools.tld</taglib-location>
		</taglib>
</web-app>
```

- 바뀐 방식
```
<web-app xmlns="http://java.sun.com/xml/ns/javaee" version="3.1">
	<jsp-config>
		<taglib>
			<taglib-uri>/taglibs/tools.tld</taglib-uri>
			<taglib-location>/WEB-INF/tlds/tools.tld</taglib-location>
		</taglib>
	</jsp-config>
</web-app>
```
