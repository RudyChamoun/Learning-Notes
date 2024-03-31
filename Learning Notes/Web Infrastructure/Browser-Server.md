
## Browser - Server Interaction

When a browser sends a request to a server, such as requesting a web page, here’s how it typically works

1. **HTTP Request from the Browser:**
    - A user interacts with a web page in their browser, triggering an HTTP request. This could be clicking a link, submitting a form, or any action requiring data from the server.
2. **Routing and Endpoint Mapping:**
    - The HTTP request is received by the server. The server's routing system maps the request to a specific endpoint based on the URL. Endpoints are predefined paths (<b>routes</b>) within the application that correspond to specific functionalities. For instance, a request to `/products` would be mapped to the endpoint responsible for handling product-related data.
3. **Middleware:**
    - The request may pass through one or more middleware functions before reaching the route handler. Middleware functions can perform tasks such as authentication, logging, or preprocessing required before handling the request.
4. **Route Handler:**
    - Once past any middleware, the request reaches the appropriate route handler associated with the mapped endpoint. The route handler is responsible for processing the request and generating a response.
5. **Database Interaction:**
    - The route handler initiates communication with the database to fetch the required data. This involves constructing and executing a database query tailored to the endpoint's purpose.
6. **Response Generation:**
    - After retrieving data from the database, the route handler constructs an HTTP response containing the requested data. Additionally, the response may include status codes, headers, and other metadata necessary for the client.
7. **HTTP Response to the Browser:**
    - The HTTP response is sent back to the browser, where it's received and processed. The browser then renders the response, presenting the requested data to the user.

<u>Ex:</u> Whenever I am using a website, let’s say I clicked on the next page button wich shows me dynamic content, the way that actually works is the following : the next page click is interpreted as a request, the browser sends this request to the server using HTTP. The server receives this request, it analyses what the request is asking for (querying a database for information, processing user input, or generating HTML content dynamically based on specific conditions or parameters), in our case there is dynamic content to be displayed so the server-side scripting language (such as php) executes on the server and generates the necessary html for displaying the webpage.

All of this is sent form the server to the browser as a response using HTTP, the browser now analyses the response and it renders the webpage.

## **Cloudflare**

Cloudflare is a cloud-based platform that offers various services, one of these services is “WAF” **Web Application F**irewall. It ensures the security of the backend and provides protection against various attacks such as SQL injections…


Every request that is sent to the backend (server) from the browser goes through Cloudflare and according to a predefined set of rules and logic Cloudflare decides whether this request is safe and can reach the backend. Similar, whenever the server generates a response and wants to send it back to the browser, this response goes through Cloudflare to clear it.

Easter egg chekre


