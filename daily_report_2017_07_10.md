# Day 10-07-2017
----------

[TOC]

## JavaScript Browser Object Model (BOM)

### ![enter image description here](http://i.imgur.com/zN5R6ZZ.png)
## window
> We can do some action by this method like:
>- open a window,
>- close this window
>- close another windows
Open a window by Javascript:
```javascript
window.open('http://facebook.com','facebook',"width=200,height=100");
```
The code below will close this window:
```javascript
window.close();
```
### History
>To access browser history, We can use window.history method.
>To go back to previous page:
```javascript
window.history.back();
```
> Reload page:
```javascript
window.history.go();
```
### Navigator
> The navigator object contains information about the browser.
With navigatorr, we can get browser information like:
- appCodeName
- appName
- appVersion
- cookieEnabled
- geolocation
- language

### Screen
> The screen object contains information about the visitor's screen.

- availHeight:	Returns the height of the screen
- availWidth:	Returns the width of the screen
- colorDepth:	Returns the bit depth of the color palette for displaying images
- height:	Returns the total height of the screen
- pixelDepth:	Returns the color resolution of the screen
- width:	Returns the total width of the screen

### Document
> We can add cookie by: 

```javascript
document.cookie = "name=abc"

```
### Location
> We can get more information  about the url by this method

If you want to return hostname of website:
```javascript
window.location.hostname();
```
Or redirect to other website:

```javascript
window.location.href("facebook.com");
```
### JSON 
> JSON is a file contain record of a element in html page, we have to import this records to render it to.

>The code below is the way to import json file:

```javascript
function load_ajax(){
	var xmlhttp;

	if(window.XMLHttpRequest){
		xmlhttp = new XMLHttpRequest();
	}
	else{
		xmlhttp= new ActiveXObject("Microsoft.XMLHTTP");

	}
	xmlhttp.onreadystatechange = function(){
		if(xmlhttp.readyState == 4 && xmlhttp.status == 200){
			document.getElementById("results").innerHTML = xmlhttp.responseText;
			// xmlhttp = xmlhttp.responseText;
			// JSON.parse(xmlhttp.responseText);
		}
	};
	xmlhttp.open("GET", "../template/product.json");
	xmlhttp.send();

}

```
> After that, we can load json file and append it into a html page. 

