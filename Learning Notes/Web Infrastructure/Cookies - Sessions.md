
## Cookies

<u>What are Cookies?</u>

Cookies are small pieces of data stored in the client's (me) browser. They are commonly used to store information about the user or their interaction with a website. Cookies are sent from the server (**only first time**) and stored on the client's computer, and then sent back to the server with each subsequent request.

<u>Ex:</u> Whenever I google a website, the server of this website sends the page alongside with cookies, these cookies will now be stored in my browser, so if I visit this website again it will recognize me because of the saved cookies on my browser.

<u>Cookies (php)</u>

- php supports cookies, we can set cookies using the following method:

		setcookie(_name_, _value_, _expiration date_);

			- _name_: required, specifies the name of the cookie

			- value_: Optional, specifies the value of the cookie

			-_expiration date_: Optional, specifies when the cookie expires (time()+..)

-  Cookies are part of the header, so setcookie() must be called before any output is sent to the browser

- To **delete** a cookie, use the setcookie() function with an expiration date in the past.

- Any cookie sent to you from the client (client’s browser) will automatically be stored in a $_COOKIE auto-global array

<u>Cookies (Limitations)</u>

- Users data are not completely controlled by server (can be deleted or modified by client side processes).

-  Require sending user data with each request [After the first time, every time I enter a website the client’s browser has to send the stored cookies] (confidentiality, performance issue).

- Developer must take care of putting all cookies writing before any HTML code.

## **Session**s

<u>What is a Session?</u>

1-    When you log in to a website, the **server creates a session** for your user account. This session includes various pieces of information such as your user ID, permissions, and any other relevant data.

2-    The server then **generates** a **unique session ID** for your session.

3-    This session **ID is sent to your browser** **as a cookie**. The cookie contains only the session ID, **not** the actual session data.

4-    **Whenever** you make a **request** to the server, such as loading a new page or submitting a form, your **browser** **sends** the **session ID** cookie along with the request.

5-    The server uses this session ID to look up the corresponding session data stored on the server. It then processes the request based on this session data.

6-    After processing the request, the server sends the response back to your browser. This response may include instructions to update the session data or create new cookies for subsequent requests.

<u>Difference from cookies</u>

Unlike cookies, the session data is stored on the server side and not on the client side, the server simply sends the session ID with a cookie in order to recognize the user whenever a request is made. The server has more control since the user only has access to the session ID and not the actual session data.