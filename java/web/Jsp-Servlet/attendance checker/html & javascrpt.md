# Today I learned
html, Javascript

WebTemplate.jsp
-------------
```
<%@page contentType="text/html; charset=UTF-8"%>
<%@taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core"%>
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>아리보 코딩 클럽(ACC)</title>
</head>
<body>
	<h1 style="text-align:center";>아리보 코딩 클럽(Arivo Coding Club)</h1>
	<table>
		<tr>
			<td width=300 valign=top text-align=center padding=100>
				<c:choose>
					<c:when test="${sessionScope.LOGIN_ID == null}">
						<jsp:include page="LoginWindow.jsp"/>
					</c:when>
					<c:otherwise>
						<jsp:include page="LogoutWindow.jsp"/>
					</c:otherwise>
				</c:choose>
				<a href="WebTemplate.jsp?BODY_PATH=Intro.jsp">코딩 클럽 소개</a><br>
				<a href="WebTemplate.jsp?BODY_PATH=attendance.jsp">출석부</a><br>
				<a href="bbs-list">학습 게시판</a><br>
				<a href="books-info">아리보 도서 구입</a><br>
				<a href="WebTemplate.jsp?BODY_PATH=memberJoin.jsp">멤버 가입</a><br>
			</td>
			<td valign=top width=800 text-align=center>
				<article>
				<jsp:include page="${param.BODY_PATH}" />
				</article>
			</td>
		</tr>
	</table>
	<h5>Since 2016, Arivo Coding Club(ACC)</h5>
</body>
</html>
```

attandance.jsp
--------------
```
<%@page contentType="text/html; charset=UTF-8"%>
<%@taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core"%>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <title>출석부</title>
</head>
<body>
    <form name="attendance" action="값을 보낼 주소" method="post 방식인지 get 방식인지">
        <table>
            <caption>출결 관리</caption>
            <thead>
                <tr>
                    <th scope="col">이름</th>
                    <th scope="col">아이디</th>
                    <th scope="col">출결</th>
                    <th scope="col">비고</th>
                </tr>
            </thead>
            <tfoot>
                <tr>
                    <td colspan="4"><%--오늘 날짜받아오기--%></td>
                </tr>
            </tfoot>
            <tbody>
                <tr>
                    <th scope="row">name1</th>
                    <td>LJY</td>
                    <td>
                        <input type="checkbox" name="chk_info" value="출석">출석
                        <input type="checkbox" name="chk_info" value="결석">결석
                    </td>
                    <td><input type="text" name="remarks" /></td>
                </tr>
                   <tr>
                    <th scope="row">name2</th>
                    <td>YSH</td>
                    <td>
                        <input type="checkbox" name="chk_info" value="출석">출석
                        <input type="checkbox" name="chk_info" value="결석">결석
                    </td>
                    <td><input type="text" name="remarks" /></td>
                </tr>
                   <tr>
                    <th scope="row">name3</th>
                    <td>RHS</td>
                    <td>
                        <input type="checkbox" name="chk_info" value="출석">출석
                        <input type="checkbox" name="chk_info" value="결석">결석
                    </td>
                    <td><input type="text" name="remarks" /></td>
                </tr>
                   <tr>
                    <th scope="row">name4</th>
                    <td>ODG</td>
                    <td>
                        <input type="checkbox" name="chk_info" value="출석">출석
                        <input type="checkbox" name="chk_info" value="결석">결석
                    </td>
                    <td><input type="text" name="remarks" /></td>
                </tr>
                   <tr>
                    <th scope="row">name5</th>
                    <td>LGE</td>
                    <td>
                        <input type="checkbox" name="chk_info" value="출석">출석
                        <input type="checkbox" name="chk_info" value="결석">결석
                    </td>
                    <td><input type="text" name="remarks" /></td>
                </tr>
                   <tr>
                    <th scope="row">name6</th>
                    <td>CPG</td>
                    <td>
                        <input type="checkbox" name="chk_info" value="출석">출석
                        <input type="checkbox" name="chk_info" value="결석">결석
                    </td>
                    <td><input type="text" name="remarks" /></td>
                </tr>
                <tr>
                    <td></td>
                    <td><input type="submit" name="submit" value="완료" />
                    <input type="reset" name="reset" value="리셋" /></td>
                </tr>
            </tbody>
        </table>
    </form>
</body>
</html>
```
