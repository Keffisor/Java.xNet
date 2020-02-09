Version Java 8

Proxy servers working: HTTP, Socks5 and proxyless.

I personally not recommend this library for threading because this library use the HttpUrlConnection

Example:
<pre>
HttpRequest request = new HttpRequest();

String result = request.Get("http://checkip.amazonaws.com/").toString();

String result2 = request.Post("http://example.com", "mail=example@gmail.com&password=pass").toString();

String resultWithProxy = request.Post("http://example.com", "mail=example@gmail.com&password=pass", 
"179.0.0.0:8080", Proxy.Type.HTTP).toString();

String resultWithProxyGet = request.Get("http://example.com", "mail=example@gmail.com&password=pass", 
"179.0.0.0:8080", Proxy.Type.HTTP).toString();

// Now with variables
HttpRequest request = new HttpRequest();
       request.ConnectTimeout = 5000;
       request.Cookies.add("cookieName=cookieValue");
       request.Referer = "https://google.com";
       request.UserAgent = Http.ChromeUserAgent();
       request.ContentType = "application/json";
       request.KeepAlive = true;
       String resultf = request.Post("http://example.com", "mail=example@gmail.com&password=pass").toString();
       System.out.println(resultf);
</pre>

This library have been inspired by the C# library xNet (https://github.com/X-rus/xNet)
