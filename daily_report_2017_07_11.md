# Day 11-07-2017
---------
[TOC]

## Rails validates
> We can validate inputs at a form_for when user input wrong values
> The validate not by javascript, we code it in model file

- Example validate name in user model file:
```ruby
validates	:name,	presence:	true, length: {minimum: 5,maximum: 50 }

```
+ This code mean that you cannot type name with length is shorter than 5 and longer than 50 
> We can validate many other input values like email, date, password...

- Example validate email:
```ruby
	VALID_EMAIL_REGEX = /\A[\w+\-.]+@[a-z\d\-.]+\.[a-z]+\z/i
	validates :email, presence: true, length: { maximum: 255 }, format: { with: VALID_EMAIL_REGEX }, uniqueness: { case_sensitive: false }

```
VALID_EMAIL_REGEX is a variable contain the regex that we permitted user to use: xxx.xxx@xxx.xxx and not permitted to use case sensitive.

## Partial view
> During we build a website, there are many pages, many elements that we have to use by many times, but duplicate this elements will make us spend too much time, and the web performance is not good.
> Partial view is a function help us to reduced duplicates part and web performance could be improve.
> - To use partial, we have to define the element in a partial file: _....html.erb
> - And call it by render code in main page: 
>
```htmlbars
<table class="table table-bordered">
	<thead>
		<tr>
			<th>Book name</th>
			<th>Author</th>
			<th>Publisher</th>
			<th>Description</th>
			<th>Price</th>
			<th>Book Image</th>
			<th>Option</th>
		</tr>
	</thead>
			
	<tbody>
			
		<%= render partial: "book" , collection: @books %>


	</tbody>
</table>
```
> To render a form in a partial page to main page, we create a form in _book.html.erb
```vbscript-html
<tr>
			<td><%= book.name %></td>
			<td><%= book.author %></td>
			<td><%= book.publisher %></td>
			<td><%= book.description %></td>
			<td><%= book.price %></td>
			<td><%= image_tag book.image.thumb %></td>

			<td><%= link_to "edit", edit_book_path(book) %>/<%= link_to "delete",book,  :method => 'delete' , data: {confirm: "are you sure that you want to delete book#{book.name}?"} %><%= link_to "show", book_path(book) %></td>
</tr>
```
## 

