---
layout: post
title: Day 16 / 56
tags: learning, general assembly, ruby, backend, oop
---
@Ga_Melbourne by *Johan Codinha*.

##:gem: Programing with ~~a spoon~~ objects.

So we have been using object since day one with javascript, most of the time without realizing it. Now it's time to create our own or get a headache trying. After an emotional programming story from our instructor DT, we talked about his early experience with object oriented programming.
My first introduction to OOP was few years ago when I started learning C++ after years of using C to program microcontrollers in high school. The first time,  I got so confused about the principles behind object, then I tried again to understand the concept with another language, PhP, didn't work. Few failure later I finally get it, and I understand the confusion present in the class, I have been there. All you need to do is to  check out other learning materials, keep reading courses and experiment, until you finally get it.
I would recommend watching this [video](https://www.youtube.com/watch?v=KyTUN6_Z9TM), it's a concrete example of what object are good at.

## :dart: Every day goals :  

**Coding**, Spend most of the day building an animal shelter, *console* app that can manage the relationship between clients and animals.  
**Talking about it**, Spend the evening at an art and design conference, meet some awesome peoples, and when I told them that I was a developer, they started pitching app idea, good fun. Also here's my daily [Walk and Talk](https://soundcloud.com/johan-c-819300950/walk-and-talk-day-16-58).

## :book: TIL :  
- **OOP design** :
    - classes creation, with class Class_name, uppercase first letter to follow convention.
    - attr_accesor to acces varaiable inside obj without writing the acces funtion manually.
    - method creation, when creating a method you can set it like that `def method=(para)` and call it `obj.method = para` instead of `obj.method(para)`.
    - initialize / constructor method, `def initialize` will run when object is created for the first time.
    - instance variable, @varaiable is an instance varaiable, only accesible from the object
- **Crappy DB** : 
    - Whant to make a database in a single text file ? What could go wrong ? to open a text file in Ruby `file = File.open('crappy_database.txt', 'a+') do |file| ...some code ... end` a+ will give read/write acces and the `do |file| ... end` part will close the file for us, otherwise `file.close` when you are done with the file. 
  
**:shell: Quotes of the day :**  
>“The problem with object-oriented languages is they’ve got all this implicit environment that they carry around with them. You wanted a banana but what you got was a gorilla holding the banana and the entire jungle.” – Joe Armstrong
