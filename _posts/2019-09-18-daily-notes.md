---
layout: post
title: 'Daily Notes: September 18, 2019'
description: The Fetch API and Meta Tags
tags: [daily, html, js]
---

### Figuring out Fetch

_**When creating a simple Node/Express API, be sure to set the CORS Headers to allow the origin and header.**_ I had set the 'no-cors' header on the Fetch request, but the Fetch action kept returning an error while parsing the JSON body of the response. This error was caused by receiving a null body. The browser was allowing me to make an 'opaque' request which returned a null body. By adding the below to the Node/Express server, and removing the 'no-cors' header from the Fetch options, the action worked as intended.

~~~
app.use(function(req, res, next) {
    res.header('Access-Control-Allow-Origin', 'YOUR-DOMAIN.TLD'); // update to match the domain you will make the request from
    res.header(
    	'Access-Control-Allow-Headers',
    	'Origin, X-Requested-With, Content-Type, Accept'
    );
    next();
});
~~~

Reference: [CORS on ExpressJS](https://enable-cors.org/server_expressjs.html)

### The Importance of Meta

_**When writing a new HTML doc, be sure to include the viewport meta tag.**_ I was testing out a new HTML layout using Chrome Devtools, but all of the text was incredibly small. The zoom was correct and the the different device settings weren't having an effect. On investigation, Chrom showed the width of each element at 980px which is far larger than the 320px selected. By entering the following meta tag into the head, the text displayed properly.

~~~
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
~~~
