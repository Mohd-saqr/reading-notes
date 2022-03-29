# Spring Security Architecture
Spring security is framework used for securing Spring applications. It stands between client and application and gives possibility of configuring what data and functionalities are exposed to which users. Also, it handles common vulnerabilities. 


![image](https://user-images.githubusercontent.com/97642724/160506673-a637d79d-9577-4547-860f-a4e035ed717b.png)



Authentication filter creates authentication object that contains credentials from request. Than it sends that object to authentication manger, to choose appropriate authentication provider. There are different authentication strategies, and for each strategy there is appropriate AuthenticationProvider. Each provider needs to get user from the system and to check its credentials (is it expired, is
password correct…). You can use different type of authentication providers in Spring security, or you can combine them.
Only part that is different between providers is how it finds user. That part is extracted in class UserDetailsService in loadByUsername() method which returns UserDetails object. UserDetails object contains data about user and account (is account expired, locked or enabled, are credentials non expired…) which authentication provider needs for authentication. If authentication is successful the Authentication object with the principal is returned to the Authentication Filter, which will set principal to SecurityContext . SecurityContext is associated
with current thread, and it provide principal for further authorization of request.
In the case that authentication is failed, spring throws an AuthenticationException, which goes back to the filter, so it can be catch or showed to user.



### Configure Spring Security for Spring Boot Project

Filters : Before the request reaches the Dispatcher Servlet, it is first intercepted by a chain of filters.

![image](https://user-images.githubusercontent.com/97642724/160506811-139256d0-1f9b-489a-a7d8-6c0b6de89746.png)





### Processing Secure Methods Asynchronously :

Since the SecurityContext is thread-bound, if you want to do any background processing that calls secure methods (for example, with @Async), you need to ensure that the context is propagated. This boils down to wrapping the SecurityContext with the task (Runnable, Callable, and so on) that is executed in the background. Spring Security provides some helpers to make this easier, such as wrappers for Runnable and Callable. To propagate the SecurityContext to @Async methods, you need to supply an AsyncConfigurer and ensure the Executor is of the correct type:

```
@Configuration
public class ApplicationConfiguration extends AsyncConfigurerSupport {

  @Override
  public Executor getAsyncExecutor() {
    return new DelegatingSecurityContextExecutorService(Executors.newFixedThreadPool(5));
  }

}
```
### WebSecurityConfig extends WebSecurityConfigurerAdapter :

- has a UserDetailsService
- passwordEncoder bean
- configure AuthManagerBuilder
    - ``auth.userDetailsService(userDetailsService).passwordEncoder    (passwordEncoder())``
- configure HttpSecurity
    - cors? csrf?
    - matchers for URLs that are allowed
     - ensure that login and signup URLs allowed; also consider homepage etc.
    - formLogin with login page set up
    - logout

```
    @Override
    @Bean
    public AuthenticationManager authenticationManagerBean() throws Exception {
        return super.authenticationManagerBean();
    }
```

---------------------------------------------


# Resourses

[Spring Auth Cheat Sheet](https://github.com/codefellows/seattle-java-401d2/blob/master/SpringAuthCheatSheet.md).

[Spring Security Architecture](https://spring.io/guides/topicals/spring-security-architecture/).

[Understand Spring Security Architecture and implement Spring Boot Security](https://www.javainuse.com/webseries/spring-security-jwt/chap3)

