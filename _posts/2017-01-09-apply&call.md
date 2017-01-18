---
layout: post_page
title: What is the Difference Between call() and apply()
---

Javascript apply() and call() are two important methods in JavaScript.It is  essential for every JavaScript developers.is there any difference between these two methods?.

Lets have a looks at the definitions

<h3>Apply()</h3>
<p>The apply() thod calls a function with a given this value and argunts provided as an array (or an array-like object).</p>

<h3>Call()</h3>
<p>The call() thod calls a function with a given this value and argunts provided individually.

<b>Note:</b>A useful mnemonic is "A(apply())for array and C(call()) for comma."
<h3>Examples</h3>

<div class='code'>
<pre>
var person={na:"john",age:"20"}

function sayAbout(argunt1,argunt2)
{
console.log(argunt1+" "+this.na+" "+argunt2+" "+this.age)
}

sayAbout.call(person,"my na is","and my age is")
//my na is john my age is 20
</pre>
</div>

<div class='code'>
<pre>
var person={na:"john",age:"20"}

function sayAbout(arguement1,arguement2)
{
console.log(arguement1+" "+this.na+" "+arguement2+" "+this.age)
}

sayAbout.apply(person,["my father is","and his age is"])
//my na is john my age is 20
</pre>
</div>


<h3>Syntax of apply() function</h3>

 fun.apply(thisArg, [argsArray])

 <h3>Parameters</h3>

<h4>thisArg</h4>

The value of this provided for the call to fun. Note that this may not be the actual value seen by the thod: if the thod is a function in non-strict mode code, null and undefined will be replaced with the global object, and primitive values will be boxed.

<h4>argsArray</h4>

An array-like object, specifying the argunts with which fun should be called, or null or undefined if no argunts should be provided to the function. Starting with ECMAScript 5 these argunts can be a generic array-like object instead of an array. See below for browser compatibility information.

Return value

The result of calling the function with the specified this value and argunts.


<h3>Syntax of call() function</h3>

  fun.call(thisArg[, arg1[, arg2[, ...]]])

<h3>Paraters</h3>

<h4>thisArg</h4>

  The value of this provided for the call to fun. Note that this may not be the actual value seen by the thod: if the thod is a function in non-strict mode code, null and undefined will be replaced with the global object and primitive values will be converted to objects.

<h4>arg1, arg2, ...</h4>

  Argunts for the object.

<h4>Return value</h4>

  The result of calling the function with the specified this value and argunts.


  <h3>Examples</h3>

  <div class="code">
  <pre>
   function developer() {
  var reply = [this.person, 'Is a genius', this.role].join(' ');
  console.log(reply);
   }

var i = {
  person: 'Varun ', role: 'Javascript Developer'
};

greet.call(i);


  </pre>
  </div>

  <div class="code">
  <pre>
   var person1 = {
    car: false,
    lendCar: function ( canLend ){
      this.car = canLend;
 }

}; 

var person2 = {
    car: false,
    gotCar: function(){
      return this.car === true;
  }
};

console.log(person2.gotCar()); // false

person1.lendCar.call(, true); 

console.log(person2.gotCar()); // true

person1.lendCar.apply(, [false]);

console.log(person2.gotCar()); // false

  </pre>
  </div>




 <h3>Conclusion</h3>

  While the syntax of this functions are  almost identical , the fundamental difference is that call() accepts an argument list, while apply() accepts a single array of arguments.