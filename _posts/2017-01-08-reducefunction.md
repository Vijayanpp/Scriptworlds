---
layout: post_page
title: Understand JavaScript reduce() function
---

JavaScript’s reduce function is an another useful method in JavaScript.The reduce() method applies a function against an accumulator and each value of the array (from left-to-right) to reduce it to a single value.The return value of the function is stored in an accumulator (result/total).The reduce() does not execute the function for array elements without the values

<h3>Example</h3>

<div class='code'>
var n=[1,2,3,4,5]
var sum=n.reduce((a,b)=>{
return a+b},0)

//sum 15
</div>


<h3>Syntax of map() function</h3>

 arr.reduce(callback, [initialValue])

 <h3>Parameters</h3>

callback
	Function to execute on each value in the array, taking four arguments:
	accumulator
	The accumulated value previously returned in the last invocation of the callback, or initialValue, if supplied. (See below.)
	currentValue
	The current element being processed in the array.
	currentIndex
	The index of the current element being processed in the array. Starts at index 0, if an initialValue is provided, and at index 1 otherwise.
	array
	The array reduce was called upon.
	initialValue
	Optional. Value to use as the first argument to the first call of the callback.

Return value

The value that results from the reduction.


<h3>Description</h3>
<p>reduce executes the callback function once for each element present in the array, excluding holes in the array, receiving four arguments:</p>

accumulator
currentValue
currentIndex
array
<p>The first time the callback is called, accumulator and currentValue can be one of two values. If initialValue is provided in the call to reduce, then accumulator will be equal to initialValue and currentValue will be equal to the first value in the array. If no initialValue was provided, then accumulator will be equal to the first value in the array and currentValue will be equal to the second.In above example we provided the initialvalue 0.So  accumulator is  0 and initial value is 1.</p>

<h3>Example</h3>

<div class='code'>
[0,1,2,3,4].reduce( (accumulator, currentValue, currentIndex, array) => {
  return accumulator + currentValue;
}, 10)
</div>

In above example
accumulator =10,currentValue=1,currentIndex=0,array=[0,1,2,3,4]
<div class='code'>
<table>
 <thead>
  <tr>
   <th scope="col"><code>callback</code></th>
   <th scope="col"><code>accumulator</code></th>
   <th scope="col"><code>currentValue</code></th>
   <th scope="col"><code>currentIndex</code></th>
   <th scope="col"><code>array</code></th>
   <th scope="col">return value</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <th scope="row">first call</th>
   <td><code>10</code></td>
   <td><code>0</code></td>
   <td><code>0</code></td>
   <td><code>[0, 1, 2, 3, 4]</code></td>
   <td><code>10</code></td>
  </tr>
  <tr>
   <th scope="row">second call</th>
   <td><code>10</code></td>
   <td><code>1</code></td>
   <td><code>1</code></td>
   <td><code>[0, 1, 2, 3, 4]</code></td>
   <td><code>11</code></td>
  </tr>
  <tr>
   <th scope="row">third call</th>
   <td><code>11</code></td>
   <td><code>2</code></td>
   <td><code>2</code></td>
   <td><code>[0, 1, 2, 3, 4]</code></td>
   <td><code>13</code></td>
  </tr>
  <tr>
   <th scope="row">fourth call</th>
   <td><code>13</code></td>
   <td><code>3</code></td>
   <td><code>3</code></td>
   <td><code>[0, 1, 2, 3, 4]</code></td>
   <td><code>16</code></td>
  </tr>
  <tr>
   <th scope="row">fifth call</th>
   <td><code>16</code></td>
   <td><code>4</code></td>
   <td><code>4</code></td>
   <td><code>[0, 1, 2, 3, 4]</code></td>
   <td><code>20</code></td>
  </tr>
 </tbody>
</table>

</div>

Alos consider the cases

<div class='code'>
if initial value is 3 then sum will be 18
if initial value is 5 then sum will be 20
</div>

<p>So now we have to conside the another case, what will be the return value  if there is no initial vale.</p>

<div class='code'>
var n=[1,2,3,4,5]
var sum=n.reduce((a,b)=>{
return a+b})

//sum 15
</div>

<b>Note:</b> <p>If initialValue isn't provided, reduce will execute the callback function starting at index 1, skipping the first index. If initialValue is provided, it will start at index 0.</p>

<h3>Example</h3>

<div class='code'>

[0, 1, 2, 3, 4].reduce(function(accumulator, currentValue, currentIndex, array) {
  return accumulator + currentValue;
});

</div>

In abouve example accumulator=0(first element),currentValue=1,currentIndex=1,array=[0,1,2,3,4]

<div class='code'>
<table>
 <thead>
  <tr>
   <th scope="col"><code>callback</code></th>
   <th scope="col"><code>accumulator</code></th>
   <th scope="col"><code>currentValue</code></th>
   <th scope="col"><code>currentIndex</code></th>
   <th scope="col"><code>array</code></th>
   <th scope="col">return value</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <th scope="row">first call</th>
   <td><code>0</code></td>
   <td><code>1</code></td>
   <td><code>1</code></td>
   <td><code>[0, 1, 2, 3, 4]</code></td>
   <td><code>1</code></td>
  </tr>
  <tr>
   <th scope="row">second call</th>
   <td><code>1</code></td>
   <td><code>2</code></td>
   <td><code>2</code></td>
   <td><code>[0, 1, 2, 3, 4]</code></td>
   <td><code>3</code></td>
  </tr>
  <tr>
   <th scope="row">third call</th>
   <td><code>3</code></td>
   <td><code>3</code></td>
   <td><code>3</code></td>
   <td><code>[0, 1, 2, 3, 4]</code></td>
   <td><code>6</code></td>
  </tr>
  <tr>
   <th scope="row">fourth call</th>
   <td><code>6</code></td>
   <td><code>4</code></td>
   <td><code>4</code></td>
   <td><code>[0, 1, 2, 3, 4]</code></td>
   <td><code>10</code></td>
  </tr>
 </tbody>
</table>

</div>

<p>If the given array has only one element  and no initialValue was provided, or if initialValue is provided but the array is empty, the solo value would be returned without calling callback.</p>

<h3>Examples</h3>

<div class='code'>
var n=[1];
var sum=n.reduce((a,b)=>
                 {
return a+b})

//sum 1
</div>

<div class='code'>
var n=[];
var sum=n.reduce((a,b)=>
                 {
return a+b},10)

//sum 10
</div>


 <h3>Conclusion</h3>

 Waht is Javascript reducer()? Javascript Reduce function is reducing a collection of elements.That's it! 