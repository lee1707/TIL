# Today I learned
Spring Boot Basic. I am following lectures of the book called **Spring Boot By Examples**
<br>
Here comes **Error** 

# Symptoms
When I typed `http://localhost:8095/SampleWebApp/` on my browser, an error page appeared.
```
HTTP Status 500 – Internal Server Error
Type Exception Report

Message java.lang.ClassNotFoundException: org.apache.jsp.index_jsp
```

# Cause
My STS showed two warnings.
1. Description	Resource	Path	Location	Type<br>
```
Build path specifies execution environment JavaSE-1.7. There are no JREs installed in the workspace that are strictly compatible with this environment. 	SampleWebApp		Build path	JRE System Library Problem
```
2.<br>
```
No grammar constraints (DTD or XML Schema) referenced in the document.	logback.xml	/SampleWebApp/src/main/resources	line 1	XML Problem
```

# Tried 
I tried top three [answers](https://stackoverflow.com/questions/14804945/maven-build-path-specifies-execution-environment-j2se-1-5-even-though-i-chang) from stackoverflow.
<br>
But didn't worked well, it turned out I don't have jre 1.7.

# Still working on it
My jre version is 1.8, and I couldn't get JavaSE-1.7. Oracle doesn't offer jre 1.7 anymore. It's old.<br>
I guess this is one the reasons why error appeared. I am going to keep working on it.
