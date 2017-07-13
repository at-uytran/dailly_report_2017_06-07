# Day 13-07-2017
---------
[TOC]
## Model
### Validates 
> Validates have 3 layer, the first layer:
>- Validate at website by javascript, 
>- Validate at model by dependent bare 
>- Validate at database by set up the obligatory values
If we want to validate that when user create an account, they have not to care about name length, and we just validate on update.
```ruby
validates	:name,	presence:	true, length: {minimum: 5,maximum: 50 }, on: :update


```
### Reset all database
> We can reset database if we want to reset all table to the new mode

```
rails db:migrate:reset
```
###  Fake database
> We can create fake rows of a table by a gem named Faker.
> First we have to install a gem named Fake gem

And in file seeds.rb:
```ruby
10.times do |i|
	User.create(name: "Uy #{i}")
end
```

After this code, we have 10 fake users in User

### Role values to set admin or members 
> In a website, we have to set roles to members, admin and moderator.
> Set default of role is member, values is 0, moderator is 1 and admin is 2.


In fle migrate create users in db/migrate:
Create role column and set default is 0
```ruby
    create_table :users do |t|
    	t.string :name
    	t.string :email
    	t.datetime :birthday
    	t.integer :gender
    	t.text :password
    	t.text :user_name
		t.text :image
		t.integer :role, default: 0
end
```
In model/users.rb file:

```ruby
 	enum role: ['member','mod','admin']

```

When we create a row and not set role, the default show value is member.

