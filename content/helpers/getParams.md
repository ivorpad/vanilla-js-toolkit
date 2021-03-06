---
title: "getParams.js"
date: 2018-01-24T12:16:26-05:00
draft: false
description: "Get the URL parameters from a query string."
how: "https://gomakethings.com/getting-all-query-string-values-from-a-url-with-vanilla-js/"
demo: "https://codepen.io/cferdinandi/pen/PVwwpZ"
weight: 10
noIndex: false
---

```js
/**
 * Get the URL parameters
 * source: https://css-tricks.com/snippets/javascript/get-url-variables/
 * @param  {String} url The URL
 * @return {Object}     The URL parameters
 */
var getParams = function (url) {
	var params = {};
	var parser = document.createElement('a');
	parser.href = url ? url : window.location.href;
	var query = parser.search.substring(1);
	var vars = query.split('&');
	if (vars.length < 1 || vars[0].length < 1) return params;
	for (var i = 0; i < vars.length; i++) {
		var pair = vars[i].split('=');
		params[decodeURIComponent(pair[0])] = decodeURIComponent(pair[1]);
	}
	return params;
};
```