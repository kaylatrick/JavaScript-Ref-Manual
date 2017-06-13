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
##while //L
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
##anonymous functions //L
##nested function scope / closures //K
##exceptions //T
##try-catch //L
##the global namespace //K
##important functions and objects in the global namespace //T
##DOM methods and properties //L
##event handlers //K
