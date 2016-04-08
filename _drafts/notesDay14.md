Today
- hashes
    to get back information from hash use array[] notation,
    hash is basicly an array but you can name the index
    why would you use hash [:str = 'hello'] instead of an array with a string as index like ['str' = 'hello'] ? 
    Because if you use a string as index, everytime you are gonna call a method on it, it will create a new object, using a symbol will reuse the same, that way we use less memory, so it's about perf.

    { name: 'bart'} AND { :name => 'bart'} is the same thing,
    both are hash with symbols, just a different notation.

- Json
    

- enumerables

- classes & methods ? (methods is functions attached to an obj)
`method?` with a '?' at the end of the name, means that the methods return a boolean.


use .each when you have a collection, that way you dont have to count
in Ruby you can count backward with index, so [-1] means last index

require ' fileutils' to manipulate the file system, like create directories, move them ect..

99 design speacker : 
book :  code complete 
        pragramtic programer 
        release it

when choosing technologies, would it actualt solve the job ? 

before building a backend website we need to understand the web

