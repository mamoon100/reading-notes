# Spring Authentication

Today we will be talking and reading about the spring Authentication to ask the user who are you and what authorization you have.

Authentication in spring application is done by the **AuthenticationManager**.

```java
public interface AuthenticationManager {

  Authentication authenticate(Authentication authentication)
    throws AuthenticationException;
}
```

An **AuthenticationManager** can do one of 3 things in its authenticate() method:

- Return an Authentication (normally with authenticated=true) if it can verify that the input represents a valid principal.

- Throw an AuthenticationException if it believes that the input represents an invalid principal.

- Return null if it cannot decide.

by this simple interface we can give the user a chance to login and get the authorization.

we can also customize the authentication process.

Spring Security provides some configuration helpers to quickly get common authentication manager features set up in your application. The most commonly used helper is the AuthenticationManagerBuilder, which is great for setting up in-memory, JDBC, or LDAP user details or for adding a custom UserDetailsService. The following example shows an application that configures the global (parent) AuthenticationManager:

```java
@Configuration
public class ApplicationSecurity extends WebSecurityConfigurerAdapter {

   ... // web stuff here

  @Autowired
  public void initialize(AuthenticationManagerBuilder builder, DataSource dataSource) {
    builder.jdbcAuthentication().dataSource(dataSource).withUser("dave")
      .password("secret").roles("USER");
  }

}
```

And there is a cheat sheet that will help you remember the code for spring security.

[Spring Security cheat sheet](https://github.com/codefellows/seattle-java-401d2/blob/master/SpringAuthCheatSheet.md)
