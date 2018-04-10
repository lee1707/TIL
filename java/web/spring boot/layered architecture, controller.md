# Today I learned
layered architecture

# Layered Architecture
(=  Hierarchical Architecture)
```
 User
 Request
 --------
 Controller // MVC ArivoMember Model, View Page, Controller -> Service -> Repository
 Model2 Servlet -> JSP View (Data - Model)
 --------
 Service <-
 ArivoMember
 --------
 ArivoMemberRepository <- interface
 MySqlArivoMemberRepository implements ArivoMemberRepository // findAllMember List<ArivoMember>
 MSSqlArivoMemberRepository implements Arivo
 Repository <- save, query, (CRUD) / Persistence Layer
 -------
 DB(MySQL -> Oracle, MsSQL
 ```

 **Loose Coupling, High Cohesion**
 

# Controller Example 1 : ArivoMemberController
 ```
@Controller
@RequestMapping("/arivo")
public class ArivoMemberController {
	@Autowired
	private ArivoMemberService arivoMemberService;
	// localhost:8080/arivo/members
	@RequestMapping(value = "/members", method = RequestMethod.GET)
	public String getMembersPage(Model model) {
		model.addAttribute("members", arivoMemberService.getAllMembers());
		
		return "arivo-member";
	}
	
	@RequestMapping(value = "/members2", method = RequestMethod.GET)
	@ResponseBody
	public List<ArivoMember> getMembers(Model model) {
		return arivoMemberService.getAllMembers();
	}
}
```

# Controller Example 2 : HelloWorldController
```
@Controller
public class HelloWorldController {
	// Dependency
	// Injection (DI)
	@Autowired
	private Random random;
	
	private Random random2;
	
	private Random random3;
	
	@Autowired
	public void setRandom2(Random random) {
		logger.error("called random2 setter");
		this.random2 = random;
	}
	
	@Autowired
	public HelloWorldController(Random random) {
		logger.error("called constructor.!!");
		this.random3 = random;
	}
	
	private static final Logger logger = LoggerFactory.getLogger(HelloWorldController.class);
	public HelloWorldController() {
		logger.error("HelloWorldController is created!!;");
	}
	
	// <servlet-mapping> url
	@RequestMapping("/hello")
	public String hello(Model model, 
			@RequestParam(required = false) String foo) {
		// localhost:8080/hello?foo=bar <= Query String/ Query Parameter / Request Param
		// required = true (default)
		// localhost:8080/hello <- exception required query X
		// required = false -> OK
		
		// Spring DispatcherServlet <=
		// accept all request.
		
		String[] messages = {
				"annyung",
			"Hello World!!!",
			"NIHAO",
			"Gonbangwa",
			
		};
		
		String message = messages[random.nextInt(messages.length)];
		model.addAttribute("message", message);
		return "world";
	}
}
```
reference : [Junyoung](https://github.com/nnoco)
