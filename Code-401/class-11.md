# Spring

What is spring ?

Spring is a framework for developing **Java** applications.

![spring project](https://1.bp.blogspot.com/-4vTgRx2HlTE/YN9IoM8gMzI/AAAAAAAAuTk/Qk-GDPUDTEENOmwhl04bZLq65PrZUwBTACLcBGAsYHQ/s2048/Spring%2BEcosystem.png)

What is spring mvc ?

A Spring MVC is a Java framework which is used to build web applications. It follows the Model-View-Controller design pattern. It implements all the basic features of a core spring framework like Inversion of Control, Dependency Injection.

![spring mvc](https://miro.medium.com/max/1400/1*5vtc2zP1F3wF4qnD9hDmFg.png)

What is thymeleaf ?

Thymeleaf is a Java XML/XHTML/HTML5 template engine that can work both in web and non-web environments. It is better suited for serving XHTML/HTML5 at the view layer of MVC-based web applications, but it can process any XML file even in offline environments.

## Build Hello World Spring MVC Application

We will build an application which will display Hello World in the browser.

> http://localhost:8080/greeting

Download the **Spring MVC** project from the **GitHub** repository.

`git clone https://github.com/spring-guides/gs-serving-web-content.git`

`cd gs-serving-web-content/initial`

Create a Web Controller

In Spring’s approach to building web sites, HTTP requests are handled by a controller. You can easily identify the controller by the @Controller annotation. In the following example, GreetingController handles GET requests for /greeting by returning the name of a View (in this case, greeting). A View is responsible for rendering the HTML content. The following listing (from src/main/java/com/example/servingwebcontent/GreetingController.java) shows the controller:

```java
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
```

This controller is concise and simple, but there is plenty going on. We break it down step by step.

The @GetMapping annotation ensures that HTTP GET requests to /greeting are mapped to the greeting() method.

@RequestParam binds the value of the query string parameter name into the name parameter of the greeting() method. This query string parameter is not required. If it is absent in the request, the defaultValue of World is used. The value of the name parameter is added to a Model object, ultimately making it accessible to the view template

Run the Application

The Spring Initializr creates an application class for you. In this case, you need not further modify the class provided by the Spring Initializr. The following listing (from src/main/java/com/example/servingwebcontent/ServingWebContentApplication.java) shows the application class:

```java
package com.example.servingwebcontent;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class ServingWebContentApplication {

    public static void main(String[] args) {
        SpringApplication.run(ServingWebContentApplication.class, args);
    }

}
```
