Today Day16
*my object story
	FISH and family, sad story

*OOP / design
	classes creation
	attr_accessor to acces variable inside obj
	method creation

*abstraction
	if i ask an object for a value, i dont care if it grab it form a database ot look for it in a crappy text file, this is abstraction, using function to absctract concept
*data & behavior modeling

*classes & instances

*instance variable
	@varaiable is an instance varaiable, only accesible fron the object
*initialize / constructor method
	def initialize
	end
	will execute when creating an object for the first time.

*getters & setters
	attr_accessor :name, :age, :gender
	attribute accesor will make ruby write read and write function for you
	you can always do it the long way : 

	def name=(new_name) # = sign so that you can call it obj.name = ? instead of obj.name(?)
		@name = new_name
	end

*poor man/womand's database
	file = File.open('crappy_database.txt', 'a+') do |file|
	end

