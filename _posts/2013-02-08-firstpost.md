---
layout: post_page
title: JavaScript map() function
---

JavaScript’s map function is an extremely useful method for JavaScript devlopers, but it can also be a bit confusing for beginners.So what is Javascript map() function.The map() method creates a new array with the results of calling a  function on every element in this array.The map() method calls the provided function once for each element in an array, in order.This method does not execute the function for array elements without values .It doesn't change the original array instead it will return a new array

<h3>Example</h3>

<div class='code'>
var numbers = [4, 9, 16, 25];

var roots = numbers.map(function(x){
   return x * 2;
});

/ roots is now [16, 81, 256, 525]
// numbers is still [4, 9, 16, 25]
</div>


<h3>Syntax of map() function</h3>

 var newarray = arr.map(callback[, thisArg])

 <h3>Parameters</h3>

callback
Function that produces an element of the new Array, taking three arguments:
 
	currentValue
	The current element being processed in the array.
	index
	The index of the current element being processed in the array.
	array
	The array map was called upon.
	thisArg
	Optional. Value to use as this when executing callback.
Return value

A new array with each element being the result of the callback function.