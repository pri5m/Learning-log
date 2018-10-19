# Service beans

[Service beans slides](https://learningcentral.cf.ac.uk/webapps/blackboard/execute/content/file?cmd=view&content_id=_4842095_1&course_id=_387554_1)

Injecting a dependency

```
@Controller
//This is a controller. It is NOT a RestController. It is part of the Spring MVC
framework so more aligned with server-side generation of HTML.
public class CharitySearchController {
static final Logger LOG = LoggerFactory.getLogger(CharitySearchController.class);
private CharityService charityService;
@Autowired
public CharitySearchController(CharityService aService) {
charityService = aService;
}
```

Implementing the bean
```
@Service
public class CharityServiceStatic implements CharityService {
```
