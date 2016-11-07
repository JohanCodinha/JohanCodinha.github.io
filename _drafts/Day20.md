---
layout: post
title: Day 20 / 56
tags: learning, general assembly, backend, ruby, sql, active records
---
@Ga_Melbourne by *Johan Codinha*.

##:gem: Learn the hard way, after that everything seems easy, or not.

It's time to say 'good bye Sql' and let it rest backstage, today we are adding a level of abstraction to our database queries by using [Active Record](http://guides.rubyonrails.org/active_record_basics.html). This tool is giving us the abilities to perform database operation with an object-orientated syntax. It doesn't required much configuration but to achieve that it required that you follow naming convention.

## :dart: Every day goals : 

**Coding**, does Sql queries count as writing code ? Active records sure does.
**Talking about it**, while walking, otherwise it's too easy,[Walk and Talk](https://soundcloud.com/johan-c-819300950/walk-and-talk-day-20-58).

## :book: TIL :  

Good buy SQL day
    -relational database
    When you want to talk a relational db, you have to use sql,
    to learn more about sql, sqlzoo
    can we skip sql ? 
    -sql joins

    -associations
    -ORM (magical)
    object relation mapping
        -Active record
        -table definition -> class
        single row of record -> instance

so active record know that by convention, a class Dish will link to the table dishes, same for class DishType link to the table Dish_types, magic.

active records maps to object so i can use object notation

you can see witch sql command is beeing run by active record by adding .to_sql !

`ActiveRecord::Base.logger = Logger.new(STDERR)` into the console file to display the querry.

`has_many :dishes` in the class DishType do describe the relation between the tables, in this case our dish type corresdpond to different dishes

`belong_to :dish_type` in the class Dish because every dishes belong to a dish type
naming convetion : 
Database Table - Plural with underscores separating words (e.g., book_clubs).
Model Class - Singular with the first letter of each word capitalized (e.g., BookClub).
docu -> http://guides.rubyonrails.org/active_record_basics.html
