---
title: "pick.js"
date: 2018-01-24T12:16:26-05:00
draft: false
description: "Create a new object composed of properties picked from another object."
how: "https://gomakethings.com/how-to-create-a-new-object-with-only-a-subject-of-properties-using-vanilla-js/"
demo: "https://codepen.io/cferdinandi/pen/MzxMeE"
weight: 10
noIndex: false
---

```js
/*!
 * Create a new object composed of properties picked from another object
 * (c) 2018 Chris Ferdinandi, MIT License, https://gomakethings.com
 * @param  {Object} obj   The object to pick properties from
 * @param  {Array}  props An array of properties to use
 * @return {Object}       The new object
 */
var pick = function (obj, props) {

	'use strict';

	// Make sure object and properties are provided
	if (!obj || !props) return;

	// Create new object
	var picked = {};

	// Loop through props and push to new object
	props.forEach(function(prop) {
		picked[prop] = obj[prop];
	});

	// Return new object
	return picked;

};
```
