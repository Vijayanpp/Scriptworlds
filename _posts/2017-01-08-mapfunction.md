---
layout: post_page
title:Understand JavaScript map() function
---

JavaScript’s map function is an extremely useful method for JavaScript devlopers, but it can also be a bit confusing for beginners.So what is Javascript map() function.The map() method creates a new array with the results of calling a  function on every element in this array.The map() method calls the provided function once for each element in an array, in order.This method does not execute the function for array elements without values .It doesn't change the original array instead it will return a new array

<h3>Example</h3>

<div class='code'>
var numbers = [4, 9, 16, 25];

var square = numbers.map(function(x){
   return x * x;
});

//squar is now [16, 81, 256, 525]
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


<h3>Mapping an array of numbers to array</h3>
<p>This example takes an array of numbers and creates a new array containing the square roots of the numbers in the first array</p>
<div class='code'>
var num=[4,5,6]
var squareroot=num.map(Math.sqrt)

//squareroot is now[2, 2.23606797749979, 2.449489742783178]
// numbers is still [4,5,6]
</div>

<h3>Using map generically</h3>

<p>Following example shows that how to use map function on a string to get an array of   characters in a string</p>

<div class='code'>
let map=Array.prototype.map
let g=map.call("i am a programmer",(value)=>{
return value.charAt(0)
})

//g is ["i", " ", "a", "m", " ", "a", " ", "p", "r", "o", "g", "r", "a", "m", "m", "e", "r"]

</div>

<h3>Check a string is palindrome or not</h3>

<p>In this example i created a function using map() method which will check that given string is a palindrome or not</p>

 <div class='code'>

function checkPalindrome(str)
{
let a=Array.prototype.map.call(str,(x)=>{
return x
}).reverse().join('')
if (a===str){
return true
} else{
return false;
}
}

// checkPalindrome("vijayan") return false;
// checkPalindrome("iii") return true

 </div>

 <h3>Conclusion</h3>

 map() is an intersting and very important method in JavaScript Array, so it’s well worth taking the time to understand it. Hopefully this short tutorial help you to undestand the map() method