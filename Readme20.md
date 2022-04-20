## Spring Boot and OAuth2

in spring boot we user spring security to  protect own application 
we use login page and signup page etc.

--------------------------------------------------

### setup spring security.
first add in dependency spring security library and  create class 
for implement security configuration  and create user details service
and mak  user module to implement user details service.



### create login page 
by default spring security provide login page we can create login page and in security confige class change the `loginUrl` to your url in controller it return your login page .

for your login page tou can spicefec username paramater and password also , by default username paramater = username  and password  = password 

```
<form action="login">
<input name="usename">
<input name"password">
<button type="submit">
</form>
```
-------------------------------

### create logout button 

you can just in security confige add `logoutUrl` and create button type ancertage and put your url

```
<a href="/log_out" type=button>logout</a>
```
------------------------------

### create error page 
we can create url page many way first way just creat html page and name it error and put it in templete folder
second way add this to propertis file `server.error.whitelabel.enabled=false`
`server.error.path=/error`

and create end point for error page 

```
@RequestMapping("/error")
public String handleError(HttpServletRequest request) {
    Object status = request.getAttribute(RequestDispatcher.ERROR_STATUS_CODE);
    
    if (status != null) {
        Integer statusCode = Integer.valueOf(status.toString());
    
        if(statusCode == HttpStatus.NOT_FOUND.value()) {
            return "error-404";
        }
        else if(statusCode == HttpStatus.INTERNAL_SERVER_ERROR.value()) {
            return "error-500";
        }
    }
    return "error";
}
```
.

# Resources
[Spring Boot and OAuth2](https://spring.io/guides/tutorials/spring-boot-oauth2/)



