Today
    -Relationships / association

    -data modeling
    -one to one
    -one to many
    -many to many
    -adding relationships to goodfoodhunting
let's add a comments fonctionality

til
drop down menu with ruby


this is a way to keep track of many object are created by the class
``` ruby
class Car
  @@counter = 0
  
  def initialize
    @@counter += 1
  end

  def self.counter
    @@counter
  end
end
```
