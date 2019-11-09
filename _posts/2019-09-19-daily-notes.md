---
layout: post
title: 'Daily Notes: September 19, 2019'
description: The Console API and Semantic HTML
tags: [daily, html, js, console]
---

### The Console API

_**Use the appropriate type of console write.**_ I came across an article that pointed out the alternatvies to console.log(). Here are some that I think would be helpful:

```js
console.assert(true, 'Will write if false'); // Will only print if the first arg is false.
console.table({ firstName: 'Matthew', lastName: 'Petrus' }); // Prints a pretty table of the object key:value pairs. console.time("Timer 1");
console.timeEnd('Timer 1'); // Prints the time elapsed between calls "Timer 1: 20ms"
```

Found on reddit, linked from (htt://levelup.getconnected.com).

### Semantic HTML

_**The article element is higher level than a section.**_ When writing the HTML layout, an article element should be a higher level element to delimit a "component" of the page; a piece that could stand on its own (ie. an article of clothing). Here are a few other highlights:

- The section element is used within an article.
- You should "pre>code" to maintain formatting when giving code examples.
- Use the ul>li for nav links.
- Buttons are for actions, links are for resources.
- b elements replace span for styling purposes.
