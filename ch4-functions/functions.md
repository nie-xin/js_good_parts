###Function objects

Functions in js are objects which are collections of name-value pairs having a hidden link to a prototype object.

Functions can be stored in variables, objects and arrays. Functions can be passed as arguments to functions, and functions can ben returned from functions.

###Function literal

	// create a varialb called add and store a function in it that adds two numbers
	var add = function(a, b) {
		return a + b;
	};

Function literal have 4 parts:
	1. reserved word "function"
	2. function name(optional) - can be used to call itself recursively. If function has no name then it is called anonymous
	3. the set of parameters
	4. set of statements in curly braces that are body of the function

###The method invocation pattern

If a function is stored as a property of an object, it is called a "method".

	var myObject = {
		value: 0,
		// the increment is a method of the object
		increment: function(inc) {
			this.value += typeof inc === 'number' ? inc : 1;
		}
	};

###The function invocation pattern

When a function is not the property of an object, then it is invoked as a function. 

	myObject.double = function() {
		// this is bound to the global object
		var that = this;

		var helper = function() {
			// in the inner function, this is still bound to this of outer function
			that.value = add(that.value, that.value);
		};

		helper();
	};

###The constructor invocation pattern

	// create a constructor function
	var Quo = function(string) {
		this.status = string;
	};

	// give all instance of Quo a public methos called get_status
	Quo.prototype.get_status = function() {
		return this.status;
	};

	// this is how we make an instance
	var myQuo = new Quo("confused");
	// how we get status
	myQuo.get_status();

###The apply invocation pattern

The apply methos takes 2 parameters - the first is the value that should be bound to this. The second is an array of parameters.

	var array = [3, 4];
	var sum = add.apply(null, array);

	var statusObject = {
		status: 'A-OK'
	};

	var status = Quo.prototype.get_status.apply(statusObject);