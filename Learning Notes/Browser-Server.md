
## Browser - Server Interaction

When a browser sends a request to a server, such as requesting a web page, here’s how it typically works

1.     **Client Sends a Request**: The process begins when a user interacts with a web application, such as clicking on a link or submitting a form, which triggers the browser to send an ==HTTP== (hyper text transfer protocol) request to the server.

2.     **Server Receives the Request:** The server, upon receiving the HTTP request, determines which resource or web page the client is requesting.

3.     **Server-side Scripting Language Executes**: If the requested resource is dynamic or requires server-side processing (e.g., retrieving data from a database), the server-side scripting language comes into play. The server executes the appropriate script written in the chosen server-side language.

4.     **Data Processing and Generation**: The server-side script may perform various tasks, such as querying a database for information, processing user input, or generating HTML content dynamically based on specific conditions or parameters.

5.     **HTML Generation**: After processing the request and any necessary data, the server-side script generates HTML content dynamically. This HTML content may include text, images, forms, and other elements required to render the web page.

6.     **Response Sent to Client**: Once the HTML content is generated, the server sends an HTTP response back to the client's browser. This response typically includes the dynamically generated HTML content along with any other necessary resources, such as stylesheets, scripts, or media files.

7.     **Client Renders the Response**: Upon receiving the response, the client's browser renders the HTML content received from the server, displaying the dynamic web page to the user.

<u>Ex:</u> Whenever I am using a website, let’s say I clicked on the next page button wich shows me dynamic content, the way that actually works is the following : the next page click is interpreted as a request, the browser sends this request to the server using HTTP. The server receives this request, it analyses what the request is asking for (querying a database for information, processing user input, or generating HTML content dynamically based on specific conditions or parameters), in our case there is dynamic content to be displayed so the server-side scripting language (such as php) executes on the server and generates the necessary html for displaying the webpage.

All of this is sent form the server to the browser as a response using HTTP, the browser now analyses the response and it renders the webpage.

## **Cloudflare**

Cloudflare is a cloud-based platform that offers various services, one of these services is “WAF” **Web Application F**irewall. It ensures the security of the backend and provides protection against various attacks such as SQL injections…


Every request that is sent to the backend (server) from the browser goes through Cloudflare and according to a predefined set of rules and logic Cloudflare decides whether this request is safe and can reach the backend. Similar, whenever the server generates a response and wants to send it back to the browser, this response goes through Cloudflare to clear it.

Easter egg chekre


