# Today I learned
Today I learned Web Templeate 1,2.

* **GET/POST method <br>**
 GET : mainly to **read** <br>
 POST: mainly to **modify**

# Errors
* Error
```
한글 looks ????? on web
```

* solution
```
- Go to **apache-tomcat-9.0.5\conf\server.xml**
- Look for <Connector port="8080"...> and add URlEncoding="euc-kr"
```
In my case, I am using **Sublime text**. I added **URlEncoding="UTF-8"***

* Error
```
When I compile java class, my cmd shows
**error: package javax.servlet does not exist**
```
* solution
```
add the path to Tomcat's /lib/servlet-api.jar file to the compile time classpath.

Here's what I did
javac -cp .;C:\Users\gramgram\Downloads\apache-tomcat-9.0.5\apache-tomcat-9.0.5\lib\servlet-api.jar BBSItem.java -encoding UTF-8
```
reference [stackoverflow:javax servelt does not exist](https://stackoverflow.com/questions/9193228/compile-error-package-javax-servlet-does-not-exist)

