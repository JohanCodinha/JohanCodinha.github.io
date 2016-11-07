---
layout: post
title: Day 19 / 56
tags: learning, general assembly, ruby, backend, oop, sinatra
---
@Ga_Melbourne by *Johan Codinha*.

##:gem: Long ass code along day.

Today felt like the learning curve accelerate, the all class pool knowledge and idea together with the instructor to build a picture sharing website, a simple CRUD app, where users could create edit browse and delete content.
To be able to put everything together we used everything we learned so far, from HTTP methods to CSS. It's build with ruby using the sinatra framworks and the standart and good practice in mind.

## :dart: Every day goals :  

**Coding**, between the warmups exercice and the making of our CRUD app, I spend most of my time editing text, you can check out the code of my app on github.  
**Talking about it**, another day, another [Walk and Talk](https://soundcloud.com/johan-c-819300950/walk-and-talk-day-19-58).

## :book: TIL :  

- URL design
    restful convention 

- http verbs/methods (get post put patch,...)
    -get should only be use to fetch data that wont have effect on the server
 
- Pro tips : 
    `raise var.inspect`  will **create** an error to pause the programe and display the variable
- CRUD apps :

<table>  
    <tr>
        <td><strong>CRUD</strong></td>
        <td><strong>Sql</strong></td>
        <td><strong>Http</strong></td>
    </tr>
    <tr>
        <td>Create</td>
        <td>Insert</td>
        <td>post</td>
    </tr>
    <tr>
        <td>Read</td>
        <td>Select</td>
        <td>get</td>
    </tr>
    <tr>
        <td>Update</td>
        <td>Update</td>
        <td>put/patch</td>
    </tr>
    <tr>
        <td>Delete</td>
        <td>delete</td>
        <td>delete</td>
    </tr>
</table> 

**:shell: Quotes of the day :**  

>"As a person, I was born to give out my opinions. By giving out my opinions, I realize who I am." - Ai Weiwei 