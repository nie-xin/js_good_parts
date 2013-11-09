Grammar
---

###Whitespace

/* */ are not safe for commenting out blocks of code because those pairs can occur in regular expression literals

	/*
		var rm_a = /a*/.match(s);
	 */
	
So // comments is recommended.


###Numbers

A single number type represented as 64-bit floating point. There is no difference between 1 and 1.0, they are considered as same value in js. So all you need to konw is that it is a number.

NaN is not equal to any value, including itself. 
	
	isNaN(number)	// test if number is NaN 

The value Infinity represents all values greater than 1.79769313486231570e+308

###Strings

All characters in js are 16 bits wide. 

There is no char type in js, so a character could be represented by a string with one char in it.

String can never be changed once it is made. 


###Statements

Blocks in js do not create a new scope, so variables should be defined ar top of the function, not in blocks.

False value:

	*false
	*null
	*undefined
	*empty string ''
	*number 0
	*number NaN
	