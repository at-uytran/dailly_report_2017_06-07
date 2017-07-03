
# Day 03-07-2017
----------

[TOC]

## Ruby on Rails
>A project of Ruby on Rails have a lots of functions, highlights of this functions are 3 folders of project - models, views and controllers. Rails create this help us have a overview of a project and that make us easier to work with.

### Models folder
> This folder store code for connect to database and communicate with it.
> A project just work with a type of database manager system
### Controllers folder
>This folder contain code of controller files - which control all main activities of a Rails project.
>Some example of this activities are receive all request of user, then send command to models - this make change database. Send link or set attributes to erb files to render views...

### Views folder
> This folder contain erb or another file type which can receive attributes, render views...
> This folder make what we can see in browser.

![Alt text](./image_thumb3.png)

### Gemfile
>Rails project have a file named Gemfile. It store project gem information - which gem we were use, which gem for developer, which for test and for customer.-

### images folder
>app/assets/images: contain static images of project like logo, banner... we shouldn't make change at this folder


### database.yml file
>Contain in config folder. This file configuration about database manager system.
>This file configuration some database for us check on developer mode or test database before apply to main database.
>It is a helpful function when we are not sure about our database and we want to make a backup for test of database.

### locales yml file
>config/locales/en.yml this file contain code make project can compatible with many languages. en.yml  is a file config for English, if we want to compatible with another language, we should make more files in this folder.


### seed files
> db/seed.rb: this file can make a fake database for us. and you have not to create database by query.



