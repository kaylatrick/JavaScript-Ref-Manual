#Javascript Manual

##values, data types
Data types:
- Primitive: String, number, boolean, null, undefined
- Object

Value:
- raw data assigned to a variable
- String: immutable list of characters, ex: 'value' or "value" (can be single or double quotes)
- Number: numeric, example: 4
- Boolean: true/false
- Null: has a value of null
- undefined: not assigned a value
- Object: series of key-value pairs (ex {foo: 4})

##operations / operators / operands
Operators: plus, minus, multiply, divide (in 5+3, '+' is the operator)
Operand: values being acted upon by an operator (in 5+3, 5 and 3 are the operands)
Operation: process of using operators and operands (in 5+3, '5+3' is the operation)

##variables, var
variable: reference to a piece of data in memory (ex: var x = 4;)

##reserved words
select words in the language that have a specific meaning (ex: for, where, function).  These words cannot be used for variable names.

##statements vs. expressions
Statement: describes a complete action, whether it returns a value or not (ex: if(true) {console.log("hi")};)
Expression: anything that resolves in a value (ex: var y = 1 + 2;)

##variables vs. values
variable references a String or another data type, while a value is that piece of data in memory
ex: var x = 4; (x is the variable, while 4 is the value)

##if-else //T
If / else statements are conditional statements. Under different conditions, the computer will output different things.
  1) IF Statement say if the condition evaluate to "True" then execute to the next statement or otherwise skip the next statement and go on from there.
  2) Else Statement says if the condition evaluate to "False"
  Example:
  var stopnumber = 5;
  for (var i = 1; i < 11; i++)  {
    if (i === stopnumber)   {
      console.log("The loop stops here!<br>");
      break;
    } else {
      console.log(i + "I am part of a loop!<br>");
    }
}

##while //L
A While Loop is a loop that continues to perform "while" the condition is true.
Example:
The following loop will run ininitely because the condition is always true:
while(true){
  console.log("Stuff");
}
This loop will run 10 times:
var a = 0;
while(a<10){
  a++;
}
##for //K
a statement in javascript that loops through a set number of times; made up of 3 statements:
   1) pre-statement, which defines a variable,
   2) statement, which is the condition for the loop to run, and
   3) post-statement, which denotes how the pre-statement is changing each time you loop through (i++, i--)
Ex:
for(var i = 0; i < array.length; i++) {
  array[i] = i+1;
}

##for-in //T
A for-in loop allows you to iterates over the properties of an object.

Example:
var obj = {amber: 2, brandy: 9, todd: 5};
var arr = [];
for (var k in obj) {
    arr[arr.length] = k;
}
var a = arr;  

A for-in loop allows you to iterates over the indexes of an array.
Example:
var x = [10, 20, 30, 40, 50];
var y = [];
// copy every element of 'x' to 'y'
for (var i in arr) {
    y[i] = x[i];         // 'i' is the index, not the value!
}

##functions //L
  A function is a called operation that may or may not accept input values and may or may not return a value.
  Example:
  function addition(x,y){
    return x+y
  }
  addition(6,2) returns 8
  function declaration(){
    console.log("I love ice cream!")
  }

  declaration() prints "I love ice cream!" to the console.

##local vs. global variables //K
local variables
  - variables only valid inside of a function
  - cannot be accessed outside of the function

  Ex: the below variable "y" cannot be access outside of the below function
    function orange(x,y) {
    var z = x+y;
    }

    console.log(z);   // not valid!!

global variables
  - variables that can be accessed anywhere in the javascript code

  Ex: The below results in a value of 9.
  var x = 2;
  function yellow(y) {
    return x^2 + y;
  }
  console.log(yellow(5));

##arrays //T
An array is a container that store lists of data that can be made up of different data types that holds a fixed number of values of a single type.
1) var names = ["Bob", "Nancy", "Fred"];
2) var sizes = [1,2,4,8,9];
3) var mixed = [3,"Billy","blue", "candy"];

##objects //L
An object is similar to an array but its elements are referenced through key/value pairs and not indices.  
Example:
var o = {this:2,that:"hey",thing:"yo"}
(o.this == 2) evaluates to true as well as (o.that == "hey").

##methods //K
functions stored as object properties

Ex: the below returns '3, 7, Object{lucas: function()}'
function apple(x, y) {
		console.log(x, y, this);
	}
var obj = {
		lucas: apple
	};
obj.lucas(3,7);

##the different uses of . [] {} ;
  .
  - accessing/calling methods
  - accessing/assigning properties of objects

  []
  - creating an array (var a = [1,2])
  - access/assign to indexes of arrays (a[0] = 4;)
  - acess/assign to key of object (O["I'm a key"] = 4;)

  {}
  - body of function/loops/if elsecompound statementcreating an object ( {foo: 3; 'hi there': 9})

  ;
  - end of statement without a body
  - separation between condition and pre-condition (for(var i = 0; i < 6; i++))

  ()
  - surrounds conditions
  - overriding order of operations
  - calling a function/methods (surrounds args)
  - surrounding parameters

##object links //T
An object link can be perform when you set a global namespace s called Object which has a method create. The create method takes an object and returns a new object that is linked to the first:

Example:
var x = {};
var y = Object.create(x);     Note....return an object linked to the object referenced by 'x'

##anonymous functions //L
These functions are declared at runtime and are not given names in the same way as normal functions.
Example:
This is a normal function:
function hello(){
  console.log("hello");
}
To do the same function anonymously:
var hello = function(){
  console.log("hello");
}
##nested function scope / closures //K
Nested function scope
  - when a function is nested within another function, it can only be called by the function containing it and can not be called elsewhere
  - in the example below, the nested function is contained in the variable 'bar' and is called at the end of the foo() function

closures
  - makes it possible to access the scope of the parent function
  - in the example below, 'x++' is able to access x in its parent function

Ex:
function foo(x) {
  var y = x + 2;
  var bar = function () {
    x++;
    console.log(x,y);
  };
  return bar;
  }
var a = foo(3);
var b = foo(7);

a(); // 4 5
b(); // 8 9
a(); // 5 5

##exceptions //T
Exceptions are consider errors that occur in Javascript where an error message gets generated
based on coding errors made by the developer, wrong input or other things.

Example:
"Uncaught SyntaxError: Unexpected token )"
var a = ()
for (var i=0; i<0; i++)
a(i)

##try-catch //L
The try-catch executes the code within the "try" block and tests it for errors.  If there is an error then the error is handled by the "catch" block.  It is possible to have multiple "catch" blocks.
Example:

var ajaxrequest=null
if (window.ActiveXObject){ //Test for support for different versions of ActiveXObject in IE
    try {
        ajaxrequest=new ActiveXObject("Msxml2.XMLHTTP")
    }
    catch (e){
        try{
        ajaxrequest=new ActiveXObject("Microsoft.XMLHTTP")
        } //end inner try
        catch (e){
            alert("I give up. Your IE doesn't support Ajax!")
        } //end inner catch
    } //end outer catch
}
else if (window.XMLHttpRequest) // if Mozilla, Safari etc
    ajaxrequest=new XMLHttpRequest()
ajaxrequest.open('GET', 'process.php', true) //do something with request

##the global namespace //K
Javascript objects/variables that can be accessed anywhere else in the code; need to be careful when using global variables as it can be hard to keep track of its transformations throughout the code

Ex:
var x = 4;
function blue(y) {
  x = x * y;
}
blue(5);
console.log(x) //20

##important functions and objects in the global namespace //T
##DOM methods and properties //L

##event handlers //K
methods that are executed when a particular event occurs

Example:
<html><body>
<ol id="foo">
  <li>Apple</li>
  <li>Orange</li>
  <li>Banana</li>
  <li>Kiwi</li>
</ol>
</body></html>

<script>
Function hello(evt) {
  Console.log('yo'); }
var foo = document.getElementById('foo');
foo.addEventListener('click', hello); //when you click on any part of the above list
</script>
