# Day 04-07-2017
----------

[TOC]

## Java Scripts
> Java scripts is a programming language that we can add code into a html code.
> It can run like a application when browser is running with many functions.
> It is a object oriented programming, simple of code and non static language.
> We can write java scripts for a html file by 2 ways: add it like a scripts into html code or write a java scripts file outside of this html file and call it in html code.

### add java scripts source:
```htmlbars
<script type="javascript" src="demo.js" type="text/javascript"></script>
```

### add scripts segment
```htmlbars
<script>
    document.write("<h1>This is a heading</h1>");
</script>

```

## Java scripts variables
> Like other programming languages, js(java scripts) have variable to contain attributes.
### var variable
>Var create a variable effective during the function contain it.  

####example var variable
```javascript
function exp() {
   var x = 10;
   if (true) {
      var x = 20; 
      console.log(x);
   }
   console.log(x); 
}
```
>output:
20
20

### let variable
>let create a variable just work in block contain it.
> If we declare  let variable in for loop, if else... ,out of this construction, this let variable is not exist.
####example
```javascript
function exp() {
   let x = 10;
   if (true) {
      let x = 20; 
      console.log(x);
   }
   console.log(x); 
}
```

>output:
20
10
### const variable
>This variable is contain constant of this code. Const define once time and it not cannot change during code.
#### Example
the code below will return error because of constant just define once time.
```javascript
const A = 5;
A = 10;
```
## Function of JS
### Loops and condition expression in java scripts
>as like as other languages, js have loop and condition constructions: while, for, switch-case, if else...

###  Filter
>The filter() method creates a new array with all elements that pass the test implemented by the provided function.
```javascript
var words = ["apple", "samsung", "sony", "dell"];

var longWords = words.filter(function(word){
  return word.length > 6;
})
```
After this code done, longwords now is an array stored words of words array that have length >  6.

### forEach() method
>This method consider all member of an array and perform some code if this member pass the condition.

The code below can get name of person array.
```javascript
var person = [{name: "nguyen", age: "24"},{name: "tran", age: "25"}];

person.forEach(function(element){
	console.log(element.name)
})

```


### Confirm method
>This method return us true if user click ok or false when user click cancel.
>It is a method to confirm user before an important action perform.

```javascript
confirm("Are you sure you want tho delete this book?");
```


### Prompt method
>this method create a input on screen that user can type some thing to send to server
```javascript
prompt("input some words");
```


###Document.write method

>This method can write to html file, that mean we can add code to html by java scripts.
```javascript
while(i<=10){
	document.write(i+'</br>');
	i++;
}

```


