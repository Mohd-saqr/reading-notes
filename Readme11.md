# The HTTP Request Lifecycle
i will explain all things i picture , first HTTP stands for HyperText Transfer Protocol,HTTP runs on top of the TCP/IP protocol and (later) on the QUIC protocol. Web browsers are HTTP clients that send file requests to Web servers, which in turn handle the requests via an HTTP service.
![HTTP](https://user-images.githubusercontent.com/97642724/158058661-f9985861-91f0-4002-a29f-a656879ff113.png)




# Do a Simple HTTP Request in Java

in java we can use some library to use server method example :

```
create requset 
URL url = new URL("http://example.com");
HttpURLConnection con = (HttpURLConnection) url.openConnection();
con.setRequestMethod("GET");
```

```
get the data from API
Map<String, String> parameters = new HashMap<>();
parameters.put("param1", "val");

con.setDoOutput(true);
DataOutputStream out = new DataOutputStream(con.getOutputStream());
out.writeBytes(ParameterStringBuilder.getParamsString(parameters));
out.flush();
out.close();

```

-----------------------------------------

[Resorses](https://www.baeldung.com/java-http-request) <br/>
[Resorses](https://dev.to/dangolant/things-i-brushed-up-on-this-week-the-http-request-lifecycle-)


