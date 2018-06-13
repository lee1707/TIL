# Today I learned
Resolution for Errors - SQL Syntax Error, SourceTree password Error


# #SQL Syntax Error
Symptoms
-----------------
```
You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'where id ='null'' at line 1
```

Tried
-----------------
Add this code to print log.
```
 String query;
 if(Objects.isNull(id)) {
    query = "SELECT `password` FROM `userinfo` WHERE id is null"; 
 } else {
    query = "SELECT `password` FROM `userinfo` WHERE id = '"+id+"'"; 
 }
 System.out.println(query);
```

Cause
-----------------
```
ResultSet rs = stmt.executeQuery("select password" +
                                 "from userinfo where id = '" + id + "';"); 
```
1. There were no space befor `from`
2. I forgot to recompile this java file and restart tomcat.

Resolution
-----------------
I changed code to this.
```
"SELECT `password` FROM `userinfo` WHERE id = '"+id+"'"; 
```
Also, recompile this file.

# #SourceTree Password Error

Symptoms
-----------------
When I tried to push/pull on SourceTree, it made me type github id and password.<br>
Althought my information was right, I failed to login and got this message.
```
git -c diff.mnemonicprefix=false -c core.quotepath=false push -v --set-upstream origin master:master
fatal: HttpRequestException encountered.
   �� ��û�� ������ ���� ������ �߻��߽��ϴ�.

remote: Anonymous access to lee1707/hello-world.git denied.
fatal: Authentication failed for 'https://@github.com/lee1707/hello-world.git/'

Pushing to https://@github.com/lee1707/hello-world.git
Completed with errors, see above
```
Cause
-----------------
'https://@github.com/lee1707/hello-world.git/'<br>
This was a main cause, but not really helpful to solve this error by my own.<br>
(SourceTree couldn't get my address somehow. guess it is SourceTree Bug)

Resolution
-----------------
  1. On SourceTree, Go to Tools-Options-Authentication-Accounts<br>
  2. Click All accounts(one by one) and delete password except yourGithubId@github.com(it is located at the top)<br>
  3. Click yourGithubId@github.com and click `set as default`<br><br>
   
  4. On SourceTree, Go to Settings-Remotes-Origin-Edit
  5. on Required Information-URL/Path, add your id before @.
  ```
  https://@github.com/lee1707/hello-world.git
  to
  https://lee1707@github.com/lee1707/hello-world.git
  ```
  6. on Optional extended integration(this is located under the #5), erase your **username** 

Suggestion
-----------------
If you continuously have this Error, you are recommended to use **git**<br>
[git download](https://git-scm.com/download/win)<br>
This is Linux command line tool(shell), which you can use on window.<br><br>

You can replace SourceTree with git.<br>
Here's some example codes.

```
gramgram@DESKTOP-AOREGJ3 MINGW64 ~
$ cd Documents/learning-git/hello-world/

gramgram@DESKTOP-AOREGJ3 MINGW64 ~/Documents/learning-git/hello-world (master)
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   #4-lotto-generator.html
        deleted:    README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        #5-lotto-generator.html
        #6-profile.html

no changes added to commit (use "git add" and/or "git commit -a")

gramgram@DESKTOP-AOREGJ3 MINGW64 ~/Documents/learning-git/hello-world (master)
$ git add \#4-lotto-generator.html

gramgram@DESKTOP-AOREGJ3 MINGW64 ~/Documents/learning-git/hello-world (master)
$ git add README.md

gramgram@DESKTOP-AOREGJ3 MINGW64 ~/Documents/learning-git/hello-world (master)
$ git commit -m "apply changes"
[master 3e2224d] apply changes
 2 files changed, 4 insertions(+), 4 deletions(-)
 delete mode 100644 README.md

gramgram@DESKTOP-AOREGJ3 MINGW64 ~/Documents/learning-git/hello-world (master)
$ git push origin master
Counting objects: 3, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 398 bytes | 398.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/lee1707/hello-world.git
   5d07cd4..3e2224d  master -> master

gramgram@DESKTOP-AOREGJ3 MINGW64 ~/Documents/learning-git/hello-world (master)
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        #5-lotto-generator.html
        #6-profile.html

nothing added to commit but untracked files present (use "git add" to track)

gramgram@DESKTOP-AOREGJ3 MINGW64 ~/Documents/learning-git/hello-world (master)
$ git add .
warning: LF will be replaced by CRLF in #5-lotto-generator.html.
The file will have its original line endings in your working directory.
warning: LF will be replaced by CRLF in #6-profile.html.
The file will have its original line endings in your working directory.

gramgram@DESKTOP-AOREGJ3 MINGW64 ~/Documents/learning-git/hello-world (master)
$ git commit -m "add #5, #6"
[master a04db2a] add #5, #6
 2 files changed, 92 insertions(+)
 create mode 100644 #5-lotto-generator.html
 create mode 100644 #6-profile.html

gramgram@DESKTOP-AOREGJ3 MINGW64 ~/Documents/learning-git/hello-world (master)
$ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

gramgram@DESKTOP-AOREGJ3 MINGW64 ~/Documents/learning-git/hello-world (master)
$ git checkout -b develop
Switched to a new branch 'develop'

gramgram@DESKTOP-AOREGJ3 MINGW64 ~/Documents/learning-git/hello-world (develop)
$ git status
On branch develop
nothing to commit, working tree clean

gramgram@DESKTOP-AOREGJ3 MINGW64 ~/Documents/learning-git/hello-world (develop)
$ git branch

* develop
  master
  
gramgram@DESKTOP-AOREGJ3 MINGW64 ~/Documents/learning-git/hello-world (develop)
$ curl "http://localhost:8090/brain13/WebTemplate.jsp?BODY_PATH=LoginResult.jsp?LOGIN_RESULT=FAIL" -v
* STATE: INIT => CONNECT handle 0x4a2e150; line 1392 (connection #-5000)
* Added connection 0. The cache now contains 1 members
* STATE: CONNECT => WAITRESOLVE handle 0x4a2e150; line 1428 (connection #0)
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0*   Trying ::1...
* TCP_NODELAY set
* STATE: WAITRESOLVE => WAITCONNECT handle 0x4a2e150; line 1509 (connection #0)
* Connected to localhost (::1) port 8090 (#0)
* STATE: WAITCONNECT => SENDPROTOCONNECT handle 0x4a2e150; line 1561 (connection #0)
* Marked for [keep alive]: HTTP default
* STATE: SENDPROTOCONNECT => DO handle 0x4a2e150; line 1579 (connection #0)
> GET /brain13/WebTemplate.jsp?BODY_PATH=LoginResult.jsp?LOGIN_RESULT=FAIL HTTP/1.1
> Host: localhost:8090
> User-Agent: curl/7.58.0
> Accept: */*
>
* STATE: DO => DO_DONE handle 0x4a2e150; line 1658 (connection #0)
* STATE: DO_DONE => WAITPERFORM handle 0x4a2e150; line 1783 (connection #0)
* STATE: WAITPERFORM => PERFORM handle 0x4a2e150; line 1799 (connection #0)
* HTTP 1.1 or later with persistent connection, pipelining supported
< HTTP/1.1 200
< Set-Cookie: JSESSIONID=188C16BE91AE0AA6827764959231DD35; Path=/brain13; HttpOnly
< Content-Type: text/html;charset=UTF-8
< Content-Length: 877
< Date: Mon, 02 Apr 2018 15:56:45 GMT
<
{ [877 bytes data]
* STATE: PERFORM => DONE handle 0x4a2e150; line 1968 (connection #0)
* multi_done
100   877  100   877    0     0  28290      0 --:--:-- --:--:-- --:--:-- 28290
<!DOCTYPE html>
<html lang="en">
<head>
        <meta charset="UTF-8">
        <title>한빛 미디어</title>
</head>
<body>
        <h1>한빛 미디어</h1>
        <table border=1 cellpadding=10>
                <tr>
                        <td width=150 valign=top>
                                <a href="WebTemplate.jsp?BODY_PATH=Intro.jsp">회사소개</a><br>
                                <a href="books-info">책 정보</a><br>
                                <a href="WebTemplate.jsp?BODY_PATH=BBSInput.jsp">게시판 글쓰기</a><br>
                                <a href="bbs-list">게시판 글읽기</a><br>
                        </td>
                        <td valign=top width=650>


<<!DOCTYPE html>
<html lang="en">
<head>
        <meta charset="UTF-8">
        <title>로그인</title>
</head>
<body>
        <h4>로그인</h4>



                        로그인에 실패했습니다.<br>아이디와 패스워드를 체크하세요


</body>
</html>

                        </td>
                </tr>
        </table>
        <h5>Copyright@ 1993-2010 한빛미디어(주)</h5>
</body>
</html>
* Connection #0 to host localhost left intact
* Expire cleared

```

**These resolutions were suggested by Junyoung**<br>
reference : [Junyoung](https://github.com/nnoco)

#fatal: HttpRequestException encountered.<br>
#fatal: Authentication failed
