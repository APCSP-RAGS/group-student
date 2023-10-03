---
layout: default
title: RAGS Group Blog
---


<html>

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

body {
  min-block-size: 100%;
  min-inline-size: 100%;
  margin: 0;
  box-sizing: border-box;
  display: grid;
  place-content: center;
  font-family: system-ui, sans-serif;
}

.block-container {
    padding-top: 1rem;
    padding-bottom: 0rem;
    padding-left: 5rem;
    padding-right: 0rem;
}

/* @media (orientation: landscape) {
  body {
    grid-auto-flow: column;
  }
} */
</style>


<body>

<h2>About Me</h2>
<p>We the RAGS Group are a group of coders that want to learn things such as the coding development process, how to debug, and learn different languages such as javascript and html. So far, we have learned: </p><br>
<ul>
<li>Debugging JS Code</li>
<li>Having HTML interact with JS code</li>
<li>Learning JS Data Types</li>
<li>Learning HTML formatting for front-end dev</li>
</ul>
<br>
<h2>Special Shoutout</h2>
<p>One of our favorite albums(and album covers): <br>
Wish You Were Here - Pink Floyd <br></p>
<a href="https://www.youtube.com/watch?v=Y9LU0utKCSw&list=OLAK5uy_mzowhqljIOba8BVGEmVkeaWeL2S_bO4bw" target="_blank"><img src="wishyouwerehere.jpg" width="300"></a>
