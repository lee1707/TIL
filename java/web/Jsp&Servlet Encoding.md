# Today I learned
#Encoding

# Symptoms
JSP page which contains **#jsp:include(html page)** creates 한글 looks ????<Br>
=> New Encoding Error

# Cause
Tomcat follows JVM default encoding if **jsp:include** file is not jsp file.<br>
This was the main cause after I checked server.xml, eclipse content encoding, sublime encoding, and jsp, html encoding. 
[reference](https://okky.kr/article/197910)

# Resolution
Here's what I did.

1. **make html page to jsp page**<br>

2. add this to web.xml
```
<jsp-config>
  <jsp-property-group>
    <url-pattern>*.html</url-pattern>
    <page-encoding>UTF-8</page-encoding>
  </jsp-property-group>
</jsp-config>
```
[reference](http://geek.starbean.net/?p=459)

3. If it still shows some ??? Add this on Top of the jsp page(=old html page).
```
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8"%>
```

Also, you can change <meta charset=utf-8"/> to <br>
```
<meta http-equiv="Content-Type" content="text/html; charset=utf-8"/>
```
