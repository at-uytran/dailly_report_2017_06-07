
# Day 06-07-2017
----------

[TOC]


## JavaScripts Document object model(DOM)
>- DOM is an API using to access document element in html page.
>- When a web page is loaded, the browser creates a Document Object Model of the page.
>- DOM model is constructed by a tree of objects

![enter image description here](https://www.w3schools.com/js/pic_htmltree.gif)
### Function
> Function in JavaSccripts is a part that we can call to complete some action.
```javascript
function square(x){
 	return x*x;
}
```
#### Define function in function
>We can define function inside of a function. but we can't call it outside this function.
```javascript
function addSquare(x){
	function square(x){
	return x*x;
	}
return square(a)+square(b);	
}
```
### Finding html Elements
>DOC can help us find elements.
#### Get element by Id

```javascript
var x = document.getElementById('idName');
```
#### Get elements by tagName
```javascript
var x = document.getElementsByTagName('tagName');
```
#### Get elements by className
```javascript
var x = document.getElementsByClassName('tagName');
```
### Changing html Elements
>We can change elements by using the methods below:
#### Add contents by innerHTML
```javascript
var x = document.getElementById('idName');
x.innerHTML = <p>this is inner html</p>;

```
#### Set attributes
```javascript
var x = document.getElementById('idName');
x.setAttribute(attribute,value);

```
#### Style for elements
```javascript
var x = document.getElementById('idName');
x.style.color = 'red';

```
### Add - Delete elements
>We can add and delete elements in html page
#### Create Elements
```javascript
var create = document.createElement('div');
create.innerHTML = <p>New html</p>
```

#### AppendChild
```htmlbars
<ul id="myList">
  <li>Pepsi</li>
  <li>Sting</li>
</ul>
<script>
	var a = document.getElementById('myList');
	var b = document.createTextNode("Cocacola");
	a.appendChild(b);
</script>


```
#### Remove elements
```javascript
item.removeChild(ul.li[0]);

```

### EventListener
```javascript
var x = findElementById('click me!');
x.addEventListener('click', function(){
    document.getElementById("click").innerHTML = "Hello World";
 });
```





---------------------------------------



