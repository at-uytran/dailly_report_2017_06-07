
# Day 26-06-2017
----------

[TOC]

## SCSS
>SCSS is a file  as synchronize with css file, it's a way that make us be easier to code css for a website, code will be clearly and smarty.
>
>With SCSS, we can use variables to store color, width, height or another properties.
>
>Moreover we can write code shorter, it's look like we code with a class, all child members are styled inside their group.
### Variables
>variable is save a property, and we can call it in our css  file.

```scss
$body-color: #fff;

```
and use it for another tag.
```scss
div{
	color: $body-color;
}
```

### Nesting
>In scss, we can write  code like a class with child component inside it.
```scss
nav{
	ul{
		color: #000;
		border-top: 1px solid black;
	}
	li{
		color: #fff;
		display: inline-block;
	}
}
```
### Import an another scss file
>we can import another scss file into a file. By using @import 'file_name'

file leftmenu.scss:
```scss
ul{
	padding-top: 10px;
}
```
file base.scss:

```scss
@import 'leftmenu';
ul{
	background-color: solid black;
}

```

### Mixins
>in scss, we can use Mixins as same as a function.
>when we want to use, we can call it and input it a variable.

```scss
@mixin border-radius($radius) {
  -webkit-border-radius: $radius;
     -moz-border-radius: $radius;
      -ms-border-radius: $radius;
          border-radius: $radius;
}

.box { @include border-radius(10px); }
```

Now  the .box code will look like this:
```scss
.box{
  -webkit-border-radius: 10px;
     -moz-border-radius: 10px;
      -ms-border-radius: 10px;
          border-radius: 10px;
}
```

### Exend

>extend in scss look like oop code.
```scss
.message {
  border: 1px solid #ccc;
  padding: 10px;
  color: #333;
}

.success {
  @extend .message;
  border-color: green;
}
```
