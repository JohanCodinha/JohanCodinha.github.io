##Better looking goodfoodhunting
##MVC
##Migrations (database)
##helpers
##the sharing os caring web

Let's create a new goodfood hunting : 
`rails new goodfoodhunting --database=postgresql -T`
-T not to generate testing code, we want to do it manualy
`rake db:create` is a script that will create a db base on your config file

we want to create a table in the db called dishes with two colloumns: name and image_url
`rails generate model dish name:string image_url:text`
it create two files, that can be run to create our database
then run
`rake db:migrate`
we can check that everything s working by going to the rails console
and check our newly created table.
`Dish.all.size` = 0
`Dish.create(name: 'birthday_pudding', image_url:'http://3.bp.blogspot.com/-yTIhH5Zp630/UTg5rvJOzLI/AAAAAAAABII/KJsH8MlY2Bc/s1600/Banana+Pudding+Cake+Recipe+2.jpg' )`
`Dish.all.size` = 1

edit routes.rb
`get '/' => 'dishes#index'`
create a dishes_controller.rb
`class DishesController < ApplicationController
    
end`
refresh and you can see the index is not found for the DishesController
let's create it by adding the following inside our class DishController
`   #automagically looks for a template with the same name as the method
    def index
        
    end`

now create a foler called dishes in the views folder
create a file called index.html.erb
refresh and a beautifull white page should appear, congrat your winning !

now let's write some html in index.html.erb
`<h1>goodfoodhunting</h1>`

now let's display our dishes on that page
`<% @dishes.each do |dish| %>
    <p><%= dish.name %></p>
    <img src="<%= dish.image_url %>" alt="">
<% end %>`

Rails is complaigning, it doesnt know what is @dishes to let's help hin on that.
go to the dishes_controller.rb page and add the following line in the index method: 
`@dishes = Dish.all`

refresh the page and as you can see our image is way too big so let's add some css.
let's create a style.css in goodfoodhunting/app/assest/stylsheets
and specifie a new rule for image: 
`img {
    max-width: 100px;
}`

let's create more routes in our routes.rb file : 
`get '/dishes/new' => 'dishes#new'
  post '/dishes' => 'dishes#create'`
and let's update the dishes_controller.rb file : 
`   def new
    end

    def create
    end`

now let's create a new file with a form to post new dishes, called new.html.erb in our views/dishes folder : 
`<form action="" method="post">
    
    <label for="">name</label>
    <input type="text" name="name">

    <label for="">image_url</label>
    <input type="text" name="image_url">

    <button>create</button>
</form>`
 you can now browse to /dishes/new and see the new form

 we need to give a security token when passing on form for security reason by adding a hidden field in our form : 
 `  <%= hidden_field_tag :authenticity_token,
    form_authenticity_token %>`

now let's refresh the form and try to create a dish, it failed beacause it doesnt now what to do with a post request to /dishes, so let's create the logic behind it : 
in our dishes_controller.rb in the create method => 
        `dish = Dish.new
                dish.name = params[:name]
                dish.image_url = params[:image_url]
        
                if dish.save
                    redirect_to '/'
                else 
                    render :new
                end
        `

now let's add some rule on what information can be entered in the form : 
in our dish.rb file in models folder let's add the following inside our Dish class : 
`   validates :name, length: {
        minimum: 3 }`
now if you go in a rails console and try to create a dish with a name less than 3 character.
`pudding = Dish.new`
`pudding.name = 'ck'`
`pudding.valid?` => false
`pudding.save` => false

now let's create mor functionality 
lets make a page to visualize a single dish
add a new route to routes.rb : 
`get '/dishes/:id' => 'dishes#show'`

then let's wrtie some code in our controller.rb to do something when users go to that url. We just add a new method to our DishController class called show: 
`   def show
        @dish = Dish.find(params[:id])
    end`
now let's create a show.html.erb file in our views/dishes folder :
`<%= @dish.name %>`

now we can browse to dishes/1 to see the name of the first dish

let's create a new page to edit our dishes, to start, ounce again we add a new route to our routes.rb file : 
`get '/dishes/:id/edit' => 'dishes#edit'`
then create a method in our DishesController class in dishes_controller.rb file : 
`   def edit
        @dish = Dish.find(params[:id])
    end
`
now that the route is up and runnig and that our controller knows what to do when users request this url we just need to create the html page called edit.html.erb (because the name is the same as our method described in our dushes_controller.rb file, rails know that it need to load this file without telling him to do so)

Now let's create the form to edit our dish : 

`<form action="/dishes/<%= @dish.id %>" method="post">
    <%= hidden_field_tag :authenticity_token,
    form_authenticity_token %>

    <label for="">name</label>
    <input type="text" name="name" value="<%= @dish.name %>">

    <label for="">image_url</label>
    <input type="text" name="image_url" value="<%= @dish.image_url %>">

    <button>update</button>
</form>
`

now we can browse to /dishes/1/edit and see our form with value displayed in our input form. if we click update we got a new error, rails doesn't know yet what to do with a post request to /dishes/id.

So lets create a route : 
`post '/dishes/:id' => 'dishes#update'`

then a update method in our controller : 
`   def update
        @dish = Dish.find(params[:id])

        @dish.name = params[:name]
        @dish.image_url = params[:image_url]

        if @dish.save
            redirect_to '/'
        else
            render :edit
        end
    end`

now when you submit the form, if the change are allowed (name is over 4 character long), the databe will be updated with new data.

now let's create a page that will delete our dishes when requested
start with the route: 
`  delete '/dishes/:id' => 'dishes#destroy'`

let's add a link to this url on our show page, we will create a form to do that : 

`<form action="/dishes/<%= @dish.id %>" method="post">
    <input type="hidden" value="delete" name="_method">
    <%= hidden_field_tag :authenticity_token,
    form_authenticity_token %>

    <button>delete</button>
</form>`

now when we browse to /dishes/1 we can see the delete button, when clicked it give us an error, the action is not found in controller.
So let's create a new method in our controller called destroy : 
`   def destroy
        @dish = Dish.find(params[:id])

        if @dish.destroy
            redirect_to '/'
        else
            render :show
        end
    end`

Now when /dishes/1 is visited and the user click delete, if the action doesnt fail the user should be redirect to '/'

###Let's add different dishes type to our app
So i know what i want, a simple table called dish_types with a name collums.
First we are going to create the model of our table.
`rails g model dish_type name:string`

this generate two files that will be use to create our table.
Now let's generate the table by typing: 
`rake db:migrate`

we can now get on our rails console to check that everything is working by typing:
`DishType.all`

Now let's create a page that will display all the dish types.
First we create the route :
`get '/dish_types' => 'dish_types#index'`

As you can see we are routing into dish_types instead of dishes, so we need to create a dish_types controller.
first let's create a file called dish_types_controller.rb in our controllers folder

Then create a class called DishTypesController and define a method called index: `class DishTypesController < ApplicationController
    def index
    end
end`

now we need to create a view called index.html.erb in a folder called after our new class, dish_types.

To display every dish types in the db just drop the following code un the index.html.erb file that is inside dish_types folder : 
`<h1>goodfoodhunting</h1>
<h2>Dish Types</h2>

<% @dish_types.each do |type| %>
    <p><%= type.name %></p>
<% end %>`




resources :dish_types to create the routing automaticly, like attr_accesor in ruby

Now we woud like to add a relation between our database, we need to ad a collumns dish_type_id to our dishes table:
`rails g migration add_dish_type_id_to_dishes dish_type_id:integer`

so this generated a new migration file that will add up an extra collumns to our dishes table. Now let's run the migration file by typing :
`rake db:migrate`

Now we need to specified the relationship between our two table.
let's add the following to dish.rb
`belongs_to :dish_types`
and the following to dish_type.rb
`has_many :dishes`

Now we can check if everything is working by typing the following in a rails console : 
DishType.first.dishes

different way to create link.
<a href="/dish_types/<%= dish_type.id %>/edit">edit</a>
<%= link_to 'edit', edit_dish_type_path(dish_type.id) %> 
#you can found the path in the rails/info/routes page of your app.
or you can do :
<%= link_to 'show', [:edit, dish_type]%>

if you want to create a link to show a specific item : 
<%= link_to 'show', dish_type %>

_______
rake db:create -> create new db
rake db:drop -> delete db
rake db:migrate -> running migration
rake db:rollback -> reverse the last change made

use pry-byebug to add step by step debugging

https://gist.github.com/LJKenward/5b79366bfe06e76fc5fb6a9eef29c4a3

"no message is good message"