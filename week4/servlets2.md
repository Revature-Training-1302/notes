## Session Tracking
- Keeping track of information between requests
- A session is just an interval of time
- Session tracking helps us keep track of the state (data) of our user
- HTTP is stateless, meaning for every new request, the server is treating it as a completely new request, not making any assumptions about anything

### Cookies
- Cookies are a small piece information that can persist between the requests
- Cookies have a name, value, and some optional attributes
- If you disable cookies in the browser, then you can't use them with your application
- Simple way of maintaining data
- Methods
    - addCookie
    - getCookies
- https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies

### Request Dispatcher
- helps us dispatch requests to a different resource/servlet
- collaboration between different servlets
- we'll use the request dispatcher to pass data around the different servlets
- Two Methods:
    - forward - send a request from servlet to another resource (html, jsp, servlet)
    - include - include the content of the current resource in the response

### HttpSession
- 2 methods
    - setAttribute(String key, Object value)
    - getAttribute(String key)



### Optional Exercise:
- Try Clearing cookies and see how the demos change: 
- On your computer, open Chrome.
- At the top right, click More. Settings.
- Under "Privacy and security," click Site settings.
- Click Cookies.
- From here, you can: Turn on cookies: Next to "Blocked," turn on the switch. Turn off cookies: Turn off Allow sites to save and read cookie data.