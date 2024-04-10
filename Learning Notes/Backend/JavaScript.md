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
- String Interpolation : A feature in javaScript that allows us to concatenate something with a String without using the "+" operator is called **==template literals**== ==> In ES6, template literals use backticks `` ` `` and `${}` to interpolate values into a string.
	 ex : const name = "rudy";
		console.log(`Hello my name is ${name}`);

Important Operator : **typeof** ==> The `typeof` keyword returns the data type (as a string) of a value.
	ex :    let x = 3;
	     const y = "rudy";
	     console.log(typeof(x)); //number
	     console.log(typeof(y));//string
	     

### <u>Conditional Statements </u>		
- Everything is the same as Java
- Equality Operator is === instead of ==
- We can assign to a variable a value OR another one. In case the first one is false, it'll automatically assign the second value to the variable 
	- ex : let x = '';
		let z = x || 'true value'; // z is assigned 'true value'
- Ternary Operator : 
		condition? execute if true : execute if false;


### <u> Functions</u>
Function Creation Syntax :
![[Pasted image 20240404121438.png]]
Another way to declare functions :
![[Pasted image 20240404131053.png]]
### ==<u>Arrow Functions!!!</u>==
Arrow functions remove the need to type out the keyword `function` every time you need to create a function. Instead, you first include the parameters inside the `( )` and then add an arrow ==`=>`== that points to the function body surrounded in `{ }`

ex : 
const getGrade = (credits,hours)=>
	{
		/// body
	};


### <u>Arrays</u>
- In JavaScript arrays can store any data types, an array can have elements of **different types** or they can all be the same.
- Declaration of Array :
		let students = ["Rudy",32,true,"Paul"];
- Everything for arrays is the same as Java
- Additional Features : 
	- **.push()** method => adds elements to the end of the array
	- **.pop()** method => removes element at the end of the array
	- **.shift()** method => removes the first element in the array and shifts rest
	- **.unshift()** method =>adds an element to the beginning of the array
	- **.slice(i,j)** method => returns array elements from index i to j-1
	- **.indexOf(element)**=> returns the index of element in the array

### <u>Loops</u>
- Everything is the same as Java 
- for loop : for(let i =0;i<5;i++){
		}

### <u>Iterators</u>
- The ==.forEach( )== Method, there are 2 ways to use this iterator.
	- 
	 ![[Pasted image 20240404163024.png]]

	    Iterates over every element in the array and applies the specified function
	    
	- Using Narrow Function Syntax :
		groceries.forEach(item=> console.log(item));)

- The **==.map( )==** method works in a similar manner to [`.forEach()`](https://www.codecademy.com/resources/docs/javascript/arrays/forEach)— the major difference is that `.map()` ==returns a new array==.
		ex : const new_groceries = groceries.map(item=>
		{
		// do this to item and store it in new array
		})

- The **==.filter()==** method. Like .map(), .filter() ==returns a new array==. However, `.filter()` goes through every element in the array and if the element matches the boolean condition  in the callback function, it will be added to the new array.
	ex : const words = ['chair', 'music', 'pillow', 'brick', 'pen', 'door'];  
  
	const shortWords = words.filter(word => {  
		  return word.length < 6;  
	});


- The **==.findIndex()==** method. This method iterates through all the elements in the array and returns the index of the element that matches the condition we place in the callback function.
		ex : const found_idx = words.findIndex(word=>{
			return word.charAt(0)!=s})


### <u>Objects</u>
- When creating objects in JS, we assign to them certain attributes in a key **:** value pair syntax, separating each attribute with a ",".
		ex : let car = {
				type : 'Bugatti' **,**
				color : 'red',
				'year made' : 2003 
				};
				
- To access these properties we can either use :
		1.  The dot "." operator 
				ex : car.type;
				   car.color;
		
		
	2. Bracket Notation "[ ]"
			ex :   car[type];
			    car['year made'];
		
		We ==**must**== use bracket notation when accessing keys that have numbers, spaces, or special characters in them. Without bracket notation in these situations, our code would throw an error.

- Objects are mutable , meaning we can change their properties after creating them 
	- We can use the "." operator or "[ ]" notation to do that 
		ex : car.color = 'yellow'  // reassigns the color property
		   car.weight = 1000; // assigns a new weight property to car
		   delete car['year made']; // deletes this property from our object

- <b>Methods</b>
	- We can include methods in our object literals by creating ordinary, colon-separated key-value pairs. The key serves as our method’s name, while the value is an anonymous function expression.
	- ex : const vehicule = {
					drive() {
						console.log("I am driving")
						},
					crash(){
						console.log("I crashed")
						}
							};
	- To invoke these methods simply : vehicule.drive()   ; vehicule.crash();


- <b>Nested Objects </b>
	- We can have as properties to objects, other objects (for example for a ship I want to have an object that contains the color and the weight and so on )
			-ex : let ship = {
							ship_details :{
										color :'blue' ,
										weight:300 
										} ,	
							fuel : 2345 ,
							passengers : [{name : 'rudy'},{name:'paul'}]
						};
### <u>Advanced Objects</u>

- The <b>this</b> keyword 
	- Any method that is defined in an object cannot simply access the attributes of this object by calling them by name, that is why the "this" keyword is used, it references the _calling object_ which provides access to the calling object’s properties
	- ex : const car = {
					name : 'Toyota',
					advertise(){
						return "Hello "+ ==this==.name;
							}
					};
- Privacy 
	- Certain languages have privacy built-in for objects, but JavaScript does not have this feature. Rather, JavaScript developers follow naming conventions that signal to other developers how to interact with a property. One common ==convention== is to place an underscore `_` before the name of a property to mean that the property should not be altered.
	- ex : const human = {
						name : 'rudy',
						_age : 21	};
						
- Getters
	- _Getters_ are [methods](https://www.codecademy.com/resources/docs/javascript/methods) that get and return the internal properties of an object. But they can do more than just retrieve the value of a property!
	- When writing the method in the object we have to  use the **get** keyword before the function name.
	- ex : const  person = {
						firstName : 'Rudy',
						lastName : 'Chamoun',
						get fullName() {
								// code if else or hayala 
									}
						};
- Setters
	- _setter_ methods reassign values of existing properties within an object.
	- When writing the method in the object we have to  use the **set** keyword before the function name.
	- ex : const person = {
						firstName : 'rudy',
						lastName : 'chamoun',
						_age : '21',
						set age(num) {
							// code 
								  } 
					  };
	- To call it we have to do it this way : person.age = 22;

- Factory Functions
	- A factory function is a function that returns an object and can be reused to make multiple object instances. Factory functions can also have parameters allowing us to customize the object that gets returned.
	- ex : const factoryFunction = (n,a)=>{
									return {name : n,
										 age : a,
										 speak(){
												console.log('hello');
												}			
										 }
									}
-  Destructured Assignment
	- To extract and save a property for an object, we can do the following : const x = car.name;
	- A faster technique is called  Destructured Assignment : 
				const =={name_of_property}== = ==object_name==;
				ex : const{name} = car;

- Built-In Object Methods
	- Object.**keys**(name_of_object) ==> returns an array containing all the keys (properties) in "name_of_object"
	
	- Object.**entries**(name_of_object)==> will also return an array, but the array will contain more arrays that have both the key and value of the properties in an object.
	
	-  Object.**assign**(target,source)==> assigns to target all the properties of source