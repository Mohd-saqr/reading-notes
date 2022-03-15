# Serving Web Content with Spring MVC.
 the Spring MVC it's big framework it use for build web-Applecations and use for cloud etc ..


 to use this framework we need :
 1-JDK 1.8 OR LATER .
2- Gradle 4+ or Maven 3.2+.
3- IDE

first we need to fo some steps to use this framework:

1- Download and unzip the source repository for this guide, or clone it using Git: git clone 
`
https://github.com/spring-guides/gs-serving-web-content.git
`
2-cd into gs-serving-web-content/initial

3- create Web Controller class it contain this code 

`````
package com.example.servingwebcontent;

import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RequestParam;

@Controller
public class GreetingController {

	@GetMapping("/greeting")
	public String greeting(@RequestParam(name="name", required=false, defaultValue="World") String name, Model model) {
		model.addAttribute("name", name);
		return "greeting";
	}

}
`````

## Spring Boot Devtools
the it's a framework that use for devlopment web-applecation 
and we can bulid requset method to connect to server and we can use it for logging and connecting to data base as you see in picture.

![image](https://user-images.githubusercontent.com/97642724/158468103-7078f18d-e76b-4d7b-8920-756bab2efdbc.png)

![image](https://user-images.githubusercontent.com/97642724/158468214-f80ab5d8-8c4b-443f-b2b9-3cf0d58fd65e.png)

------------------------
## Spring MVC and Thymeleaf: how to access data from templates

In a typical Spring MVC application, @Controller classes are responsible for preparing a model map with data and selecting a view to be rendered. This model map allows for the complete abstraction of the view technology and, in the case of Thymeleaf, it is transformed into a Thymeleaf context object (part of the Thymeleaf template execution context) that makes all the defined variables available to expressions executed in templates.

1- Spring model attributes:

Spring MVC calls the pieces of data that can be accessed during the execution of views model attributes. The equivalent term in Thymeleaf language is context variables.

There are several ways of adding model attributes to a view in Spring MVC. such as 

Add attribute to Model via its addAttribute method:

```
 @RequestMapping(value = "message", method = RequestMethod.GET)
        public String messages(Model model) {
            model.addAttribute("messages", messageRepository.findAll());
            return "message/list";
        }

```

return ModelAndView with model attributes included:

```
@RequestMapping(value = "message", method = RequestMethod.GET)
        public ModelAndView messages() {
            ModelAndView mav = new ModelAndView("message/list");
            mav.addObject("messages", messageRepository.findAll());
            return mav;
        }
```

2- Request parameters
Request parameters can be easily accessed in Thymeleaf views. Request parameters are passed from the client to server like:
```
www.google.com/id=2
```

3- Session attributes

```
 @RequestMapping({"/"})
        String index(HttpSession session) {
            session.setAttribute("mySessionAttribute", "someValue");
            return "index";
        }
 <p th:text="${session.mySessionAttribute}" th:unless="${session == null}">[...]</p>

```
4- Spring beans
Thymeleaf allows accessing beans registered at the Spring Application Context with the @beanName syntax, for example:

```
<div th:text="${@urlService.getApplicationUrl()}">...</div> 
```
In the above example, @urlService refers to a Spring Bean registered at your context, e.g.


````
@Configuration
        public class MyConfiguration {
            @Bean(name = "urlService")
            public UrlService urlService() {
                return () -> "domain.com/myapp";
            }
        }

        public interface UrlService {
            String getApplicationUrl();
        }
````

# REFERANCES
[1-Thymeleaf](https://www.thymeleaf.org/doc/articles/springmvcaccessdata.html)<br/>
[2-Serving Web Content with Spring MVC
](https://spring.io/guides/gs/serving-web-content/#initial)<br/>
[3-Amigoscode](https://www.youtube.com/watch?v=9SGDpanrc8U)<br/>