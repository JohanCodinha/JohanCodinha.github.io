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

`belong_to :dish_type` in the class Dish because every dishes belong to a dish type.

docu -> http://guides.rubyonrails.org/active_record_basics.html
