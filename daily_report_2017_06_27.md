
# Day 27-06-2017
----------

[TOC]

## MVC 
>MVC is acronym of Model - View - Controller. With MVC we can improve our code system by group code by 3 group. 
>- View: it's a component that communicate with user, when user make a request to server, it will receive by Controller. 
>- Controller: receive request from user and redirect some request to model.
>- Model: communicate with database as insert, delete update or select...
>
### Request
>In html Form or link, we cans send a request to system by Button, Server if receive this request match. something can perform.

#### Get method
>get method is a method that we can see it at url input of browser.
>When we type a url in browser, it's a get request

if we use the form below, name will be visible on url when we submit by button
```htmlbars

	<form action="/insert" method="get">
		<input type="text" name="name"><br>
		<button type="submit">Them</button>
	</form>
```
#####  Parameters
> by using url, we can send a parameters to server. 

this code will receive id of book, query in database and store it to array results.
After that, redirect website to edit page
```ruby
	get '/book/edit/:id' do
		@results = client.query("SELECT *  FROM book WHERE id = #{params[:id]}")
		erb :edit
	end
```
##### send attributes to view
this code will show the array that we were store
```htmlbars
<table title="book information">
	<tr>
	    <th>Id</th>
	    <th>name</th> 
	    <th>nxb</th>
	    <th>author</th>
	</tr>
	<tr>
	  <% @results.each do |row|%>
	    <td><%=row['id'].to_s%></td>
	    <td><%=row['bookname'].to_s%></td> 
	    <td><%=row['nxb'].to_s%></td>
	    <td><%=row['author'].to_s%></td>
	    </tr>
	<%end%>
</table>
```
#### Post
>opposite with get method, if we use post method, user can'nt see what user send to server

using method post 
```htmlbars
<form action="/insert" method="get">
		<input type="text" name="name"><br>
		<button type="submit">Them</button>
</form>
```
#### Delete and  Put method
>some other way to send to server by PUT and DELETE, we can update or delete information, but the most population are GET AND POST
### ERB file
>html is a static web view, with ruby, if you want to work with variable of a ruby code on a web page, you have to use erb file. When server is running, erb file will render to html file and browser can view it to user.
### Config file
>in mvc, run config file by using:
```
rack config.ru
```
this code will run class MyApp 

```ruby
#file config.ru:

require 'sinatra'
require "pry"
require "./my_app"

run MyApp
```
>we can change to port 3000 by using:


```
rack up -p 3000
```

