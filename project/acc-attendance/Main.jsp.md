# Today I learned
Main.jsp

- Problems need to fix
1) main에서 창 크기를 줄였을 때 둥둥 뜨는게 배경화면에서 벗어나는 문제
2) main에서 학습활동 누를시 example로 가는 오류
3) board-list(servlet)이 아니라 BoardListView로 가야하는데 annotation문제로 연결안되는 오류  
4) 소개에서 로그인 누르면 signinForm으로 가야한느데 자꾸 signin으로 가는 이유

```
<%@page contentType="text/html; charset=UTF-8"%>
<%@taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core"%>
<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport"
	content="width=device-width, initial-scale=1, shrink-to-fit=no">
<meta name="description" content="">
<meta name="author" content="">
<link rel="icon" href="../../../../favicon.ico">

<title>아리보 코딩 클럽</title>

<!-- Bootstrap core CSS -->
<link href="/acc-attendance/assets/css/bootstrap.min.css"
	rel="stylesheet">
<link href="/acc-attendance/assets/css/my-bootstrap.css"
	rel="stylesheet">

<!-- Custom styles for this template -->
<link href="/acc-attendance/assets/css/jumbotron.css" rel="stylesheet">

<!-- magic style -->
<link rel="stylesheet" href="/acc-attendance/assets/css/magic.css">

<!-- button style -->
<link rel="stylesheet" href="/acc-attendance/assets/css/buttons.css">

<link href="https://fonts.googleapis.com/css?family=Hi+Melody|Luckiest+Guy" rel="stylesheet">

<style>

#font1{
	font-family: 'Luckiest Guy', cursive;
	color: #FF9900;
}

.font2{
	color: white;
}

.jumbotron{
	transition: all 2s;
}
.jumbotron {
	height:520px;
	padding: 2rem 1rem;
	margin-bottom: 2rem;
	background-image: url('science-fiction.jpg');
	border-radius: .3rem;
	background-size: cover;
	
}

p{
    display: inline-block;
    vertical-align: middle;
    transform: translateZ(0);
    box-shadow: 0 0 1px rgba(0, 0, 0, 0);
    backface-visibility: hidden;
    -moz-osx-font-smoothing: grayscale;
    transition-duration: 0.3s;
    transition-property: transform 1s;
}

p:hover,
p:focus,
p:active {
    transform: scale(1.1);
}

#video{
	top: 300px;
	left: 100px;
	position: absolute;
	height: 300px;
	width: 300px;
}

@keyframes float {
	0% {
		box-shadow: 0 5px 15px 0px rgba(0,0,0,0.6);
		transform: translatey(0px);
	}
	50% {
		box-shadow: 0 25px 15px 0px rgba(0,0,0,0.2);
		transform: translatey(-20px);
	}
	100% {
		box-shadow: 0 5px 15px 0px rgba(0,0,0,0.6);
		transform: translatey(0px);
	}
}

.container {
	width: 100%;
	height: 100%;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
}

.avatar {
	position: relative;
	left: 700px;
	width: 150px;
	height: 150px;
	box-sizing: border-box;
	border: 5px white solid;
	border-radius: 50%;
	overflow: hidden;
	box-shadow: 0 5px 15px 0px rgba(0,0,0,0.6);
	transform: translatey(0px);
	animation: float 6s ease-in-out infinite;
	img { width: 100%; height: auto; }

}



</style>
</head>

<body onload="document.querySelector('body').style.backgroundColor='white';">

	<nav class="navbar navbar-expand-md navbar-dark fixed-top bg-dark">
		<a class="navbar-brand" href="#">Arivo Coding Club</a>
		<button class="navbar-toggler" type="button" data-toggle="collapse"
			data-target="#navbarsExampleDefault"
			aria-controls="navbarsExampleDefault" aria-expanded="false"
			aria-label="Toggle navigation">
			<span class="navbar-toggler-icon"></span>
		</button>

		   <div class="collapse navbar-collapse" id="navbarCollapse">
          <ul class="navbar-nav mr-auto">
            <li class="nav-item active">
              <a class="nav-link" href="Main.jsp">홈 <span class="sr-only">(current)</span></a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="intro.html">ACC소개</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="playground.html">놀이터</a>
            </li>
            <li class="nav-item dropdown">
              <a class="nav-link dropdown-toggle" href="http://example.com" id="dropdown01" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">학습활동</a>
              <div class="dropdown-menu" aria-labelledby="dropdown01">
                <a class="dropdown-item" href="attendanceInput.html">출결입력</a>
                <a class="dropdown-item" href="attendanceCheck.html">출석확인</a>
                <a class="dropdown-item" href="progress.html">진도표</a>
                <a class="dropdown-item" href="board.html">게시판</a>
              </div>
            </li>
          </ul>
        

			<c:choose>
				<c:when test="${sessionScope.SIGNIN_ID == null}">
					<button class="btn btn-outline-success my-2 my-sm-0" type="submit">
						<a href="signinForm.html">로그인</a>
					</button>
					<%--             <jsp:include page="SigninWindow.jsp"/> --%>
				</c:when>
				<c:otherwise>
					<!--
            <a href="oldSignout">로그아웃</a>
          -->
					<jsp:include page="Signout.jsp" />
				</c:otherwise>
			</c:choose>
			<button class="btn btn-outline-success my-2 my-sm-0" type="submit">
				<a href="signup.html">회원가입</a>
			</button>
			<!--
        <form class="form-inline my-2 my-lg-0">
          <input class="form-control mr-sm-2" type="text" placeholder="Search" aria-label="Search">
          <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
        </form>
        -->
		</div>
	</nav>

	<main role="main"> <!-- Main jumbotron for a primary marketing message or call to action -->
	<div class="jumbotron">
		<div class="container">
			<div class="center jumbovidtext">
			<h1 class="display-3" id="font1">Arivo Coding Club(ACC)</h1>
			
			<div class="font2">
			안녕하세요, 여러분! 아리보 코딩 클럽에 방문한 여러분을 진심을 환영합니다. 
			아리보 코딩 클럽은 JAVA를 공부하는 모임입니다.
			</div>
			
			<p>
				<a class="button button-3d button-action button-pill" href="intro.html" role="button">더
					알고싶어요 &raquo;</a>
			</p>
			
			<div class="avatar">
				<a href="intro.html"><img src="super-mario.jpg" /></a>
			</div>
			
			</div>
			<!--  
			<video id="video" preload="auto" autoplay="true" loop="loop" muted="muted"
			volumn="0"><source src="Notebook.mp4" type="video/mp4"/></video>
			-->
		</div>
	</div>

	<div class="container">
		<!-- Example row of columns -->
		<div class="row">
			<div class="col-md-4">
			
				<p>
					<a class="button button-3d button-action button-pill" href="progress.html"
						role="button">진도표 보러가기&raquo;</a>
				</p>
			</div>
			<div class="col-md-4">
				
				<p>
					<a class="button button-3d button-action button-pill" href="attendanceInput.html"
						role="button">출결 입력 하러가기&raquo;</a>
				</p>
			</div>
			<div class="col-md-4">
			
				<p>
					<a class="button button-3d button-action button-pill" href="board-list" role="button">게시판
						보러가기 &raquo;</a>
				</p>
			</div>
		</div>

		<hr>

	</div>
	<!-- /container --> </main>

	<footer class="container">
		<p>&copy; Arivo Coding Club 2016-2018</p>
	</footer>

	<!-- Bootstrap core JavaScript
    ================================================== -->
	<!-- Placed at the end of the document so the pages load faster -->
	<script>window.jQuery || document.write(<script src="<%= request.getContextPath() %>/assets/js/jquery-slim.min.js"><\/script>)
	</script>
	<script src="<%=request.getContextPath()%>/assets/js/popper.min.js"></script>
	<script
		src="<%=request.getContextPath()%>/assets/js/bootstrap.min.js"></script>
</body>
</html>
```
