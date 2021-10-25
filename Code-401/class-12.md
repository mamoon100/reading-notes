# Spring RESTful Routing & Static Files

The Spring Framework provides a number of annotations that can be used to configure RESTful routing and static file serving.

Let's First Talk About The RequestMapping Annotation.

1. @RequestMapping by path

   > @RequestMapping(value = "/hello", method = RequestMethod.GET)

2. @RequestMapping by HTTP method

   > @RequestMapping(value ="/hello", method = Post)

3. RequestMapping With Path Variables

   > @RequestMapping(value = "/hello/{name}", method = RequestMethod.GET)

4. RequestMapping With Request Parameters

   > @RequestMapping(value = "/hello", method = RequestMethod.GET)

We can see from above that the @RequestMapping annotation can be used to map a request to a method and it's useful annotation to deal with Spring.

---

Let's talk about Storing data and retrieve it from relational database using Spring JPA.

First create an @Entity.

```java
    @Entity

public class Customer {

@Id
@GeneratedValue(strategy=GenerationType.AUTO)
private Long id;
private String firstName;
private String lastName;

protected Customer() {}

public Customer(String firstName, String lastName) {
this.firstName = firstName;
this.lastName = lastName;
}

@Override
public String toString() {
return String.format(
"Customer[id=%d, firstName='%s', lastName='%s']",
id, firstName, lastName);
}

public Long getId() {
return id;
}

public String getFirstName() {
return firstName;
}

public String getLastName() {
return lastName;
}
}
```

You Can see that there is two constructors in the above class, the first one you can use to create a new customer and the second one is used to create a new customer from the database and The default constructor exists only for the sake of JPA. You do not use it directly, so it is designated as **protected**.
