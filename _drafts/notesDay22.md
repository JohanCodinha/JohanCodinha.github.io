Friday

No users no money, let's learn authentification

storing sensible data

#look up of email is in db, do not tell client about this informationc
user = User.where(email: 'abc.xyz') this return a collection
user = User.find_by(email: 'abz.wyz') this return a single items

user.authenticate('password')

It's already been two weeks since we started the back-end part of the course, What have we learn so far ? I can tell for my self that I'm now able to build a CRUD app using ruby with the sinatra framworks and a postgres database using SQL queries or active record. The last brick missing to be able to make millions by copying facebook or flickr was to take care of users authentification and be able to keep track of their session. So today this is the subject we tackle and implemented it back into our photo sharing app.
Few weeks ago I signed up for a hackaton, Techfugees, It's taking place during the week end and the introduction was tonight. After meeting almost everybody involved we split into groups of 5 to 7 to think about how technologies could improve the life of the poeple that are fleewing war to settle in Australia.
