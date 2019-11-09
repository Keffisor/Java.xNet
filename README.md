Version Java 8
Proxy servers working: HTTP and Socks5.

I personally not recommend this library for threading because this library use the HttpUrlConnection

Example:
<pre>
HttpRequest request = new HttpRequest();

String result = request.Get("http://checkip.amazonaws.com/").toString();

String result2 = request.Post("http://example.com", "mail=example@gmail.com&password=pass");

String resultWithProxy = request.PostProxy("http://example.com", "mail=example@gmail.com&password=pass", "179.0.0.0:8080", Proxy.Type.HTTP);

// Now with variables
HttpRequest request = new HttpRequest();
       request.ConnectTimeout = 5000;
       request.Cookies.add("csf=cookie");
       request.Referer = "https://google.com";
       request.UserAgent = Http.ChromeUserAgent();
       request.ContentType = "application/json";
       request.KeepAlive = true;
       String resultf = request.Post("http://example.com", "mail=example@gmail.com&password=pass").toString();
       System.out.println(resultf);
</pre>
