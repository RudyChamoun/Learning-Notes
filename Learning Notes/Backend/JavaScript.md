## <u>Intro to JavaScript</u>

- In backend development, JavaScript (often referred to as Node.js) is used to write server-side code that runs on the server rather than in the browser
- It is powered by ==Node.js==, a runtime environment that allows developers to run JavaScript on the server.
- With Node.js, we can use JavaScript to build scalable, high-performance server-side applications.

## <u>How JavaScript Interacts with the Server</u>


- **Handling HTTP Requests**: Node.js provides built-in modules like `http` or popular frameworks like ==Express.js to handle HTTP== requests and responses. Developers can define [[Routes]] and[[Middleware]] to process incoming requests and generate responses.

- **Accessing Databases**: JavaScript in the backend can interact with databases such as MongoDB, MySQL, or PostgreSQL using database drivers or ORMs (Object-Relational Mappers) like Mongoose.

- **Business Logic**: Backend JavaScript code implements the application's business logic, including data processing, authentication, authorization, and other server-side operations.

- **Responding to Clients**: After processing requests, JavaScript sends responses back to clients, typically in the form of JSON data for API endpoints or rendered HTML for web pages.

## <u>Syntax and Concepts</u>

### <u>Intro to JavaScript</u>
- Data is printed, or logged, to the console, a panel that displays messages, with ==`console.log("Hello World)`.==
- We can write single-line [comments](https://www.codecademy.com/resources/docs/javascript/comments) with `//` and multi-line comments between `/*` and `*/`.
- There are 7 fundamental [data types](https://www.codecademy.com/resources/docs/javascript/data-types) in JavaScript: [strings](https://www.codecademy.com/resources/docs/javascript/strings), numbers, Booleans, null, undefined, symbol, and object.
- Numbers are any number without quotes: `23.8879`
- Strings are characters wrapped in single or double quotes: `'Sample String'`
- The built-in arithmetic [operators](https://www.codecademy.com/resources/docs/javascript/operators) include `+`, `-`, `*`, `/`, and `%`.
- [Objects](https://www.codecademy.com/resources/docs/javascript/objects), including instances of data types, can have properties, stored information. The properties are denoted with a `.` after the name of the object, for example: `'Hello'.length`.
- Objects, including instances of data types, can have [methods](https://www.codecademy.com/resources/docs/javascript/methods) which perform actions. Methods are called by appending the object or instance with a period, the method name, and parentheses. For example: `'hello'.toUpperCase()`.
- We can access properties and methods by using the `.`, dot operator.
- Built-in objects, including `Math`, are collections of methods and properties that JavaScript provides.

### <u>Variables</u>
- We can use ***var***, ***let*** and ***const*** to declare variables
	- ex :   const name = "Hello";
		  let x = 5;

- Difference between ***let*** and ***const*** :
	- **const**(constant) : - cannot be declared without an initial value
			- cannot be reassigned
	- **let** :     - can be declared without an initial value
			- can be reassigned

### <u>Strings</u>
- Everything is the same as Java when it comes to strings (concatenation, .....)
- String Interpolation : A feature in javaScript that allows us to concatenate something with a String without using the "+" operator is called **template literals** :  ${name_of_variable}
			
	