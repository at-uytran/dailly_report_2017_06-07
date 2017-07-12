# Day 12-07-2017
---------
[TOC]


## Javascript
### Object method
> In javascript, methods is actions that object can do
>

```javascript
var person = {
    firstName: "David",
    lastName : "Joe",
    fullName : function() {
       return this.firstName + " " + this.lastName;
    }
};
```
And call this method:
```javascript
var name = person.fullName();
```

### Object Prototype
> Prototype of a object is a instance, every instance have many different action and many properties.
> There are many ways to define a prototype:


```javascript
var Person = function(firstname){
	this.firstName = firstname;
}
var john = new Person("John")
console.log(john);
```
Now lets define a prototype for Person class:

```javascript
Person.prototype.sayhello = function(){
	console.log("Hello, I'm "+ this.firstName);
}
```

Person class now have prototype named sayhello 
```javascript
john.sayhello();
// => Hello, I'm John
```

### Private and public variables 
> A instance have many properties, and many of them should be security.
```javascript

function a(){
	var hobbies = 'fishing'; // this property is private
	this.name = 'John';  //this property is public
}
```

### Constructor
> when we want to initialize values for object

```javascript

function Person(first, last, age, eyecolor) {
    this.firstName = first;
    this.lastName = last;
    this.age = age;
    this.name = this.firstName + this.lastName;
}
```



