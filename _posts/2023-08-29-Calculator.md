---
toc: true
comments: false
layout: post
title: Calculator
description: Using HTML and JavaScript to do basic calculations.
courses: { compsci: {week: 2} }
type: hacks
---

<html>

<style>
	*{
    padding: 0;
    margin: 0;
    font-family: 'poppins', sans-serif;
 }
 body{
    background-color: #495250;
    display: grid;
    height: 100vh;
    place-items: center;
	margin-top: 0.2rem;
 }
 .main{
    width: 400px;
    height: 450px;
    background-color: #171515;
    position: relative;
    border: 5px solid black;
    border-radius: 6px; 
 }
 .main input[type='text'] {
    width: 88%;
    position: relative;
    height: 80px;
    top: 5px;
    text-align: right;
    padding: 3px 6px;
    outline: none;
    font-size: 40px;
    border: 5px solid black;
    display: flex;
    margin: auto;
    border-radius: 6px;
    color: black;
 }
 .btn input[type='button']{
    width:90px;
    padding: 2px;
    margin: 2px 0px;
    position: relative;
    left: 13px;
    top: 20px;
    height: 60px;
    cursor: pointer;
    font-size: 18px;
    transition: 0.5s;
    background-color: #495250;
    border-radius: 6px;
    color: white;
 }
 .btn input[type='button']:hover{
    background-color: black;
    color: white;
 }
</style>


<html lang="en">
<head>
   <title>Calulator</title>
</head>

<body>
   <div class="main">
      <input type="text" id = 'res'>
      <div class="btn">
         <input type="button" value = 'C' onclick = "Clear()">
         <input type="button" value = '%' onclick = "Solve('%')">
         <input type="button" value = '←' onclick ="Back('←')">
         <input type="button" value = '/' onclick = "Solve('/')">
         <br>
         <input type="button" value = '7' onclick = "Solve('7')">
         <input type="button" value = '8' onclick = "Solve('8')">
         <input type="button" value = '9' onclick = "Solve('9')">
         <input type="button" value = 'x' onclick = "Solve('*')">
         <br>
         <input type="button" value = '4' onclick = "Solve('4')">
         <input type="button" value = '5' onclick = "Solve('5')">
         <input type="button" value = '6' onclick = "Solve('6')">
         <input type="button" value = '-' onclick = "Solve('-')">
         <br>
         <input type="button" value = '1' onclick = "Solve('1')">
         <input type="button" value = '2' onclick = "Solve('2')">
         <input type="button" value = '3' onclick = "Solve('3')">
         <input type="button" value = '+' onclick = "Solve('+')">
         <br>
         <input type="button" value = '0' onclick = "Solve('0')">
         <input type="button" value = '.' onclick = "Solve('.')">
         <input type="button" value = '=' onclick = "Result()">
      </div>
   </div>
   <script>
	function Solve(val) {
    var v = document.getElementById('res');
    v.value += val;
 }
 function Result() {
    var num1 = document.getElementById('res').value;
    var num2 = eval(num1);
    document.getElementById('res').value = num2;
 }
 function Clear() {
    var inp = document.getElementById('res');
    inp.value = '';
 }
 function Back() {
    var ev = document.getElementById('res');
    ev.value = ev.value.slice(0,-1);
 }
   </script>

<style>
body {
      background-color: #171515;
      color: #ffffff;
  }

h2::before {  
  transform: scaleX(0);
  transform-origin: bottom right;
}

h2:hover::before {
  transform: scaleX(1);
  transform-origin: bottom left;
}

h2::before {
  content: " ";
  display: block;
  position: absolute;
  top: 0; right: 0; bottom: 0; left: 0;
  inset: 0 0 0 0;
  background: rgb(0, 0, 0);
  z-index: -1;
  transition: transform .3s ease;
}

h2 {
  position: relative;
  color: #39FF14;
  font-size: 1.5rem;
  font-family: Monospace;
}

p {
  font-family: Monospace;
}

html {
  block-size: 100%;
  inline-size: 100%;
}

.block-container {
    padding-top: 1rem;
    padding-bottom: 0rem;
    padding-left: 5rem;
    padding-right: 5rem;
}

@media (orientation: landscape) {
  body {
    grid-auto-flow: column;
  }
}
</style>

</body>
</html>


</html>