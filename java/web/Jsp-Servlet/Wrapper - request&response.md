Today I learned
===========

**Today I learned how to create RequestWrapper class and ResponseWrapper class.**

I practiced some examples from the JSP&Servelt book.


-RequestWrapper class should contain getParameter method, getParameterValues method, and getParameterMap.
because servlet class and JSP page use all these three method when they get ```<FORM>``` data.

-ResponseWrapper class uses cookie to prove they really changes some datas from web browers.


Step1
===========
ResopnseWrapper class that change UpperCase data to LowerCase data) -from the book
```
package myfilter;
import javax.servlet.http.*;
import javax.servlet.*;
import java.io.*;
public class CookieLowerCaseResponseWrapper
								extends HttpServletResponseWrapper {
	private HttpServletResponse response;
	public CookieLowerCaseResponseWrapper(
									HttpServletResponse response) {
		super(response);
		this.response = response;
	}
	public void addCookie(Cookie cookie){
		String value = cookie.getValue();
		String newValue = value.toLowerCase();
		cookie.setValue(newValue);
		response.addCookie(cookie);
	}
}
```

Step2
===========
Filter class that uses ResponseWrapper class
```
package myfilter;
import javax.servlet.http.*;
import javax.servlet.*;
import java.io.*;
public class ParamUpperCaseFilter implements Filter{
	public void init(FilterConfig config) throws ServletException {
	}
	public void doFilter(ServletRequest request,
						ServletResponse response, FilterChain chain)
						throws IOException, ServletException {
		ParamUpperCaseRequestWrapper requestWrapper = 
						new ParamUpperCaseRequestWrapper(
									(HttpServletRequest) request);
		chain.doFilter(requestWrapper, response);
	}
	public void destroy(){
	}
}
```

Step3
===========
Add filter class to web.xml file

Step4
===========
create two JSP page and look if they change data
