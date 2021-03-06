<!-- cheat sheets -->

# JavaScript
**Requirments:** none  
**Syntax:**  
`<script> code within HTML file </script>`  
`<script  src="myExternalFile.js"></script>`
### Output
`document.write()` write into HTML output (good for testing)  
`window.alert()` write to alert box  
`console.log()` write to browser console (for debugging)  
`document.getElementById('id').innerHTML` access HTML elements  
**warning:** using document.write() after html document is lodaed will delete all existing HTML  
`window.print()` prints current window content

`// comment`  
`/* multi-line comment */`

### Data types
`let variable;` // same as undefined  
`let string = "Hello";`  
`let num = 10;`  
`let float = 15.371;`  
`let bool = true;`  
`let arr = [red,green,blue];`  
`let dog = { name : 'Spot', breed : 'Dalmatian' };`  
`let notDefine = undefined;`  
`let nothing = null;`  
**Undefined vs null**  
```
typeof undefined    // undefined
typeof null         // object
null == undefined   // true
null === undefined  // false
```
`const constant = 9;`  

All Datatypes have a 'valuOf()' and 'toString()' method  

`typeof "Returns data type"`  

**primative data** - simple single data value  
&ensp;string, number, boolian, undefined  
**complex data**  
&ensp;function  
&ensp;object - `typeof` returns 'object' for objects, arrays and null

**Identifiers** - contain letters, digits, underscores and dollar signs  
Start with a **letter** or **$**  

**Function** - block of code to perform a particular task
	function is executed when it is invoked
```
function name(parameter1, parameter2, parameter3) {
	// code to be executed
}
```
### Obejects
**properties** and **methods**  
properties are writen in **name:value** pairs:  
&ensp;&ensp;`let myObj = {shape:"square", size:"500", color:"white"};`  
methods are actions that can be preformed on objects  
method = function stored as a property:  
```
let person = {
	firstName: "John",
	lastName : "Doe",
	fullName : function() {
		return this.firstName + " " + this.lastName;
	}
};
```
**access property** `obj.property` or `obj["property"]`  
**access method** &ensp;`obj.method()`  

var declared with `new` creates a object

comparing objects return false: (x==y) and (x===y)

all obj have a `toString()` method

`this` keyword refers to owner

### Events
`<element event='some JavaScript'> `  
e.g. `<button onclick="document.getElementById('demo').innerHTML = Date()">The time is?</button>`  
or call a func:  `<button onclick="mytimefunc()">The time is?</button>`  
**common HTML events**  
&ensp;&ensp;`onchange`, `onclick`, `onmouseover`, `onmouseout`, `onkeydown`, `onload`  

event handlers can handle and verify, user input, user actions and browser actions

Strings
	`lenght` property
		let txt = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
		document.getElementById("demo").innerHTML = txt.length;
	escape char '\' turns special chars into string chars
String methods
	primative values vannot have properties or methods as they are not objects
	however methods and properties are available to primitive values
		as JS treats primative values as objects when execusing methods and properties
		e.g. the 'length' property returns the length of a string
	indexOf() returns the index of the first occurenct of text within a string
	JS counts positions from zero
	lastIndexOf() returns the index last occurence of text within a string (searches backwards)
	indexOf() and lastIndexOf() both:
		* return '-1' when no occurence found
		* accept second parameter for starting position for search
	search() acts exactly same as indexOf() but does not take second starting position argument, and can take powerful search values (regular expressions) which indexOf() cannot
	Extracting string parts	- three methods to extract part of sting
    slice(start, end) - returns extracted part in a new string
    substring(start, end) - same as slice() but cannot take negatives
    substr(start, length) - same as slice but second parameter species length to be extracted
    start and end values are indexes, if negative the position is counted from end of string. can have one parameter
	replacing string content
		replace('strPart','replacement') - replaces value with another (in a new sting)
			default: case sensitive, first word match
				regular expressions are written without quotes
				replace case insensitive by using a regular expression with '/i' flag (insensitive)
					replace(/strPart/i,'replacement')
				repalce all matches using a regular expression with '/g' flag (global match)
					replace(/strPart/g,'replacement')
	convert to upper and lower case
		toUpperCase() converts to upper case
		toLowerCase() converts to lower case
	concatination
		concat() joins two or more strings
	remove whitespace
		trim() removes whitespase from both sides of string
			(not supported IE8 or lower)
		for IE8 support use replace() with a regular expression:
			replace(/^[\s\uFEFF\xA0]+|[\s\uFEFF\xA0]+$/g, ''))
			use above solution to add trim function to 'string.prototype'
	extracting chars - three main methods
    charAt(position) - return char at specified index
    charCodeAt(position) returns unicode of char at specified index
    Property access[ ] - same as charAt() but uses property access
    	property access may beu npredictable
  convert string to array
  	split()
	  	split(",") // split on commas
			split(" ") // split on spaces
			split("|") // split on pipe
			split("")  // split on chars
Numbers
	JS has only one type of number; no int, short, long, float
	can use scientific notation for extra samll and large numbers 'let x= 12e5;'
	JS numbers are always 64-bit floating point, they are always stored as double precision floating point numbers
	this format stores numbers in64 bits, where faction the number is stored in bits 0-51, exponent in 52-62 and the sign in 63
	Precision
		ints are accurate up to 15 digits
		macimum number of decimals is 17 digits
	Adding numbers and strings
		JS use '+' for both addition and concatenation
			numbers are added
			strings are concatinated
		num + num = num
		str + str = str
		num + str = str
		str + num = str
	Numeric strings
		JS strings can have numeric content
		JS will try to convert string to numbers in all numeric operations
		"2" + "1" = "21" //str '+' concatinates
		"2" - "1" = 1    //num
		"2" * "1" = 2    //num
		"2" / "1" = 2    //num
	NaN - Not a Number
		JS reserved word indicating that a numder is not a legal number
		arithmetics with non-numeric strings result in NaN
		1 * "hello" = NaN
		1 * "100" = 100    // number with numeric stirng
		isNaN() - returns true if not a number
		isNaN is a gloval JS function
		NaN is a number 'typof NaN' //returns number
	Infinity - returned if number outride of largest possible number
		let myNumber = 2;
			while (myNumber != Infinity) {   // Execute until Infinity
			  myNumber = myNumber * myNumber;
			}
		division by zero generates 'Infinity'
		Infinity is a number 'typeof Infinity' //returns number
	Hexadecimal
		JS interprets numeric constants as hexadecimal if preceded by 0x
			let x = 0xFF // x will be 255
		defualt: JS display numbers as base 10 decimals
			but toString() output numbers form base 2 to base 36
			hecadecimal - base 16, deciaml - base 10, octal - 8, binary - 2
				var myNumber = 32;
				myNumber.toString(10);  // returns 32
				myNumber.toString(32);  // returns 10
				myNumber.toString(16);  // returns 20
				myNumber.toString(8);   // returns 40
				myNumber.toString(2);   // returns 100000
Number methods
	All number methods can be used on any type on numbers (literals, vars, or expressions)
	toString() returns a number as a string
	toExonential(charsRoundedAfterDecimal) returns string, with number rounded using exponential notation // parameter will not round number if no parameter
	toFixed(noOfDecimals) returns a string. with specified numder of decimals
	toPrecision() returns string, with specified number length
	valueOf() returns a number as a number // no reason to use in your code
	converting vars to numbers - 3 methods
		these methods are global JS method not number methods
		Number() - returns number, converted from argument
		parseInt() - returns integer, from parsing argument
		parseFloat() - returns float, from parsing argument

		Number(true);      // returns 1
		Number(false);     // returns 0
		Number("10");      // returns 10
		Number("10.33");   // returns 10.33
		Number("10 33");   // returns NaN if number cannot be converted
 		Number(new Date("2017-09-30")); // returns 1506729600000 - milisecs since 1.1.1970

 		parseFloat, parseInt - spaces are allowed, but only first num is returned:
			parseInt("10");         // returns 10
			parseInt("10.33");      // returns 10
			parseInt("10 20 30");   // returns 10
			parseInt("10 years");   // returns 10
			parseInt("years 10");   // returns NaN

			parseFloat("10");        // returns 10
			parseFloat("10.33");     // returns 10.33
			parseFloat("10 20 30");  // returns 10
			parseFloat("10 years");  // returns 10
			parseFloat("years 10");  // returns NaN
	Number properties
	MAX_VALUE - returns largest possible number in JS
	MIN_VALUE - returns smallest possible number in JS
	POSITIVLE_INFINITY - represents positive infinity (returned on overflow)
	NEGATIVE_INFINITY - represents negative infinity (returned on overflow)
	NaN - represtents not a number value
		number properties cannot be used on vars
		number properties belong to the JS number object wrapper called Number
		there properties can olny be accessed as Number.MAX_VALUE
			not var.MAX_VALUE, expression or value will return undefined
Arrays
	store multiple values in a single var
	values can be accessed using indexes
	creating array:
		array literal is easiet way to create JS array
			let array_name = [item1, item2, ...];
		Dont use: JS 'new' keyword also creates array
		let cars = new Array("Saab", "Volvo", "BMW"); // use array literal instead as simpler, faster and easily readable.
	access element of array
		myArray[0] // selects first element
	change array element
		myArray[0] = "changed";
 	access full array by reffering to array name
		document.getElementById("demo").innerHTML = myArray;
	arrays are objects
		but best described as arrays
		arrays use numbers to access its elements myArr[0]
		objects use names to access its members   myObj.firstMember
	array elements can be objects
		variables of different types can be in the same array
			objects, functions and arrays can all be within the same array
	array properties and methods
		built-in array properties and methods are very useful
		length - returns length of array (highest index + 1)
			myArr[0] 										//accessing first element
			myArr[myArr.length - 1]     //accessing last element
	loop through arrays
		// for loop - easiest
			var fruits, text, fLen, i;
			fruits = ["Banana", "Orange", "Apple", "Mango"];
			fLen = fruits.length;

			text = "<ul>";
			for (i = 0; i < fLen; i++) {
			  text += "<li>" + fruits[i] + "</li>";
			}
			text += "</ul>";
		// Array.foreach() function
			var fruits, text;
			fruits = ["Banana", "Orange", "Apple", "Mango"];

			text = "<ul>";
			fruits.forEach(myFunction);
			text += "</ul>";

			function myFunction(value) {
			  text += "<li>" + value + "</li>";
			}
	add array elments
		esiest way - push()
			var fruits = ["Banana", "Orange", "Apple", "Mango"];
			fruits.push("Lemon");    // adds a new element (Lemon) to fruits
		also 'length' property
			var fruits = ["Banana", "Orange", "Apple", "Mango"];
			fruits[fruits.length] = "Lemon";    // adds a new element (Lemon) to fruits
		adding elements with a very high index(not next index) causes undefined to fill between:
			var fruits = ["Banana", "Orange", "Apple", "Mango"];
			fruits[6] = "Lemon";    // adds a new element (Lemon) to fruits but adds undefined
	associative arrays  - named indexes
		JS does not support associative arrays
		JS arrays are always numbered
	array vs objects
		arr - numbered indexes
		obj - named indexes
		When to use arrys or Objects
			objects when want named elments
			arrays when want numbered elements
	Avoid new Array()
		no need to use new Array()
		can also complicate code (produces undefined when changing)
		use '[]' instead
	recognize array
		typeof - returns type object
		Array.isArray(myArray) returns true if array
			some browsers do not support this method
				solved: create your own isArrau() function
					function isArray(x) { // returns true if array
					  return x.constructor.toString().indexOf("Array") > -1;
					} // actually returns true if obj protopype contains word array
		instanceof operator returns true if an object is created by a given constructor
			var fruits = ["Banana", "Orange", "Apple", "Mango"];
			fruits instanceof Array;   // returns true
Array methods
	toString() - converts array to string of array values seperated by comma
		myArr.toString();
	join() - same as toString(), but can specify the seperator
		myArr.join(" - ")
	popping - removing last element
		pop() returns last element which is "popped out"
		myArr.pop()
	pushing - add element
		push() returns the new array length and adds new element
		myArr.push("newElement")
	shifting - same as popping, but removes first element
		shift() returns value that was "shifted out" and "shifts" all other indexes lower
			myArr.shift()
		unshift() returns the new array length and adds new element to beggining of array and "unshifts" older elements
	changing elements
		access array elements by using their index number
		length property is an easy way to append new elements to an array
	deleting elements
		delete operator deletes elments
			delete myArr[0]
		deleting elements replaces them with 'undefined'
			use shift() or pop() instead
	splicing array
		splice() add new items and returns an array of deleted items
			splice(indexNo, noOfElementsToRemove, newElements, newElem.., ...)
			myArr.splice(3, 0, "myNewElement1", "myNewElement2")
	splicing to remove elements
		can remove elements without leaving holes in array like 'delete'
		myArr.splice(0, 2) // removes first 2 item
	concatenating arrays
		concat() returns a new merged array, can take multiple arguments
			arr1.concat(arr2);
			arr1.concat(arr2, arr3);
		also take string arguments
			arr1.concat("hello")
	slicing array - cut out piece of array in a new array (original fine)
		slice() returns a new array without the sliced elements
		slice(start/ingIndex, endIndex) // second arg is optional
		arr.slice(2) // removes third element to end element
		arr.slice(2, 4) // removes third to fifth elements
	Automatic toString()
		JS automatically convertr an array to comma seperated string when a primative value is expected
			this always happens when you try to outpup an array
			both do same thing:
				var fruits = ["Banana", "Orange", "Apple", "Mango"];
				document.getElementById("demo").innerHTML = fruits;
				document.getElementById("demo").innerHTML = fruits.toString();
Sorting arrays
	sort() sorts array alphabetically
	reverse() reverse the elements in array, to sort reverse alphabet use 'sort' then 'reverse'
	numeric sort
		Default: sort() sorts values as strings
		A compare function can solve this problem:
			numArr.sort(function(a, b){return a - b});  // ascending
			numArr.sort(function(a, b){return b - a});  // descending
			a compare function should return a negative, zero, or positive value
				If result is negative a is sorted before b.
				If result is positive b is sorted before a.
				If result is 0 no changes are done with the sort order of the two values.
			the compare function compares all values within array two at a time (a, b)
				e.g. (30, 40) = (30 - 40) = -10 = negative = 30 is sorted before 40
	randomly sort array
		// example below favours some numbers over others
		numArr.sort(function(a, b){return 0.5 - Math.random()}); // not very random
		A popular method is the Fisher Yates shuffle, implemented in JS:
			var points = [40, 100, 1, 5, 25, 10];
			for (i = points.length -1; i > 0; i--) {
			  j = Math.floor(Math.random() * i)
			  k = points[i]
			  points[i] = points[j]
			  points[j] = k
			}
	highest/lowest values
		Max and Min values - no built-in feature
		however, after sorting using the highest and lowest index values
			but, sorting a whole array is inefficient for finding the highest/lowest value
		arr.sort(function(a, b){return a - b});   // sort ascending
		console.log arr[0];            //for lowest value
		console.log arr[arr.length-1]; //for highest value
		arr.sort(function(a, b){return b - a});  // sort descending
		console.log arr[0];            //for highest value
		console.log arr[arr.length-1]; //for lowest value
		re: but, sorting a whole array is inefficient for finding the highest/lowest value
		Math.max.apply can find highest number in array
			function myArrayMax(arr) {
			  return Math.max.apply(null, arr);
			} 			// Math.max.apply(null, [1, 2, 3]) is equivalent to Math.max(1, 2, 3)
		Math.min.apply can find lowest number in array
			function myArrayMin(arr) {
			  return Math.min.apply(null, arr);
			}       //Math.min.apply(null, [1, 2, 3]) is equivalent to Math.min(1, 2, 3)
	my min/max JS methods
		Fastest solution is to use a user made method
		function loops through an array comparing each value with the highest value found:
			function myArrayMax(arr) {
			  var len = arr.length;
			  var max = -Infinity;
			  while (len--) {
			    if (arr[len] > max) {
			      max = arr[len];
			    }
			  }
			  return max;
			}
		This function loops through an array comparing each value with the lowest value found:
			function myArrayMin(arr) {
			  var len = arr.length;
			  var min = Infinity;
			  while (len--) {
			    if (arr[len] < min) {
			      min = arr[len];
			    }
			  }
			  return min;
			}
	sorting object arrays
		arr.sort(function(a, b){return a.property - b.property});
		Comparing string properties is a little more complex:
			cars.sort(function(a, b){
			  var x = a.type.toLowerCase();
			  var y = b.type.toLowerCase();
			  if (x < y) {return -1;}
			  if (x > y) {return 1;}
			  return 0;
			});
Array iteration methods
	array iteration methods operate on every array item
	forEach() calls a function(a callback func)  (performed on each item)
		arr.forEach(myFunc)
	map() creates new array, calls a function (performed on each item)
		var numbers1 = [45, 4, 9, 16, 25];
		var numbers2 = numbers1.map(myFunction);

		function myFunction(value, index, array) { // can also just be value by itself
		  return value * 2;
		}
	filter() creates a new array with array elements that passes a test
		var numbers = [45, 4, 9, 16, 25];
		var over18 = numbers.filter(myFunction);

		function myFunction(value, index, array) {
		  return value > 18;
		}
	reduce() runs a function to produce a single value, from left to right in array
	reduceRight() same from right to left
		they do not reduce the original array
		var numbers1 = [45, 4, 9, 16, 25];
		var sum = numbers1.reduce(myFunction);

		function myFunction(total, value, index, array) {
		  return total + value;
		}
	every() check if all array values pass a test
		var numbers = [45, 4, 9, 16, 25];
		var allOver18 = numbers.every(myFunction);

		function myFunction(value, index, array) {
		  return value > 18;
		}
	some() check if some array values pass a test
		var numbers = [45, 4, 9, 16, 25];
		var someOver18 = numbers.some(myFunction);

		function myFunction(value, index, array) {
		  return value > 18;
		}
	indexOf() searches an array for element value and returns its position
		arr.indexOf("element", startPosition)  //returns -1 if not found
	lastIndexOf() same as indexOf() but returns position of last occurence
	find() returns the value of the first element that passes a test function
	findIndex() returns the idex of the first element that passes a test function
Dates
	JS date object - work with dates
		Default:
			* JS will use browsers time zome
			* JS displays dates in full text string format: Wed Mar 25 2015 00:00:00 GMT+0000
	Create date objects
		new Date() constructor creates date objects
			date objects are static
		4 ways
			new Date()
			new Date(year, month, day, hours, minutes, seconds, milliseconds)
			new Date(milliseconds)
			new Date(dateString)
	new Date() current date and time
	new Date(year, month, ...)  specified date and time
		JS counts months from 0 to 11
	Previous century
		one and two digit years are interpreted as 19xx
			new Date(9, 11, 24); // 1909
			new Date(26, 11, 24); // 1926
	new Date(dateString) creates a new date object from a date string
	JS stores dates as milliseconds since Jan 01, 1970 00:00:00 UTC
		1970 = zero time(milisec), 2020 = about 1586626032308 miliseconds past 1970
	new Date(milliseconds) creates new date odbject as zero time plus milliseconds
		new Date(0);  // 01 Jan 1970
		new Date(100000000000); //03 March 1973 as 100000000000 + 01 Jan 1970 = 03 March 1973
		new Date(86400000);  // 02 Jan 1970   86400000 millisec = 1 day
	Date methods
		date methods allow operations on date objects /// date objects can be manipulated with methods
		when displaying a date object in HTML, its automatically converted to strig with the toString() method
		toUTCString() converts date to UTC string (standard date display)
		toDateString() converts a date to a more readable format
Date formats
	JS date input - 3 main JS date input formats
	ISO Date - "2020-03-25" (international standard)
	Short Date "03/25/2020"
	Long Date - "Mar 25 2020" or "25 Mar 2020"
	ISO dates
		JS preferred date format is ISO (YYYY-MM-DD)
			new Date("2015-03-25"); // (YYYY-MM-DD)
			new Date("2015-03"); // (YYYY-MM) allowed
			new Date("2015"); // (YYYY) allowed
	ISO date-time - ISO dates can be written with hrs, mins, and secs (YYYY-MM-DDTHH:MM:SSZ)
		new Date("2015-03-25T12:00:00Z");
			date and time is seperated with "T"
			UTC time is defined with "Z"
				Modify time relative to UTC without "Z", but with +HH:MM or -HH:MM
		UTC = GMT
	Time zones
		getting/setting date without specifying timezone, JS will use the browsers time zone
	Warining:
		* missing zeros like "2020-3-45" may produce error
		* behaviour of "YYYY/MM/DD" is undefined, some browsers guess and some return NaN
		* behaviour of "DD-MM-YYYY" is undefined, some browsers guess and some return NaN
	Long dates - "MMM DD YYYY" or "DD MMM YYYY" or month written fully
	Date input - Parsing dates
		Date.parse() returns milliseconds between Jan 1 1970
			valid date string can use this method to convert it to millisecs
		millisecs can convert it to a date object
			let msec = Date.parse("March 21, 2012");
			let d = new Date(msec);
JS date method
	getTime() returns number of millisecs since Jan 1 1970
	getFullYear() returns year as (yyyy)
	getMonth() returns month as number 0-11
	getDate() returns day as number 1-31
	getHours() returns hour 0-23
	getMinutes() returns minute 0-59
	getSeconds() returns second 0-59
	getMilliSeconds() returns millisec 0-999
	getDay() returns weekday as number 0-6
	Date.now() returns time
	in JS first day of week = 0(sunday)
		can use array to get day as a name instead of number
			var d = new Date();
			var days = ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"];
			document.getElementById("demo").innerHTML = days[d.getDay()];
	UTC methods
	All are same as date methods but return UTC date
		getUTCDate() 	Same as getDate(), but returns the UTC date
		getUTCDay() 	Same as getDay(), but returns the UTC day
		getUTCFullYear() 	Same as getFullYear(), but returns the UTC year
		getUTCHours() 	Same as getHours(), but returns the UTC hour
		getUTCMilliseconds() 	Same as getMilliseconds(), but returns the UTC milliseconds
		getUTCMinutes() 	Same as getMinutes(), but returns the UTC minutes
		getUTCMonth() 	Same as getMonth(), but returns the UTC month
		getUTCSeconds( )Same as getSeconds(), but returns the UTC seconds
JS set date methods
	setDate() 	Set the day as a number (1-31)
	setFullYear() 	Set the year (optionally month and day)
	setHours() 	Set the hour (0-23)
	setMilliseconds() 	Set the milliseconds (0-999)
	setMinutes() 	Set the minutes (0-59)
	setMonth() 	Set the month (0-11)
	setSeconds() 	Set the seconds (0-59)
	setTime() 	Set the time (milliseconds since January 1, 1970)
Math object
	JS math object allows you to perform mathemeatical tasks on numbers
	Math.round(x) returns value rounded do nearest int
	Math.pow(x, y) returns value of x to power of y
	Math.sqrt(x) returns square root
	Math.abs(x) returns absolute (positive) value of x
	Math.ceil(x) returns value of x rounded up to nearest int
	Math.floor(x) returns value of x rounded down to nearest int
	Math.sin(x) returns sine (value between -1 and 1) of the angle x (given in radians)
	Math.cos(x) returns cosine (value between -1 and 1) of the angle x (given in radians)
		If you want to use degrees instead of radians, you have to convert degrees to radians:
		Angle in radians = Angle in degrees x PI / 180.
	Math.min() returns lowest value in list of arguments
	Math.max() returns highest value in a list of arguments
	Math.random() returns random number between 0 (inclusive), and 1 (exclusive):
	Math properties (constants)
		JS provides 8 mathematical constants that can be accessed with the math object
		Math.E        // returns Euler's number
		Math.PI       // returns PI
		Math.SQRT2    // returns the square root of 2
		Math.SQRT1_2  // returns the square root of 1/2
		Math.LN2      // returns the natural logarithm of 2
		Math.LN10     // returns the natural logarithm of 10
		Math.LOG2E    // returns base 2 logarithm of E
		Math.LOG10E   // returns base 10 logarithm of E
	Math constructor
		unlike other global objects, the math object has no constructor
		all methods and properties(constants) can be used without creating a math object first
		mathe objec methods
		abs(x) 	Returns the absolute value of x
		acos(x) 	Returns the arccosine of x, in radians
		asin(x) 	Returns the arcsine of x, in radians
		atan(x) 	Returns the arctangent of x as a numeric value between -PI/2 and PI/2 radians
		atan2(y, x) 	Returns the arctangent of the quotient of its arguments
		ceil(x) 	Returns the value of x rounded up to its nearest integer
		cos(x) 	Returns the cosine of x (x is in radians)
		exp(x) 	Returns the value of Ex
		floor(x) 	Returns the value of x rounded down to its nearest integer
		log(x) 	Returns the natural logarithm (base E) of x
		max(x, y, z, ..., n) 	Returns the number with the highest value
		min(x, y, z, ..., n) 	Returns the number with the lowest value
		pow(x, y) 	Returns the value of x to the power of y
		random() 	Returns a random number between 0 and 1
		round(x) 	Returns the value of x rounded to its nearest integer
		sin(x) 	Returns the sine of x (x is in radians)
		sqrt(x) 	Returns the square root of x
		tan(x) 	Returns the tangent of an angle
Random
	Math.random() returns a random number between 0(exclusive) and 1(inclusive)
		always returns a number lower than 1
	Random integers
		Math.random() used with Math.floor() can be used to return random integers
			Math.floor(Math.random() * 10);     // returns a random integer from 0 to 9
			Math.floor(Math.random() * 101);     // returns a random integer from 0 to 100
			Math.floor(Math.random() * 10) + 1;  // returns a random integer from 1 to 10
	Proper Random function
		the random functon as shown above in random integers always returns a number between min(included) and max(excluded)
			function getRndInteger(min, max) {
			  return Math.floor(Math.random() * (max - min) ) + min;
			}
		function with both min and max included
		function getRndInteger(min, max) {
			return Math.floor(Math.random() * (max - min + 1) ) + min;
			}
booleans
	Boolean(expression) function returns true if expression is true
 	comaparision and condition
		== equivalent
		> greater than
		< less than
	empty strings are false, non empty strings are true
	any expression is true except zero
		Boolean(0) // false
		Boolean("") // false
		Boolean(undefined) // false
		Boolean(null) // false
		Boolean(false) // false
		Boolean(NaN) // false
		Boolean(0) // false
	booleans can be Objects
		normally Js booleans are primateve values created from literals
			var x = false; // typeof x returns boolean
		But booleans can also be defined as objects with the keyword new:
			var y = new Boolean(false);// typeof y returns object
		do not create boolean objects, they slow down execution speed and coplicate code
comparison and logical operators
	used to test for 'true' or 'false'
	comparison operators - used in conditional statements to compare values
		== === != !== > < >= <=
	logical operators - used to determine the logic between variable and values
		&& || !
	conditional (ternary operator)
		JS contains a conditional operator that assigns a value to a variable based on some condition
			variablename = (condition) ? value1:value2
		comparing different datatypes
			when comparing a string with a number JS will convert the string to a number, an empty = 0, non-numeric string = NaN = false
			2 < 12 	true
			2 < "12" 	true
			2 < "John" 	false
			2 > "John" 	false
			2 == "John" 	false
			comparing string with string is done alphabetically
				"2" < "12" 	false
				"2" > "12" 	true
				"2" == "12" 	false
					to secure a proper result vars shold be conbverted to the proper type before comaparision
					age = Number(age);
					if (isNaN(age)) {
					  voteable = "Input is not a number";
					} else {
					  voteable = (age < 18) ? "Too young" : "Old enough";
					}
conditions
	 conditional statements - perfom different actons for different decisions
	Use if to specify a block of code to be executed, if a specified condition is true
	Use else to specify a block of code to be executed, if the same condition is false
	Use else if to specify a new condition to test, if the first condition is false
	Use switch to specify many alternative blocks of code to be executed
	if (condtion) {}
	elseif (condition) {}
	else (condition) {}

switch statement - select one of many code blocks to be executed
	swich () {
	  case 1:
	  break;
	  default
	}
    The switch expression is evaluated once.
    The value of the expression is compared with the values of each case.
    If there is a match, the associated block of code is executed.
	break beyword breaks out of switch bloxk, stop the execution within the block, no need to break last case as defualt
	break stops execution of next case, for cases you want same code ommit the break to execute to next case
	default specifies code to run if no match
	details
		if multiple case values match then the first case is selceted
		if no matching cases, default selected
		if no default the progran continues after switch statement
	strict comparison - switch cases use strict comparison ===
		the values/operands must be of the same type
loops
	JS supports different types of loops:
    for - loops through a block of code a number of times
    for/in - loops through the properties of an object
    for/of - loops through the values of an iterable object
    while - loops through a block of code while a specified condition is true
    do/while - also loops through a block of code while a specified condition is true
	For loop
		for (statement 1; statement 2; statement 3) {
		// code block to be executed
		}
		Statement 1 is executed (one time) before the execution of the code block.
		Statement 2 defines the condition for executing the code block.
		Statement 3 is executed (every time) after the code block has been executed.
		for (i = 0; i < 5; i++) {
		  text += "The number is " + i + "<br>";
		}
		Statement 1 sets a variable before the loop starts (var i = 0).
		Statement 2 defines the condition for the loop to run (i must be less than 5).
		Statement 3 increases a value (i++) each time the code block in the loop has been executed.
		Statement 1
			normally used to initialize the var used in loop
			not always case, statement 1 is optional
				var i = 2;
				var len = cars.length;
				var text = "";
				for (; i < len; i++) {
				text += cars[i] + "<br>";
				}
			many values can be intiated in statement 1 seperated by comma
				for (i = 0, len = cars.length, text = ""; i < len; i++) {
				  text += cars[i] + "<br>";
				}
		statment 2
			normally used to evaluate the condition of the initial variables
			not always the case, statement 2 is optional
			if statment 2 returns true the loop will start over again, if false the loop ends
			use break if ommitting statment 2, or loop will never end
		statement 3
			do anything to value of the initail var
			statement 3 is optional, if ommited you can increment values within the loop
			statement 3 can do positive/negative incerement or anythign else
		for/in - loops through the properties of an object:
			var person = {fname:"John", lname:"Doe", age:25};
			var text = "";
			var x;
			for (x in person) {
			  text += person[x];
			}
		for/of - loops through the values of an iterable objects
			loop over data structors that are iterable like arrays strings maps nodelists and more
			for (variable of iterable) {
			  // code block to be executed
			}
			variable - For every iteration the value of the next property is assigned to the variable. Variable can be declared with const, let, or var.
			iterable - An object that has iterable properties.
			looping an array
				var cars = ['BMW', 'Volvo', 'Mini'];
				var x;
				for (x of cars) {
				  document.write(x + "<br >");
				}
			looping over a sting
				var txt = 'JavaScript';
				var x;

				for (x of txt) {
				  document.write(x + "<br >");
				}
While loops
	loops through code as long as condition is true
	the loop will never end unless the condition becomes false, so make sure increment/decrement or other happens.
	while (condition) {
	// code block to be executed
	}
	do while loops
		will execute code onece before checking if the condition is true, then will repeat as long as condition is true
		do {
		// code block to be executed
		}
		while (condition);
	comparing for and while
		the while loop is the same as the for loop with statemnt 1 and statement 3 omitted
Break and continue
	break statement "jumps out" of a loop.
	continue statement "jumps over" one iteration in the loop
	//break e.g.
	for (i = 0; i < 10; i++) {
		if (i === 3) { break; }
		text += "The number is " + i + "<br>";
	}
	// continue .g.
		for (i = 0; i < 10; i++) {
			if (i === 3) { continue; }
			text += "The number is " + i + "<br>";
		}
	JS lables
		label JS statements by preceding the statemnt iwth a lable name and colon
			```
			label:
			statements
			```
		break and continue statements are the only JS statments that can jump out a code block
		break labelname;
		continue labelname;
		continue statement with/without label rference only skips one loop interation
		break statment with label reference only jump out of a for/switch statment
			but with label reference the break statement can be used to jump out of any code block
			var cars = ["BMW", "Volvo", "Saab", "Ford"];
			list: {
			text += cars[0] + "<br>";
			text += cars[1] + "<br>";
			break list;
			text += cars[2] + "<br>";
			text += cars[3] + "<br>";
			}
		A code block is between '{' and '}'
JS type conversion
	Number() converts to number
	String() converts to string
	Boolean() converts to boolean
	JS Data types
	in JS 5 data types that can contain values
	string
	number
	boolean
	object
	function
 	6 types of objects:
	Object
	Date
	Array
	String
	Number
	Boolean
	And 2 data types that cannot contain values:
	null
	undefined
	typeof "John"                 // Returns "string"
	typeof 3.14                   // Returns "number"
	typeof NaN                    // Returns "number"
	typeof false                  // Returns "boolean"
	typeof [1,2,3,4]              // Returns "object"
	typeof {name:'John', age:34}  // Returns "object"
	typeof new Date()             // Returns "object"
	typeof function () {}         // Returns "function"
	typeof myCar                  // Returns "undefined" *
	typeof null                   // Returns "object"
		NaN is numbers
		array is object
		date is objects
		null is object
		undefined and var not assigned value is undefined
		typeof cannot tell you if the data type is date of array as returns obleict
	the data type of typeof
		typeof operator is not a variable, its an operator, operators are not data Types
		but typeof operator always returns a string (containg the type of the operand)
	constructor property
		constructor returns the constructor functoin for all JS Variables
		"John".constructor                // Returns function String()  {[native code]}
		(3.14).constructor                // Returns function Number()  {[native code]}
		false.constructor                 // Returns function Boolean() {[native code]}
		[1,2,3,4].constructor             // Returns function Array()   {[native code]}
		{name:'John',age:34}.constructor  // Returns function Object()  {[native code]}
		new Date().constructor            // Returns function Date()    {[native code]}
		function () {}.constructor        // Returns function Function(){[native code]}
		use constructor property to find out if oblect is an array
			function isArray(myArray) {
				return myArray.constructor.toString().indexOf("Array") > -1;
			}
			or simpler cbeeck if the object is an array function
				function isArray(myArray) {
					return myArray.constructor === Array;
				}
		use constructor property to find out if oblect is an array
			function isDate(myDate) {
			  return myDate.constructor.toString().indexOf("Date") > -1;
			}
			or simpler cbeeck if the object is an array function
				function isDate(myDate) {
					return myDate.constructor === Date;
				}
JS type conversion
	JS vars can be converted to a new var and another data types:
		* use of JS function
		* automatically by JS
	converting numbers to strings
		global method String() converts to string
			can be used on any type onf numbers, literals, vars or expressions
			String(x)         // returns a string from a number variable x
			String(123)       // returns a string from a number literal 123
			String(100 + 23)  // returns a string from a number from an expression
		the number method toString() does the same
			x.toString()
			(123).toString()
			(100 + 23).toString()
			toExponential() 	Returns a string, with a number rounded and written using exponential notation.
			toFixed() 	Returns a string, with a number rounded and written with a specified number of decimals.
			toPrecision() 	Returns a string, with a number written with a specified length
	convreting booleans to Strings
		String() convert booleans to Strings
		String(false)      // returns "false"
		String(true)       // returns "true"
		toString() does Same
			false.toString()   // returns "false"
			true.toString()    // returns "true"
		dates to string are the same: String() toString()
		other methods include all get methods for dates like getDate() and getMinutes()
	Converting strings to numbers
		number() can convert strings to numbers
			empty strings return 0
			number strings convert to numbers
			other returns NaN
		other methods include parseFloat() and parseInt()
	Unary + operator - used to convert a cariable to a number
		var y = "5";      // y is a string
		var x = + y;      // x is a number
		if var cannot be converted the value = NaN
			var y = "John";   // y is a string
			var x = + y;      // x is a number (NaN)
	convreting booleans to numbers
		Number() van conbert booleans to numbers
		Number(false)     // returns 0
		Number(true)      // returns 1
	converting dates to numbers
		Number() can convert dates to numbers
			d = new Date();
			Number(d)          // returns 1404568027739
		getTime() does Same
	Automatic type conversion
		JS will try to convert values:
		5 + null    // returns 5         because null is converted to 0
		"5" + null  // returns "5null"   because null is converted to "null"
		"5" + 2     // returns "52"      because 2 is converted to "2"
		"5" - 2     // returns 3         because "5" is converted to 5
		"5" * "2"   // returns 10        because "5" and "2" are converted to 5 and 2
	Automatic string conversion
		JS automatically calls the toString() function when you outpup an object or var
			document.getElementById("demo").innerHTML = myVar;
			// if myVar = {name:"Fjohn"}  // toString converts to "[object Object]"
			// if myVar = [1,2,3,4]       // toString converts to "1,2,3,4"
			// if myVar = new Date()      // toString converts to "Fri Jul 18 2014 09:08:55 GMT+0200"
			// Numbers and booleans are also converted, but this is not very visible:
			// if myVar = 123             // toString converts to "123"
			// if myVar = true            // toString converts to "true"
			// if myVar = false           // toString converts to "false"
JS Bitwise operations
	& 	AND 											Sets each bit to 1 if both bits are 1
	| 	OR 												Sets each bit to 1 if one of two bits is 1
	^ 	XOR 											Sets each bit to 1 if only one of two bits is 1
	~ 	NOT											 	Inverts all the bits
	<< 	Zero fill left shift		 	Shifts left by pushing zeros in from the right and let the leftmost bits fall off
	>> 	Signed right shift 				Shifts right by pushing copies of the leftmost bit in from the left, and let the rightmost bits fall off
	>>> 	Zero fill right shift 	Shifts right by pushing zeros in from the left, and let the rightmost bits fall off
	JS use 32 bitwise operands
		JS stores numbers as 64 bit floating toinp numbers
		before a bitwise operation is performed JS converts numbers to 32 bit signed integers
		after a bitwise operatino is performed the result is converted back to 64 bits JS numbers
	Bitwise AND
		bitwise AND returns 1 if both bits are 1
			e.g.  one bit
							operation 		result
				  		0 & 0					0
							0 & 1					0
							1 & 0					0
							1 & 1					1
						4 bits
							1111 & 0000		0000
							1111 & 0001		0001
							1111 & 0010		0010
							1111 & 0100		0100
	bitwise OR
		bitwise OR returns 1 if one of the bits are 1
		e.g.  one bit
						operation 		result
						0 | 0					0
						0 | 1					1
						1 | 0					1
						1 | 1					1
					4 bits
					1111 | 0000			1111
					1111 | 0001			1111
					1111 | 0010			1111
					1111 | 0100			1111
	bitwise XOR
		bitwise XOR returns 1 if the bits are different
		e.g.  one bit
						operation 		result
						0 ^ 0					0
						0 ^ 1					1
						1 ^ 0					1
						1 ^ 1					0
					4 bits
					1111 ^ 0000			1111
					1111 ^ 0001			1110
					1111 ^ 0010			1101
					1111 ^ 0100			1011
	bitwise AND (&)
		returns 1 oniy if both bits are 1
	bitwise OR (|)
		returns 1 if one of the bits are 1
	bitwise XOR (^)
		returns 1 if bits are different
	bitwise not (~)
	(zero fill) bitwise left shift (<<)
		This is a zero fill left shift. One or more zero bits are pushed in from the right, and the leftmost bits fall off
	(sign preserving) bitwise right shift(>>)
		This is a sign preserving right shift. Copies of the leftmost bit are pushed in from the left, and the rightmost bits fall off
	(zero fill) bitwise right shift (>>>)
		This is a zero fill right shift. One or more zero bits are pushed in from the left, and the rightmost bits fall off
	Binary numbers
		stored in two's complement formats
		therefore negative numbes is the bitwise NOT of the number plus 1
			binary represtnation 								decimal
			00000000000000000000000000000101		5
			11111111111111111111111111111011		-5
			00000000000000000000000000000110		6
			11111111111111111111111111111010		-6
			00000000000000000000000000101000		40
			11111111111111111111111111011000		-40
	converting decimal to binary
	function dec2bin(dec){
		return (dec >>> 0).toString(2);
	}
	converting binary to decimal
	function bin2dec(bin){
	  return parseInt(bin, 2).toString(10);
	}
Regular expressions
	sequence of chars that forms a search pattern
	the search pattern can be used for text search and text replace operations
	search pattern can be used to describle what seaching for
	regular expression can be single char or a more complicated pattern
	syn: /pattern/modifiers;
		let patt = /hello/i;
		/hello/i  is a regular expression.
		hello  is a pattern (to be used in a search).
		i  is a modifier (modifies the search to be case-insensitive)..
	using string methods
		inJS regular expressions normally used with two strign methods search() and replace()
		search() uses an expsression to search for a match and returns the position of the matches
		replace() returns a modified string where the pattern is replaced
	using string search() with a string
		var str = "Visit me!";
		var n = str.search("me");
	using string search() with a regular expression
		var str = "Visit me";
		var n = str.search(/me/i);
	using string replace() with a string
		var str = "Visit Microsoft!";
		var res = str.replace("Microsoft", "me");
	using string replace() with a regular expression
		var str = "Visit Microsoft!";
		var res = str.replace(/microsoft/i, "me");
	Regular expression arguments (instead of string arguments) can be used in the methods above.
	Regular expressions can make your search much more powerful (case insensitive for example).
	Regular expression modifiers
	i case insensitive, g tloabal match m perform multiline matching
	Regular expression patterns
	[abc] 	Find any of the characters between the brackets
	[0-9] 	Find any of the digits between the brackets
	(x|y) 	Find any of the alternatives separated with |

	Metacharacters are characters with a special meaning:
	Metacharacter 	Description
	\d 	Find a digit
	\s 	Find a whitespace character
	\b 	Find a match at the beginning of a word like this: \bWORD, or at the end of a word like this: WORD\b

	\uxxxx 	Find the Unicode character specified by the hexadecimal number xxxx

	Quantifiers define quantities:
	Quantifier 	Description
	n+ 	Matches any string that contains at least one n
	n* 	Matches any string that contains zero or more occurrences of n
	n? 	Matches any string that contains zero or one occurrences of n
	using the RegExp object
		in Js the regExp object is a regular expression object with predefined properties and methods
	using test()
		test() method is a RegExp expression method
			searches for a string for a pattern and returns true or false depending on result
			// search for 'e'
			var patt = /e/;
			patt.test("The best things in life are free!"); // since e is there the output is true
				can be shortend to one line:
					/e/.test("The best things in life are free!");
	using exec()
	 exec() is a RegExp expression method
	 	It searches a string for a specified pattern, and returns the found text as an object.
		if no match it returns null
			// search for 'e'
			/e/.exec("The best things in life are free!");
Errors - throw and try to catch
	try statement lets you test a block of code for errors.
	catch statement lets you handle the error.
	throw statement lets you create custom errors.
	finally statement lets you execute code, after try and catch, regardless of the result
	errors can happen
		when executing JS, errors can occur
		errors can be made by programmer, due to wrong input and other unforseeable things
	JS try and catch
		The try statement allows you to define a block of code to be tested for errors while it is being executed.
		The catch statement allows you to define a block of code to be executed, if an error occurs in the try block.
		The JavaScript statements try and catch come in pairs:
			try {
				Block of code to try
			}
			catch(err) {
				Block of code to handle errors
			}
	JS throws Errors
		when errors occur JS normally stops and generated an error message
		this is known as JS /bthrowing an exception/b
			JS will create a error object with two properties name and message
	Throw statements
		throw - create custom Errors
			technically you can /bthrow an exception/b
				the exception can be a JS 'string', 'Number', 'Boolean' or 'Object':
					throw "Too big";    // throw a text
					throw 500;          // throw a number
		if use throw' with try' and c'atch'  you can control program flow and generate custom error messages
	input validation example
		This example examines input. If the value is wrong, an exception (err) is thrown.
		The exception (err) is caught by the catch statement and a custom error message is displayed:
			<body>
				<p>Please input a number between 5 and 10:</p>
				<input id="demo" type="text">
				<button type="button" onclick="myFunction()">Test Input</button>
				<p id="p01"></p>
				<script>
				function myFunction() {
				  var message, x;
				  message = document.getElementById("p01");
				  message.innerHTML = "";
				  x = document.getElementById("demo").value;
				  try {
				    if(x == "") throw "empty";
				    if(isNaN(x)) throw "not a number";
				    x = Number(x);
				    if(x < 5) throw "too low";
				    if(x > 10) throw "too high";
				  }
				  catch(err) {
				    message.innerHTML = "Input is " + err;
				  }
				}
				</script>
			</body>
	HTML validation
		code above is an example
		modern browsers oftenlly use a combination of JS built-in HTML validation, using predefined validation rules defined in HTML attriblutes:
			<input id="demo" type="number" min="5" max="10" step="1">
	the finally statement
		finally statement lets you execute code, after try and catch, regardless of the result
			syn:
				try {
				  Block of code to try
				}
				catch(err) {
				  Block of code to handle errors
				}
				finally {
				  Block of code to be executed regardless of the try / catch result
				}
			e.g. function myFunction() {
					  var message, x;
					  message = document.getElementById("p01");
					  message.innerHTML = "";
					  x = document.getElementById("demo").value;
					  try {
					    if(x == "") throw "is empty";
					    if(isNaN(x)) throw "is not a number";
					    x = Number(x);
					    if(x > 10) throw "is too high";
					    if(x < 5) throw "is too low";
					  }
					  catch(err) {
					    message.innerHTML = "Error: " + err + ".";
					  }
					  finally {
					    document.getElementById("demo").value = "";
					  }
					}
	error object
		JS has built in error object that probides error information when an error occurs
		the error object probieds two usefl properteis: name and messages
			name sets or returns an error named
			message sets or returns an error message (string)
		error name values - six differnt values retruned by the name property:
			EvalError	An error has occurred in the eval() function
			RangeError	A number "out of range" has occurred
			ReferenceError	An illegal reference has occurred
			SyntaxError	A syntax error has occurred
			TypeError	A type error has occurred
			URIError	An error in encodeURI() has occurred
		EvalError dont use as is not used in newer versions. use SyntaxError instead
			do not use as is old
			use SyntaxError instead
		RangeError is thrown if you use a number that is outside the range of legal values.
			For example: You cannot set the number of significant digits of a number to 500.
			var num = 1;
				try {
				  num.toPrecision(500);   // A number cannot have 500 significant digits
			}
				catch(err) {
				  document.getElementById("demo").innerHTML = err.name;
			}
		ReferenceError is thrown if you use (reference) a variable that has not been declared:
			var x;
			try {
			  x = y + 1;   // y cannot be referenced (used)
			}
			catch(err) {
			  document.getElementById("demo").innerHTML = err.name;
			}
		SyntaxError is thrown if you try to evaluate code with a syntax error.
		 	try {
		  	eval("alert('Hello)");   // Missing ' will produce an error
		 	}
		 	catch(err) {
		  	document.getElementById("demo").innerHTML = err.name;
		 	}
		TypeError is thrown if you use a value that is outside the range of expected types
			var num = 1;
			try {
			  num.toUpperCase();   // You cannot convert a number to upper case
			}
			catch(err) {
			  document.getElementById("demo").innerHTML = err.name;
			}
		URIError (Uniform Resource Identifier) is thrown if you use illegal characters in a URI function:
			try {
			  decodeURI("%%%");   // You cannot URI decode percent signs
			}
			catch(err) {
			  document.getElementById("demo").innerHTML = err.name;
			}
Scope - 2 types local and global
	function scope, each function creates a new Scope
	scope determines accessiblity of Variables
	local Scope
		defined within function beconme local to function
	global Scope
		decalred outside function is glocal and all scripts and functions on a web page can access it
	Variables
		objects and functions are also variables
		scope can determine the accessibility of these
	automatically gloval
		assingnineg a value to var that isnt becalred it will automatically be blobal
		myFunction();
		// code here can use carName
		function myFunction() {
			carName = "Volvo";
		}
	strict mode
		all modern browsers support JS in strict mode
		undeclared vars are not automatically global in strict mode
	global vars in html
		With JavaScript, the global scope is the complete JavaScript environment.
		In HTML, the global scope is the window object. All global variables belong to the window object
			var carName = "Volvo";
			// code here can use window.carName
	Warining
		dont create global vars unless intended
		global vars or functions can overite window vars or functions
		 any function including the window oblect can oberwrite your global cars and functions
	variable lifetime
		start - when var decalared
		end - local vars deleted when function is completed
		end - global vars deleted when you close the browser Window
	function arguments - (parametres) work as local vars within functions
JS hoisting - best practice is to declare and initialize vars at top of scopes and don't hoist
JS hoisting - hosting is JS's default behavior of moving declarations to the top
	JS declarations are hoised
		variable can be declared after it has been used aka variable can be used before it has been decalared
			x = 5; // Assign 5 to x
			elem = document.getElementById("demo"); // Find an element
			elem.innerHTML = x;                     // Display x in the element
			var x; // Declare x
		hoisting is JS default behaviour of moving all adeclarations to the top of the current scope(script of current function)
	let and const keywords
		vars and constants decalred with let or const are not hoisted
	JS initilixations are not hoisted
		JS only hoists declarations not initilizations
			var x = 5; // Initialize x
			elem = document.getElementById("demo"); // Find an element
			elem.innerHTML = x + " " + y;           // Display x and y is undefined
			var y = 7; // Initialize y
		y is undefiend as only the declaration not the initilization =7 is hoisted
		because y is declared before used y is undefined
		this is the same as
			var x = 5; // Initialize x
			var y;     // Declare y
			elem = document.getElementById("demo"); // Find an element
			elem.innerHTML = x + " " + y;           // Display x and y
			y = 7;    // Assign 7 to y
		hoisting is not used often or at all as can cuase errors
			this is due to debs not understanding, therefore causing bugs
			therefore always declare vars at beginning of scopes
Strict mode
	'"use strict";' Defines that JavaScript code should be executed in "strict mode"
	The "use strict" Directive
		it is not a statement but a literal expression
		indicated that code should be executed in strict mode
		strict mode - cannot use undeclared variables
	helps write cleaner code by prevweneting undeclared variables
	declaring strict mode
		strict mode decalred by adding "use strict"; to the beginning of a script or a function.
		Declared at the beginning of a script, it has global scope, (so all code in the script will execute in stxit mode)
		Declared inside a function, it has local scope (only the code inside the function is in strict mode):
	why strict mode?
		esier to write secure JS
		changes previous bad syntax into real Errors
		In strict mode, any assignment to a non-writable property, a getter-only property, a non-existing property, a non-existing variable, or a non-existing object, will throw an error.
	strict mode rules / not allowed in strict mode
		using variables without declaring
		deleting an var/obj is not allowed
		deleting functions are not allowed
		duplicating a parameter name is not allowed
		octal numeral literals are not allowed
		octal escape chars are not allowed
		writing to a read only property or get only property is not allowed
		deleting an undeletable property is not allowed
		'eval' cannot be used as variable name
		'arguments' cannot be used as var name
		'with' statment is not allowed
		eval() is not allowed to create vars in the scope from which it was called for security reasons
		'this' keyword in functions behaves differently in strict mode.
		'this'  keyword refers to the object that called the function.
		If the object is not specified, functions in strict mode will return undefined and functions in normal mode will return the global object (window):
	Future proof
		keywords reserved for suture JS versions can not be used as var name in strict mode:
		  * implements
		  * interface
		  * let
		  * package
		  * private
		  * protected
		  * public
		  * static
		  * yield
this keyword
	this refers to the object it belongs to
	It has different values depending on where it is used:
    In a method, this refers to the owner object.
    Alone, this refers to the global object.
    In a function, this refers to the global object.
    In a function, in strict mode, this is undefined.
    In an event, this refers to the element that received the event.
    Methods like call(), and apply() can refer this to any object.
let
	can use block scope, variables (and constants) in JavaScript.
	var with let can have block scope
	{
		let x = 2;
	}
	// x can NOT be used here
	use let as it is better
	In HTML, the global scope is the window object.
		Global variables defined with the let keyword do not belong to the window object
	Variables defined with let are not hoisted to the topUsing a let variable before it is declared will result in a ReferenceError
const
	must be assigned when declared
	cannot be reassigned
	declaring a variable with const is similar to let when it comes to Block Scope.
	not real constants
		const does not define a constant value, it defines a constant reference to a value
		therefore, we cannot chage the constant primitive values but we can chgne the properties of constant objects
Arrow functions -new ES6
	allow us to write shorter function syntax:
		hello = () => {
			return "Hello World!";
		}
		instead of older:
			hello = function() {
				return "Hello World!";
			}
	can make it even shorter of func has only one statment and retruns a value
		hello = () => "Hello World!";  // semove brackets and retrun keyword
		parameters go inside '()'
			hello = (val) => "Hello " + val;
				can make even shorter if only one parameter skip the '()'
					hello = val => "Hello " + val;
	'this' in arrow functions
		there is no binding of 'this' in arrow functions
		In regular functions the this keyword represented the object that called the function, which could be the window, the document, a button or whatever.
		With arrow functions the this keyword always represents the object that defined the arrow function.
		Let us take a look at two examples to understand the difference.
		Both examples call a method twice, first when the page loads, and once again when the user clicks a button.
		The first example uses a regular function, and the second example uses an arrow function.
		The result shows that the first example returns two different objects (window and button), and the second example returns the window object twice, because the window object is the "owner" of the function.
classes - new ES6
	class is a type of function, but we use 'class' keyword and properties are assigned inside a constructor() method
	class definition
		use'class' to create a class, and always add the constructor() method
			as the constructor method is called each time the class object is initialized
			class Car {
			  constructor(brand) {
			    this.carname = brand;
			  }
			}
			myObjcar = new Car("Ford");
	methods
	The constructor method is special, it is where you initialize properties, it is called automatically when a class is initiated, and it has to have the exact name "constructor", in fact, if you do not have a constructor method, JavaScript will add an invisible and empty constructor method.
	You are also free to make your own methods, the syntax should be familiar:
		class Car {
		  constructor(brand) {
		    this.carname = brand;
		  }
		  present() {
		    return "I have a " + this.carname;
		  }
		}
		mycar = new Car("Ford");
		document.getElementById("demo").innerHTML = mycar.present();
	Static Methods
		Static methods are defined on the class itself, and not on the prototype.
		That means you cannot call a static method on the object (mycar), but on the class (Car):
		class Car {
		  constructor(brand) {
		    this.carname = brand;
		  }
		  static hello() {
		    return "Hello!!";
		  }
		}
		mycar = new Car("Ford");
		//Call 'hello()' on the class Car:
		document.getElementById("demo").innerHTML = Car.hello();
		//and NOT on the 'mycar' object:
		//document.getElementById("demo").innerHTML = mycar.hello();
		//this would raise an error.
	Inheritance
		To create a class inheritance, use the extends keyword.
		A class created with a class inheritance inherits all the methods from another class:
		Example
		Create a class named "Model" which will inherit the methods from the "Car" class:
		class Car {
		  constructor(brand) {
		    this.carname = brand;
		  }
		  present() {
		    return 'I have a ' + this.carname;
		  }
		}
		class Model extends Car {
		  constructor(brand, mod) {
		    super(brand);
		    this.model = mod;
		  }
		  show() {
		    return this.present() + ', it is a ' + this.model;
		  }
		}
		mycar = new Model("Ford", "Mustang");
		document.getElementById("demo").innerHTML = mycar.show();
		The super() method refers to the parent class.
		By calling the super() method in the constructor method, we call the parent's constructor method and gets access to the parent's properties and methods.
		Inheritance is useful for code reusability: reuse properties and methods of an existing class when you create a new class.
	Getters and Setters
		Classes also allows you to use getters and setters.
		It can be smart to use getters and setters for your properties, especially if you want to do something special with the value before returning them, or before you set them.
		To add getters and setters in the class, use the get and set keywords.
		Example
		Create a getter and a setter for the "carname" property:
		class Car {
		  constructor(brand) {
		    this.carname = brand;
		  }
		  get cnam() {
		    return this.carname;
		  }
		  set cnam(x) {
		    this.carname = x;
		  }
		}
		mycar = new Car("Ford");
		document.getElementById("demo").innerHTML = mycar.cnam;
		Note: even if the getter is a method, you do not use parentheses when you want to get the property value.
		The name of the getter/setter method cannot be the same as the name of the property, in this case carname.
		Many programmers use an underscore character _ before the property name to separate the getter/setter from the actual property:
		Example
		You can use the underscore character to separate the getter/setter from the actual property:
		class Car {
		  constructor(brand) {
		    this._carname = brand;
		  }
		  get carname() {
		    return this._carname;
		  }
		  set carname(x) {
		    this._carname = x;
		  }
		}
		mycar = new Car("Ford");
		document.getElementById("demo").innerHTML = mycar.carname;
		To use a setter, use the same syntax as when you set a property value, without parentheses:
		Example
		Use a setter to change the carname to "Volvo":
		class Car {
		  constructor(brand) {
		    this._carname = brand;
		  }
		  get carname() {
		    return this._carname;
		  }
		  set carname(x) {
		    this._carname = x;
		  }
		}
		mycar = new Car("Ford");
		mycar.carname = "Volvo";
		document.getElementById("demo").innerHTML = mycar.carname;
	Hoisting
		Unlike functions, and other JavaScript declarations, class declarations are not hoisted.
		That means that you must declare a class before you can use it:
		Example
		//You cannot use the class yet.
		//mycar = new Car("Ford")
		//This would raise an error.

		class Car {
		  constructor(brand) {
		    this.carname = brand;
		  }
		}
		//Now you can use the class:
		mycar = new Car("Ford")
		Note: For other declarations, like functions, you will NOT get an error when you try to use it before it is declared, because the default behavior of JavaScript declarations are hoisting (moving the declaration to the top).
		"use strict"
		The syntax in classes must be written in "strict mode".
		You will get an error if you do not follow the "strict mode" rules.
		Example
		In "strict mode" you will get an error if you use a variable without declaring it:
		class Car {
		  constructor(brand) {
		    i = 0;
		    this.carname = brand;
		  }
		}
debugging
	errors can happen
	code debugging
		code can have syntax errors or logical errors
		can be difficult to diagnose
		no error messages or indications
		debugging - searching and fixing errors
		debugging - proccess of testing, finding and reducing bugs
	JS debuggers
		modern browsers have buit in JS debuggers
		Built-in debuggers can be turned on and off, forcing errors to be reported to the user.
		With a debugger, you can also set breakpoints (places where code execution can be stopped), and examine variables while the code is executing.
		Normally, otherwise follow the steps at the bottom of this page, you activate debugging in your browser with the F12 key, and select "Console" in the debugger menu.
	console.log() Method
		console.log() to display JavaScript values in the debugger window
	setting breakpoints
		In the debugger window, you can set breakpoints in the JavaScript code.
		At each breakpoint, JavaScript will stop executing, and let you examine JavaScript values.
		After examining values, you can resume the execution of code (typically with a play button).
			var x = 15 * 5;
			debugger;
			document.getElementById("demo").innerHTML = x;
	Major Browsers' Debugging Tools
		Normally, you activate debugging in your browser with F12, and select "Console" in the debugger menu.
		Otherwise follow these steps:
		Chrome
		    Open the browser.
		    From the menu, select "More tools".
		    From tools, choose "Developer tools".
		    Finally, select Console.
		Firefox
		    Open the browser.
		    From the menu, select "Web Developer".
		    Finally, select "Web Console".
		Edge
		    Open the browser.
		    From the menu, select "Developer Tools".
		    Finally, select "Console".
		Opera
		    Open the browser.
		    From the menu, select "Developer".
		    From "Developer", select "Developer tools".
		    Finally, select "Console".
		Safari
		    Go to Safari, Preferences, Advanced in the main menu.
		    Check "Enable Show Develop menu in menu bar".
		    When the new option "Develop" appears in the menu:
		    Choose "Show Error Console".
Best practices
	avoid global vars, 'new', '==' and 'eval()'
	avoid global vars
	Minimize the use of global variables.
	This includes all data types, objects, and functions.
	Global variables and functions can be overwritten by other scripts.
	Use local variables instead, and learn how to use closures.
	Always Declare Local Variables
	All variables used in a function should be declared as local variables.

	Local variables must be declared with the var keyword or the let keyword, otherwise they will become global variables.

	Strict mode does not allow undeclared variables.
	Declarations on Top

	It is a good coding practice to put all declarations at the top of each script or function.

	This will:

	    Give cleaner code
	    Provide a single place to look for local variables
	    Make it easier to avoid unwanted (implied) global variables
	    Reduce the possibility of unwanted re-declarations

	// Declare at the beginning
	var firstName, lastName, price, discount, fullPrice;

	// Use later
	firstName = "John";
	lastName = "Doe";

	price = 19.90;
	discount = 0.10;

	fullPrice = price * 100 / discount;

	This also goes for loop variables:
	// Declare at the beginning
	var i;

	// Use later
	for (i = 0; i < 5; i++) {

	By default, JavaScript moves all declarations to the top (JavaScript Hoisting).
	Initialize Variables

	It is a good coding practice to initialize variables when you declare them.

	This will:

	    Give cleaner code
	    Provide a single place to initialize variables
	    Avoid undefined values

	// Declare and initiate at the beginning
	var firstName = "",
	lastName = "",
	price = 0,
	discount = 0,
	fullPrice = 0,
	myArray = [],
	myObject = {};

	Initializing variables provides an idea of the intended use (and intended data type).
	Never Declare Number, String, or Boolean Objects

	Always treat numbers, strings, or booleans as primitive values. Not as objects.

	Declaring these types as objects, slows down execution speed, and produces nasty side effects:
	Example
	var x = "John";
	var y = new String("John");
	(x === y) // is false because x is a string and y is an object.

	Or even worse:
	Example
	var x = new String("John");
	var y = new String("John");
	(x == y) // is false because you cannot compare objects.
	Don't Use new Object()

	    Use {} instead of new Object()
	    Use "" instead of new String()
	    Use 0 instead of new Number()
	    Use false instead of new Boolean()
	    Use [] instead of new Array()
	    Use /()/ instead of new RegExp()
	    Use function (){} instead of new Function()

	Example
	var x1 = {};           // new object
	var x2 = "";           // new primitive string
	var x3 = 0;            // new primitive number
	var x4 = false;        // new primitive boolean
	var x5 = [];           // new array object
	var x6 = /()/;         // new regexp object
	var x7 = function(){}; // new function object
	Beware of Automatic Type Conversions

	Beware that numbers can accidentally be converted to strings or NaN (Not a Number).

	JavaScript is loosely typed. A variable can contain different data types, and a variable can change its data type:
	Example
	var x = "Hello";     // typeof x is a string
	x = 5;               // changes typeof x to a number

	When doing mathematical operations, JavaScript can convert numbers to strings:
	Example
	var x = 5 + 7;       // x.valueOf() is 12,  typeof x is a number
	var x = 5 + "7";     // x.valueOf() is 57,  typeof x is a string
	var x = "5" + 7;     // x.valueOf() is 57,  typeof x is a string
	var x = 5 - 7;       // x.valueOf() is -2,  typeof x is a number
	var x = 5 - "7";     // x.valueOf() is -2,  typeof x is a number
	var x = "5" - 7;     // x.valueOf() is -2,  typeof x is a number
	var x = 5 - "x";     // x.valueOf() is NaN, typeof x is a number

	Subtracting a string from a string, does not generate an error but returns NaN (Not a Number):
	Example
	"Hello" - "Dolly"    // returns NaN
	Use === Comparison

	The == comparison operator always converts (to matching types) before comparison.

	The === operator forces comparison of values and type:
	Example
	0 == "";        // true
	1 == "1";       // true
	1 == true;      // true

	0 === "";       // false
	1 === "1";      // false
	1 === true;     // false
	Use Parameter Defaults

	If a function is called with a missing argument, the value of the missing argument is set to undefined.

	Undefined values can break your code. It is a good habit to assign default values to arguments.
	Example
	function myFunction(x, y) {
	  if (y === undefined) {
	    y = 0;
	  }
	}

	ECMAScript 2015 allows default parameters in the function call:
	function (a=1, b=1) { /*function code*/ }

	Read more about function parameters and arguments at Function Parameters
	End Your Switches with Defaults

	Always end your switch statements with a default. Even if you think there is no need for it.
	Example
	switch (new Date().getDay()) {
	  case 0:
	    day = "Sunday";
	    break;
	  case 1:
	    day = "Monday";
	    break;
	  case 2:
	    day = "Tuesday";
	    break;
	  case 3:
	    day = "Wednesday";
	    break;
	  case 4:
	    day = "Thursday";
	    break;
	  case 5:
	    day = "Friday";
	    break;
	  case 6:
	    day = "Saturday";
	    break;
	  default:
	    day = "Unknown";
	}
	Avoid Using eval()

	The eval() function is used to run text as code. In almost all cases, it should not be necessary to use it.

	Because it allows arbitrary code to be run, it also represents a security problem.
JS performance - speed your JS
	Reduce Activity in Loops

	Loops are often used in programming.

	Each statement in a loop, including the for statement, is executed for each iteration of the loop.

	Statements or assignments that can be placed outside the loop will make the loop run faster.
	Bad:
	var i;
	for (i = 0; i < arr.length; i++) {
	Better Code:
	var i;
	var l = arr.length;
	for (i = 0; i < l; i++) {

	The bad code accesses the length property of an array each time the loop is iterated.

	The better code accesses the length property outside the loop and makes the loop run faster.
	Reduce DOM Access

	Accessing the HTML DOM is very slow, compared to other JavaScript statements.

	If you expect to access a DOM element several times, access it once, and use it as a local variable:
	Example
	var obj;
	obj = document.getElementById("demo");
	obj.innerHTML = "Hello";
	Reduce DOM Size

	Keep the number of elements in the HTML DOM small.

	This will always improve page loading, and speed up rendering (page display), especially on smaller devices.

	Every attempt to search the DOM (like getElementsByTagName) will benefit from a smaller DOM.
	Avoid Unnecessary Variables

	Don't create new variables if you don't plan to save values.

	Often you can replace code like this:
	var fullName = firstName + " " + lastName;
	document.getElementById("demo").innerHTML = fullName;

	With this:
	document.getElementById("demo").innerHTML = firstName + " " + lastName;
	Delay JavaScript Loading

	Putting your scripts at the bottom of the page body lets the browser load the page first.

	While a script is downloading, the browser will not start any other downloads. In addition all parsing and rendering activity might be blocked.

	The HTTP specification defines that browsers should not download more than two components in parallel.

	An alternative is to use defer="true" in the script tag. The defer attribute specifies that the script should be executed after the page has finished parsing, but it only works for external scripts.

	If possible, you can add your script to the page by code, after the page has loaded:
	Example
	<script>
	window.onload = function() {
	var element = document.createElement("script");
	element.src = "myScript.js";
	document.body.appendChild(element);
	};
	</script>
	Avoid Using with

	Avoid using the with keyword. It has a negative effect on speed. It also clutters up JavaScript scopes.

	The with keyword is not allowed in strict mode.
JS has reserved keywords
JS versions
	JS became an ECMA standard
	ECMAScript(ES) is the official name of the language.
	ECMAScript 3 is fully supported in all browsers.
	ECMAScript 5 is fully supported in all modern browsers.

	What is ECMAScript 5?

	ECMAScript 5 is also known as ES5 and ECMAScript 2009

	This chapter introduces some of the most important features of ES5.
	ECMAScript 5 Features

	These were the new features released in 2009:

	    The "use strict" Directive
	    String.trim()
	    Array.isArray()
	    Array.forEach()
	    Array.map()
	    Array.filter()
	    Array.reduce()
	    Array.reduceRight()
	    Array.every()
	    Array.some()
	    Array.indexOf()
	    Array.lastIndexOf()
	    JSON.parse()
	    JSON.stringify()
	    Date.now()
	    Property Getters and Setters
	    New Object Property Methods

	ECMAScript 5 Syntactical Changes

	    Property access [ ] on strings
	    Trailing commas in array and object literals
	    Multiline string literals
	    Reserved words as property names

	The "use strict" Directive

	"use strict" defines that the JavaScript code should be executed in "strict mode".

	With strict mode you can, for example, not use undeclared variables.

	You can use strict mode in all your programs. It helps you to write cleaner code, like preventing you from using undeclared variables.

	"use strict" is just a string expression. Old browsers will not throw an error if they don't understand it.

	Read more in JS Strict Mode.
	String.trim()

	String.trim() removes whitespace from both sides of a string.
	Example
	var str = "       Hello World!        ";
	alert(str.trim());

	Read more in JS String Methods.
	Array.isArray()

	The isArray() method checks whether an object is an array.
	Example
	function myFunction() {
	  var fruits = ["Banana", "Orange", "Apple", "Mango"];
	  var x = document.getElementById("demo");
	  x.innerHTML = Array.isArray(fruits);
	}

	Read more in JS Arrays.
	Array.forEach()

	The forEach() method calls a function once for each array element.
	Example
	var txt = "";
	var numbers = [45, 4, 9, 16, 25];
	numbers.forEach(myFunction);

	function myFunction(value) {
	  txt = txt + value + "<br>";
	}

	Learn more in JS Array Iteration Methods.
	Array.map()

	This example multiplies each array value by 2:
	Example
	var numbers1 = [45, 4, 9, 16, 25];
	var numbers2 = numbers1.map(myFunction);

	function myFunction(value) {
	  return value * 2;
	}

	Learn more in JS Array Iteration Methods.
	Array.filter()

	This example creates a new array from elements with a value larger than 18:
	Example
	var numbers = [45, 4, 9, 16, 25];
	var over18 = numbers.filter(myFunction);

	function myFunction(value) {
	  return value > 18;
	}

	Learn more in JS Array Iteration Methods.
	Array.reduce()

	This example finds the sum of all numbers in an array:
	Example
	var numbers1 = [45, 4, 9, 16, 25];
	var sum = numbers1.reduce(myFunction);

	function myFunction(total, value) {
	  return total + value;
	}

	Learn more in JS Array Iteration Methods.
	Array.reduceRight()

	This example also finds the sum of all numbers in an array:
	Example
	var numbers1 = [45, 4, 9, 16, 25];
	var sum = numbers1.reduceRight(myFunction);

	function myFunction(total, value) {
	  return total + value;
	}

	Learn more in JS Array Iteration Methods.
	Array.every()

	This example checks if all values are over 18:
	Example
	var numbers = [45, 4, 9, 16, 25];
	var allOver18 = numbers.every(myFunction);

	function myFunction(value) {
	  return value > 18;
	}

	Learn more in JS Array Iteration Methods.
	Array.some()

	This example checks if some values are over 18:
	Example
	var numbers = [45, 4, 9, 16, 25];
	var allOver18 = numbers.some(myFunction);

	function myFunction(value) {
	  return value > 18;
	}

	Learn more in JS Array Iteration Methods.
	Array.indexOf()

	Search an array for an element value and returns its position.
	Example
	var fruits = ["Banana", "Orange", "Apple", "Mango"];
	var a = fruits.indexOf("Apple");

	Learn more in JS Array Iteration Methods.
	Array.lastIndexOf()

	Array.lastIndexOf() is the same as Array.indexOf(), but searches from the end of the array.
	Example
	var fruits = ["Banana", "Orange", "Apple", "Mango"];
	var a = fruits.lastIndexOf("Apple");

	Learn more in JS Array Iteration Methods.
	JSON.parse()

	A common use of JSON is to receive data from a web server.

	Imagine you received this text string from a web server:
	'{"name":"John", "age":30, "city":"New York"}'

	The JavaScript function JSON.parse() is used to convert the text into a JavaScript object:
	var obj = JSON.parse('{"name":"John", "age":30, "city":"New York"}');

	Read more in our JSON Tutorial.
	JSON.stringify()

	A common use of JSON is to send data to a web server.

	When sending data to a web server, the data has to be a string.

	Imagine we have this object in JavaScript:
	var obj = {"name":"John", "age":30, "city":"New York"};

	Use the JavaScript function JSON.stringify() to convert it into a string.
	var myJSON = JSON.stringify(obj);

	The result will be a string following the JSON notation.

	myJSON is now a string, and ready to be sent to a server:
	Example
	var obj = {"name":"John", "age":30, "city":"New York"};
	var myJSON = JSON.stringify(obj);
	document.getElementById("demo").innerHTML = myJSON;

	Read more in our JSON Tutorial.
	Date.now()

	Date.now() returns the number of milliseconds since zero date (January 1. 1970 00:00:00 UTC).
	Example
	var timInMSs = Date.now();

	Date.now() returns the same as getTime() performed on a Date object.

	Learn more in JS Dates.
	Property Getters and Setters

	ES5 lets you define object methods with a syntax that looks like getting or setting a property.

	This example creates a getter for a property called fullName:
	Example
	// Create an object:
	var person = {
	  firstName: "John",
	  lastName : "Doe",
	  get fullName() {
	    return this.firstName + " " + this.lastName;
	  }
	};

	// Display data from the object using a getter:
	document.getElementById("demo").innerHTML = person.fullName;

	This example creates a setter and a getter for the language property:
	Example
	var person = {
	  firstName: "John",
	  lastName : "Doe",
	  language : "NO",
	  get lang() {
	    return this.language;
	  },
	  set lang(value) {
	    this.language = value;
	  }
	};

	// Set an object property using a setter:
	person.lang = "en";

	// Display data from the object using a getter:
	document.getElementById("demo").innerHTML = person.lang;

	This example uses a setter to secure upper case updates of language:
	Example
	var person = {
	  firstName: "John",
	  lastName : "Doe",
	  language : "NO",
	  set lang(value) {
	    this.language = value.toUpperCase();
	  }
	};

	// Set an object property using a setter:
	person.lang = "en";

	// Display data from the object:
	document.getElementById("demo").innerHTML = person.language;

	Learn more about Gettes and Setters in JS Object Accessors
	New Object Property Methods

	Object.defineProperty() is a new Object method in ES5.

	It lets you define an object property and/or change a property's value and/or metadata.
	Example
	// Create an Object:
	var person = {
	  firstName: "John",
	  lastName : "Doe",
	  language : "NO",
	};

	// Change a Property:
	Object.defineProperty(person, "language", {
	  value: "EN",
	  writable : true,
	  enumerable : true,
	  configurable : true
	});

	// Enumerate Properties
	var txt = "";
	for (var x in person) {
	  txt += person[x] + "<br>";
	}
	document.getElementById("demo").innerHTML = txt;

	Next example is the same code, except it hides the language property from enumeration:
	Example
	// Create an Object:
	var person = {
	  firstName: "John",
	  lastName : "Doe",
	  language : "NO",
	};

	// Change a Property:
	Object.defineProperty(person, "language", {
	  value: "EN",
	  writable : true,
	  enumerable : false,
	  configurable : true
	});

	// Enumerate Properties
	var txt = "";
	for (var x in person) {
	  txt += person[x] + "<br>";
	}
	document.getElementById("demo").innerHTML = txt;

	This example creates a setter and a getter to secure upper case updates of language:
	Example
	/// Create an Object:
	var person = {
	  firstName: "John",
	  lastName : "Doe",
	  language : "NO"
	};

	// Change a Property:
	Object.defineProperty(person, "language", {
	  get : function() { return language },
	  set : function(value) { language = value.toUpperCase()}
	});

	// Change Language
	person.language = "en";

	// Display Language
	document.getElementById("demo").innerHTML = person.language;

	ECMAScript 5 added a lot of new Object Methods to JavaScript:
	ES5 New Object Methods
	// Adding or changing an object property
	Object.defineProperty(object, property, descriptor)

	// Adding or changing many object properties
	Object.defineProperties(object, descriptors)

	// Accessing Properties
	Object.getOwnPropertyDescriptor(object, property)

	// Returns all properties as an array
	Object.getOwnpropertys(object)

	// Returns enumerable properties as an array
	Object.keys(object)

	// Accessing the prototype
	Object.getPrototypeOf(object)

	// Prevents adding properties to an object
	Object.preventExtensions(object)
	// Returns true if properties can be added to an object
	Object.isExtensible(object)

	// Prevents changes of object properties (not values)
	Object.seal(object)
	// Returns true if object is sealed
	Object.isSealed(object)

	// Prevents any changes to an object
	Object.freeze(object)
	// Returns true if object is frozen
	Object.isFrozen(object)

	Learn more in Object ECMAScript5.
	Property Access on Strings

	The charAt() method returns the character at a specified index (position) in a string:
	Example
	var str = "HELLO WORLD";
	str.charAt(0);            // returns H

	ECMAScript 5 allows property access on strings:
	Example
	var str = "HELLO WORLD";
	str[0];                   // returns H

	Property access on string might be a little unpredictable.

	Read more in JS String Methods.
	Trailing Commas

	ECMAScript 5 allows trailing commas in object and array definitions:
	Object Example
	person = {
	  firstName: "John",
	  lastName: " Doe",
	  age: 46,
	}
	Array Example
	points = [
	  1,
	  5,
	  10,
	  25,
	  40,
	  100,
	];

	WARNING !!!

	Internet Explorer 8 will crash.

	JSON does not allow trailing commas.
	JSON Objects:
	// Allowed:
	var person = '{"firstName":"John", "lastName":"Doe", "age":46}'
	JSON.parse(person)

	// Not allowed:
	var person = '{"firstName":"John", "lastName":"Doe", "age":46,}'
	JSON.parse(person)
	JSON Arrays:
	// Allowed:
	points = [40, 100, 1, 5, 25, 10]

	// Not allowed:
	points = [40, 100, 1, 5, 25, 10,]
	Strings Over Multiple Lines
	ECMAScript 5 allows string literals over multiple lines if escaped with a backslash:
	Example
	"Hello \
	Dolly!";

	The \ method might not have universal support.
	Older browsers might treat the spaces around the backslash differently.
	Some older browsers do not allow spaces behind the \ character.

	A safer way to break up a string literal, is to use string addition:
	Example
	"Hello " +
	"Dolly!";
	Reserved Words as Property Names

	ECMAScript 5 allows reserved words as property names:
	Object Example
	var obj = {name: "John", new: "yes"}





	//
	//
	What is ECMAScript 6?

ECMAScript 6 is also known as ES6 and ECMAScript 2015.

Some people call it JavaScript 6.

This chapter will introduce some of the new features in ES6.

    JavaScript let
    JavaScript const
    JavaScript Arrow Functions
    JavaScript Classes
    Default parameter values
    Array.find()
    Array.findIndex()
    Exponentiation (**) (EcmaScript 2016)

Browser Support for ES6 (ECMAScript 2015)

Safari 10 and Edge 14 were the first browsers to fully support ES6:

Chrome 58 	Edge 14 	Firefox 54 	Safari 10 	Opera 55
Jan 2017 	Aug 2016 	Mar 2017 	Jul 2016 	Aug 2018
JavaScript let

The let statement allows you to declare a variable with block scope.
Example
var x = 10;
// Here x is 10
{
  let x = 2;
  // Here x is 2
}
// Here x is 10
JavaScript const

The const statement allows you to declare a constant (a JavaScript variable with a constant value).

Constants are similar to let variables, except that the value cannot be changed.
Example
var x = 10;
// Here x is 10
{
  const x = 2;
  // Here x is 2
}
// Here x is 10

Read more about let and const in our JavaScript Let / Const Chapter.
Arrow Functions

Arrow functions allows a short syntax for writing function expressions.

You don't need the function keyword, the return keyword, and the curly brackets.
Example
// ES5
var x = function(x, y) {
   return x * y;
}

// ES6
const x = (x, y) => x * y;

Arrow functions do not have their own this. They are not well suited for defining object methods.

Arrow functions are not hoisted. They must be defined before they are used.

Using const is safer than using var, because a function expression is always constant value.

You can only omit the return keyword and the curly brackets if the function is a single statement. Because of this, it might be a good habit to always keep them:
Example
const x = (x, y) => { return x * y };

Learn more about Arrow Functions in our JavaScript Arrow Function chapter.
Classes

ES6 introduced classes.

A class is a type of function, but instead of using the keyword function to initiate it, we use the keyword class, and the properties are assigned inside a constructor() method.

Use the keyword class to create a class, and always add a constructor method.

The constructor method is called each time the class object is initialized.
Example

A simple class definition for a class named "Car":
class Car {
  constructor(brand) {
    this.carname = brand;
  }
}

Now you can create objects using the Car class:
Example

Create an object called "mycar" based on the Car class:
class Car {
  constructor(brand) {
    this.carname = brand;
  }
}
mycar = new Car("Ford");

Learn more about classes in our JavaScript Classes chapter.
Default Parameter Values

ES6 allows function parameters to have default values.
Example
function myFunction(x, y = 10) {
  // y is 10 if not passed or undefined
  return x + y;
}
myFunction(5); // will return 15
Array.find()

The find() method returns the value of the first array element that passes a test function.

This example finds (returns the value of ) the first element that is larger than 18:
Example
var numbers = [4, 9, 16, 25, 29];
var first = numbers.find(myFunction);

function myFunction(value, index, array) {
  return value > 18;
}

Note that the function takes 3 arguments:

    The item value
    The item index
    The array itself

Array.findIndex()

The findIndex() method returns the index of the first array element that passes a test function.

This example finds the index of the first element that is larger than 18:
Example
var numbers = [4, 9, 16, 25, 29];
var first = numbers.findIndex(myFunction);

function myFunction(value, index, array) {
  return value > 18;
}

Note that the function takes 3 arguments:

    The item value
    The item index
    The array itself

New Number Properties

ES6 added the following properties to the Number object:

    EPSILON
    MIN_SAFE_INTEGER
    MAX_SAFE_INTEGER

Example
var x = Number.EPSILON;
Example
var x = Number.MIN_SAFE_INTEGER;
Example
var x = Number.MAX_SAFE_INTEGER;
New Number Methods

ES6 added 2 new methods to the Number object:

    Number.isInteger()
    Number.isSafeInteger()

The Number.isInteger() Method

The Number.isInteger() method returns true if the argument is an integer.
Example
Number.isInteger(10);        // returns true
Number.isInteger(10.5);      // returns false
The Number.isSafeInteger() Method

A safe integer is an integer that can be exactly represented as a double precision number.

The Number.isSafeInteger() method returns true if the argument is a safe integer.
Example
Number.isSafeInteger(10);    // returns true
Number.isSafeInteger(12345678901234567890);  // returns false

Safe integers are all integers from -(253 - 1) to +(253 - 1).
This is safe: 9007199254740991. This is not safe: 9007199254740992.
New Global Methods

ES6 also added 2 new global number methods:

    isFinite()
    isNaN()

The isFinite() Method

The global isFinite() method returns false if the argument is Infinity or NaN.

Otherwise it returns true:
Example
isFinite(10/0);       // returns false
isFinite(10/1);       // returns true
The isNaN() Method

The global isNaN() method returns true if the argument is NaN. Otherwise it returns false:
Example
isNaN("Hello");       // returns true
Exponentiation Operator

The exponentiation operator (**) raises the first operand to the power of the second operand.
Example
var x = 5;
var z = x ** 2;          // result is 25

x ** y produces the same result as Math.pow(x,y):
Example
var x = 5;
var z = Math.pow(x,2);   // result is 25

JS JSON
	JSON is a format for storing and transporting data.
	JSON is often used when data is sent from a server to a web page.
	What is JSON?

    JSON stands for JavaScript Object Notation
    JSON is a lightweight data interchange format
    JSON is language independent *
    JSON is "self-describing" and easy to understand

* The JSON syntax is derived from JavaScript object notation syntax, but the JSON format is text only. Code for reading and generating JSON data can be written in any programming language.
JSON Example

This JSON syntax defines an employees object: an array of 3 employee records (objects):
JSON Example
{
"employees":[
  {"firstName":"John", "lastName":"Doe"},
  {"firstName":"Anna", "lastName":"Smith"},
  {"firstName":"Peter", "lastName":"Jones"}
]
}
The JSON Format Evaluates to JavaScript Objects

The JSON format is syntactically identical to the code for creating JavaScript objects.

Because of this similarity, a JavaScript program can easily convert JSON data into native JavaScript objects.
JSON Syntax Rules

    Data is in name/value pairs
    Data is separated by commas
    Curly braces hold objects
    Square brackets hold arrays

JSON Data - A Name and a Value

JSON data is written as name/value pairs, just like JavaScript object properties.

A name/value pair consists of a field name (in double quotes), followed by a colon, followed by a value:
"firstName":"John"

JSON names require double quotes. JavaScript names do not.
JSON Objects

JSON objects are written inside curly braces.

Just like in JavaScript, objects can contain multiple name/value pairs:
{"firstName":"John", "lastName":"Doe"}
JSON Arrays

JSON arrays are written inside square brackets.

Just like in JavaScript, an array can contain objects:
"employees":[
  {"firstName":"John", "lastName":"Doe"},
  {"firstName":"Anna", "lastName":"Smith"},
  {"firstName":"Peter", "lastName":"Jones"}
]

In the example above, the object "employees" is an array. It contains three objects.

Each object is a record of a person (with a first name and a last name).
Converting a JSON Text to a JavaScript Object

A common use of JSON is to read data from a web server, and display the data in a web page.

For simplicity, this can be demonstrated using a string as input.

First, create a JavaScript string containing JSON syntax:
var text = '{ "employees" : [' +
'{ "firstName":"John" , "lastName":"Doe" },' +
'{ "firstName":"Anna" , "lastName":"Smith" },' +
'{ "firstName":"Peter" , "lastName":"Jones" } ]}';

Then, use the JavaScript built-in function JSON.parse() to convert the string into a JavaScript object:
var obj = JSON.parse(text);

Finally, use the new JavaScript object in your page:
Example
<p id="demo"></p>

		<script>
		document.getElementById("demo").innerHTML =
		obj.employees[1].firstName + " " + obj.employees[1].lastName;
		</script>

JS forms
	HTML fomr validation can be done by JS
	if form field empty, function alerts a message and returns false to prevent submission
		<script>
		function validateForm() {
		  var x = document.forms["myForm"]["fname"].value;
		  if (x == "") {
		    alert("Name must be filled out");
		    return false;
		  }
		}
		</script>
		<form name="myForm" action="/action_page.php" onsubmit="return validateForm()" method="post">
		  Name: <input type="text" name="fname">
		  <input type="submit" value="Submit">
		</form>
	can also validate numeric data
		<script>
			function myFunction() {
			  var x, text;

			  // Get the value of the input field with id="numb"
			  x = document.getElementById("numb").value;

			  // If x is Not a Number or less than one or greater than 10
			  if (isNaN(x) || x < 1 || x > 10) {
			    text = "Input not valid";
			  } else {
			    text = "Input OK";
			  }
			  document.getElementById("demo").innerHTML = text;
			}
		</script>
	automatic html form validation
		form validation can be performed automatically by the browsers
		using 'required' attribute in html, no js
	data validatoin
		process of ensuring that user input is clean, correct and useful
			typical validation
				filled all required fields
				entered a valid info in field such as nums in numeric field
				Server side validation is performed by a web server, after input has been sent to the server
				Client side validation is performed by a web browser, before input is sent to a web server
	html constraint validation
		based on:
			Constraint validation HTML Input Attributes
			Constraint validation CSS Pseudo Selectors
			Constraint validation DOM Properties and Methods
		input attributed
			disabled 	Specifies that the input element should be disabled
			max 	Specifies the maximum value of an input element
			min 	Specifies the minimum value of an input element
			pattern 	Specifies the value pattern of an input element
			required 	Specifies that the input field requires an element
			type  	Specifies the type of an input element
		css pseudo Selectors
			:disabled 	Selects input elements with the "disabled" attribute specified
			:invalid 	Selects input elements with invalid values
			:optional 	Selects input elements with no "required" attribute specified
			:required 	Selects input elements with the "required" attribute specified
			:valid 	Selects input elements with valid values
JS validation API
	constraint validation DOM methods
		checkValidity() 	Returns true if an input element contains valid data.
		setCustomValidity() 	Sets the validationMessage property of an input element.
	If an input field contains invalid data, display a message:
		The checkValidity() Method
		<input id="id1" type="number" min="100" max="300" required>
		<button onclick="myFunction()">OK</button>

		<p id="demo"></p>

		<script>
		function myFunction() {
		  var inpObj = document.getElementById("id1");
		  if (!inpObj.checkValidity()) {
		    document.getElementById("demo").innerHTML = inpObj.validationMessage;
		  }
		}
	constraint validation DOM proterties
		validity 	Contains boolean properties related to the validity of an input element.
		validationMessage 	Contains the message a browser will display when the validity is false.
		willValidate 	Indicates if an input element will be validated.
	validity properties
		validity property of input element contains a number of properties related to the validity data
			customError 	Set to true, if a custom validity message is set.
			patternMismatch 	Set to true, if an element's value does not match its pattern attribute.
			rangeOverflow 	Set to true, if an element's value is greater than its max attribute.
			rangeUnderflow 	Set to true, if an element's value is less than its min attribute.
			stepMismatch 	Set to true, if an element's value is invalid per its step attribute.
			tooLong 	Set to true, if an element's value exceeds its maxLength attribute.
			typeMismatch 	Set to true, if an element's value is invalid per its type attribute.
			valueMissing 	Set to true, if an element (with a required attribute) has no value.
			valid 	Set to true, if an element's value is valid.
		e.g.
			The rangeOverflow Property
				<input id="id1" type="number" max="100">    // if input field is > 100 display message
				<button onclick="myFunction()">OK</button>

				<p id="demo"></p>

				<script>
				function myFunction() {
				  var txt = "";
				  if (document.getElementById("id1").validity.rangeOverflow) {
				    txt = "Value too large";
				  }
				  document.getElementById("demo").innerHTML = txt;
				}
				</script>









js Objects
	js - almost everything is an object
	all js values, except primitives, are objects:
		objects:
			Dates
			Maths
			Regular expressions
			Arrays
			Functions
			Objects
		objects if defined with 'new':
			boolean, numbers Strings
	js primatives
		primative value - value with no properties or Methods
		primative data type - data that has a primative value
		primative values are immutable
			if x=3 you can change value of x but not the value of 3
	objects are Variables
		js vars can contain a single value
		objects are vars with many values written as 'name : value'
		named values are called properties
		objects written as name value pairs are similar to:
			Associative arrays in PHP
			Dictionaries in Python
			Hash tables in C
			Hash maps in Java
			Hashes in Ruby and Perl
	object Methods
		actions perfomed on objects
		object properties can be both primative values, objects and Functions
		object method = object property containing a function definition
	creating objects -4 ways
    Define and create a single object, using an object literal.
    Define and create a single object, with the keyword new. // dont use use literal for simplicity
    Define an object constructor, and then create objects of the constructed type.
		object.create() function
	objects are mutable - addressed by reference not value
object properties
 	can be manipulated and some are read only
	syntax for accessing properties
		objectName.property
		or
			objectName["property"]
		or
			objectName[expression]  // // x = "age"; myobj[x]  expression must evaluate to a property name
	for in loop - loop through the properties of an object
		syntax
			for (variable in object) {
				// code to be executed once for each property
			}
	add new properties - by giving it a new property and value
	 	syn
			obj.newproperty = "new value";
	delete properties - 'delete' keyword
		syntax
			delete obj.property;
		deletes property and value
		should not be used on predefined object properties - crash app
	porperty attributs
		value is a property's attribute
		also include: enumerable, configurable and writeable
		all attributes can be read but only value attribute van be changed if property is writeable
	prototype properties
		objects inhertit the properties of their prototype
		'delete' a prototype property and ll objects inherited from prototype will be affected
object Methods
	actions performed on objects
	syntax to access object method
		obj.method()
costructors
	blueprint for creating many objects of the same tupe is to use an objject constructor function
		syntax
			function obj()
			create objects of the same type:
			let myNewObj = new obj()
	cannot add new property to existing object constructors, to addi it you must add it within the constructor

Function
	'function' - define function
	use functino decalration or function exprsession
	function declaration
		function functionName(parameters) {
			// code to be executed
		}
		not executed until invoked
	function expression
		can be stroed in variable
			let x = function (a, b) {return a * b};
			now the variable can be used as the function
				e.g. let z = x(4, 3);
		as above a function name is not given(anonymous function) but just declared with 'function'
			they are invoked using var name
	function() constructor - avoid using
		function() - built-in constructor to define a functon
		using 'new' keyword - avoid using new keyword
	self-invoking functions
		Function expressions can be made "self-invoking".
		A self-invoking expression is invoked (started) automatically, without being called.
		Function expressions will execute automatically if the expression is followed by ().
		You cannot self-invoke a function declaration.
		You have to add parentheses around the function to indicate that it is a function expression:
		(function () { // anonymous self invoking function
			document.getElementById("demo").innerHTML = "Hello! I called myself";
		})();
	funcions can be used in expressions
		var x = myFunction(4, 3) * 2;
	arrow functions
