Today I learned 
===========
깃헙오류:한글로작성시스페이스바누르면글자가사라짐->영어로작성


From JSP&Servlet for Java Programmers(by HanbitMedia)
I learned filter and wrppaer 

By practicing example page, I found Error.


#Error
===========
My Tomcat 9.0 doesn't show its stdout log.
It shows only localhost access log like this.

```
0:0:0:0:0:0:0:1 - - [29/Mar/2018:20:38:39 +0900] "GET /brain11/Simple.jsp HTTP/1.1" 200 194
0:0:0:0:0:0:0:1 - - [29/Mar/2018:21:50:58 +0900] "GET /brain11/Simple.jsp HTTP/1.1" 200 194
127.0.0.1 - - [29/Mar/2018:21:54:28 +0900] "GET / HTTP/1.1" 200 11450
127.0.0.1 - - [29/Mar/2018:23:13:19 +0900] "GET / HTTP/1.1" 200 11450
127.0.0.1 - - [29/Mar/2018:23:29:47 +0900] "GET / HTTP/1.1" 200 11450
```


(My testJsp page is on /brain11/Simple.jsp)

So I googled for solution.


There were some people using log4j for logging.
I downloaded log4j.jar on C:\Users\gramgram\Downloads\apache-tomcat-9.0.5\apache-tomcat-9.0.5\webapps\brain11\WEB-INF\lib
and made log4j.properties file on C:\Users\gramgram\Downloads\apache-tomcat-9.0.5\apache-tomcat-9.0.5\webapps\brain11\WEB-INF\classes


**log4j.properties**


```
log4j.rootLogger=DEBUG, stdout, TOMCAT

log4j.appender.stdout=org.apache.log4j.ConsoleAppender
log4j.appender.stdout.layout=org.apache.log4j.PatternLayout
log4j.appender.stdout.layout.ConversionPattern=%d{dd-MM-yy HH:mm:ss:SSS}-{%p}%c{2}Thread[%t];%x%m%n
```


also, I restarted Tomcat and Web brower.

But I still can't find stdout message.

So I asked Junyoung(newt), He taught me that my eclipse is getting message from tomcat.


#solution
===========
-change log directory from eclipse 

-make new code for stdout

```
package practice;

import java.io.File;
import java.io.FileNotFoundException;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.PrintStream;
import java.time.LocalDate;
import java.time.format.DateTimeFormatter;

/**
 * Created by newt.on on 2018. 3. 29..
 */

public class HowToSystemOutToFile {
	static final int INFO = 1;
	static final int ERROR = 2;
	
	static int logLevel = INFO;
	public static void main(String[] args) throws IOException {
		String dir = "C:\\Users\\gramgram\\Downloads\\apache-tomcat-9.0.5\\apache-tomcat-9.0.5\\logs";
		DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yyyyMMdd");
		
		LocalDate today = LocalDate.now();
		String fileName =dir + "\\stdout-" + formatter.format(today) + ".log";
		// => ...\logs\stdout-20180330.log
		
		// 위에서 만든 파일이름으로 파일 객체 생성
		File file = new File(fileName);
		
		// 파일에 출력하기 위한 아웃풋 스트림 생성
		FileOutputStream fos = new FileOutputStream(file);
		
		// 시스템.아웃을 대체하기 위하여 같은 타입인 프린트스트림 타입으로 감싸기
		PrintStream ps = new PrintStream(fos);
		// 기존의 아웃을 변경 = System.out <- This!
		System.setOut(ps);
		
		logLevel = ERROR;
		info("Hello %s", "Leegang");
		error("Hello(ERROR Level) %s", "Leegang");
		fos.close();
	}
	
	public static void info(String message, Object... args) {
		if(logLevel <= INFO) {
			System.out.printf("[INFO] " + message + "\n", args);
		}
	}
	
	public static void error(String message, Object... args) {
		if(logLevel <= ERROR) {
			System.out.printf("[ERROR] " + message + "\n", args);
		}
	}
}
```

reference : Junyoung (https://github.com/nnoco)


