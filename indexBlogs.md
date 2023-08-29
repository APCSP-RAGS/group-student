---
layout: blogs
permalink: /blogs
title: Blogs
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
  font-size: 1rem;
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
    padding-right: 5rem;
}

@media (orientation: landscape) {
  body {
    grid-auto-flow: column;
  }
}
</style>


</html>