---
layout: post
title: "Daily Notes: March 10, 2020"
description: Function Execution
tags: [daily, html, js, bind]
---

### Indirect vs Direct Function Execution

_**Use bind() to "pre-configure" the context and the parameters.**_ Brad with Academind pointed out that new programmers often make the mistake of directly entering the callback function of an eventlistener like so:

```
htmlElement.addEventListener('click', setActive(element.id))
```

This is incorrect as it will cause the callback function to be executed when the file is loaded. Whatever is returned from that function will be what is called when the event is fired. Instead we could define a new function that calls the desired function, or use a bind to set the context. See here:

```
htmlElement.addEventListener('click', function () {setActive(element.id)})
is equivalent to
htmlElement.addEventListener('click', setActive.bind(null, element.id))
```

The first argument in bind() is the context (the 'this') within the function; the second argument is the first parameter that will be passed to the function. Further arguments to bind are passsed to the function as additional parameters.

Learned from Academind on Youtube.
