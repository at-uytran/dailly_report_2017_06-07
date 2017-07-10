# Day 07-07-2017
----------

[TOC]

## Ruby on Rails
### Install require gem in Rails project
> To install gems that you want to use in a Rails project, you have to define it in Gemfile in vendor folder.
> After that, you run bundle install command at terminal to install this required gem
```
bundle install
```
### Create controller
> To create a controller, run rails  g controller controller_name
```
rails g controller users
```
### Create model
> To create a model, run $ rails g model model_name
```
rails g model users
```

### Routes for project
> When user want to send request to server, this request have to direct by a true way. file routes.rb in config folder have to do this work. 

In this file, we have to define action and method like the code below:
```ruby
get "users" => 'users#index'
```
This mean that when you type  /users in browser url, the action that users controller have to transform index action
But this is an old way to define a action, with rails, we can define by use resources:

```ruby
resources :users
```

it's equivalent by

```ruby

  get "users" => 'users#index'
  get "users/new" => 'users#new'
  get "users/:id" => 'users#show'
  get "users/:id/edit" => 'users#edit'
  post "users" => 'users#create'
  put "users/:id" => 'users#update'
  delete "users/:id" => 'users#destroy'

```
And when we want to select some actions not by all of the actions above:

```ruby
resources :users, only[:index, :new, :update]

```
>After all of this, you have to apply this change by:
```
rails routes
```
### Member
### Collection
###  Create a database
> There are 3 databases of a rails project:
> - Developer
> - Test
> - Main database

> We can config the database that we want to work with in database.yml file in /config folder

### Create a tabe
> We can create a table with some additional column like timestamp and auto increase id by describe in db/migrate/create_users.rb

```ruby

def change
    create_table :users do |t|
    	t.string :name
    	t.string :email
    	t.datetime :birthday
    	t.integer :gender
    	t.text :password
    	t.text :user_name

      t.timestamps
    end
  end
```


After that, run in terminal: 

```
rails db:migrate
```

To rollback to previous version of database, use:

```
rake db:rollback STEP=1
```

### Send attributes to Views

>When render a erb file to html, we have to send attributes for this page:
```ruby
@users = User.all
```
this code set @users is a hash of all users have in database.

### Use the attributes in an erb file

to embed code ruby in erb file, type code between ''<%='' and ''%>''
The code below is a embed code in erb file:
```vbscript-html
<% @users.each do |user| %>
	<td><%= user.name  %></td>
	<td><%= user.email  %></td> 
	<td><%= user.birthday %></td>
	<td><%= user.gender %></td>
	<td><%= user.password %></td>
	<td><%= user.user_name %></td>
</tr>		
	<%end%>
```

### Embed a link
> Link in a erb file like the code below:
```html
<%= link_to 'New user' , new_user_path %>	
```
> To link to a action
```vbscript-html
<%= @users.each do |user| %>
<%= link_to 'delete', user, :method => 'delete' %>
<% end %>
```
> By another way:
> Prefix link is showed when we rub routes command and we can use this prefix to link to a action:

         Prefix Verb   URI Pattern                Controller#Action
          users GET    /users(.:format)           users#index
                POST   /users(.:format)           users#create
       new_user GET    /users/new(.:format)       users#new
      edit_user GET    /users/:id/edit(.:format)  users#edit
           user GET    /users/:id(.:format)       users#show
                PATCH  /users/:id(.:format)       users#update
                PUT    /users/:id(.:format)       users#update
                DELETE /users/:id(.:format)       users#destroy
          books GET    /books(.:format)           books#index
                POST   /books(.:format)           books#create
       new_book GET    /books/new(.:format)       books#new
      edit_book GET    /books/:id/edit(.:format)  books#edit
           book GET    /books/:id(.:format)       books#show
                PATCH  /books/:id(.:format)       books#update
                PUT    /books/:id(.:format)       books#update
                DELETE /books/:id(.:format)       books#destroy


### Form for

> A form is submit inputs by button
> Form for in erb  is define like  the code below:

Form add a user:
```vbscript-html
<%= form_for :user , :url => {:action => 'create', :method => 'post'} do |f| %>
      
      <%= f.label :name %>
      <%= f.text_field :name %><br>

      <%= f.label :email %>
      <%= f.email_field :email %><br>

      <%= f.label :birthday %>
      <%= f.datetime_local_field :birthday %><br>

      <%= f.label :gender %>
      <%= f.text_field :gender %><br>

      <%= f.label :password %>
      <%= f.password_field :password %><br>

      <%= f.label 'user name' %>
      <%= f.text_field :user_name %><br>


    <%= f.submit "Create user" %><br>

<% end %>

```
