Monday
-database intro
mixing up data and code is hard, confusing. So we should separate them.
crappy db structure ? their is no, just text in a text file
2 kind of database, noSQL and SQL (relational)
first let's install postgresql

get something you do a reading with , select
update something you do an modification with, update
insert a new records with Insert
delete with delete

-relational database
-tables, rows, column
 (the db, records, attributes)
-sql

Lets create a web app to share picture of dishes: goodfoodhunting
let's create a new sinatra app with sinatra new goodfoodhunting -va

-v views to generate views folder with index.erb and layout .erb
-a asset to generate public, javascript and stylsheet folder

to help us talk to the database we are using the gem 'pg' (gem install pg)
db = PG.connect(dbname: 'goodfoodhunting') to create a connection
row = db.exec('select * from dishes;')
now row is a hash, so i just row[0] to retrieve data.

how to convert to utf-8
string = 'é'
encoded_string = string.encode('UTF-8')
encoded_string.bytes => [195, 169]
string = ''
encoded_string.bytes.each {|byte| 
    string << "%#{byte.to_s(16)}"
}

def to_utf (str)
    encoded_str = ''
    str.split('').each {|char| 
        encoded_char = char.encode('UTF-8')
            encoded_char.bytes.each {|byte|
                encoded_str << "%#{byte.to_s(16)}"
            }
    }
    return encoded_str
end
