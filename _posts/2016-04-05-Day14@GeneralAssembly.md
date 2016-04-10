---
layout: post
title: Day 14 / 56
tags: learning, general assembly, ruby, backend
---
@Ga_Melbourne by *Johan Codinha*.

##:gem: The natural syntax of Ruby

Ruby follow the principle of least surprise, this only applies if you are familiar with at least one other programming language. If so, your learning curve will be minimized by reusing existing knowledge. Ruby syntax is intuitive, I want to get the last element of an array, in Js you would need to get the size of the array and withdraw one, in Ruby you simply do array.last, and you won't be surprised that `array.first` return the first one.

## :dart: Every day goals :  

**Coding**, manipulation on the file system (that sounds dangerous) and API request using the Github public API, then Github went down, so I went to bed.
**Talking about it**, in my daily [Walk and Talk](https://soundcloud.com/johan-c-819300950/walk-and-talk-day-14-58), it rained all day so I went inside and even if it sounds like I'm in a cathedral, it's actually an  emergency staircase.
We had the chance to receive John Barton, director of engineering at 99designs. He gave us a great lunchtime talk on how the dev team is split and how they work together. Bonus, he gave us a selection of book, [Code Complete](http://www.stevemcconnell.com/cc.htm), [The Pragmatic Programmer](https://en.wikipedia.org/wiki/The_Pragmatic_Programmer) and [Release It!](https://pragprog.com/book/mnee/release-it)

## :book: TIL :

- Hashes is another data type of Ruby. Also called associative arrays, a hash is a dictionary-like collection of unique keys and their values. You access the data the same way you will with an array `hashe[]`.
`{ name: 'bar'}` AND `{ :name => 'bar'}` are the same thing, a hash with symbols - value pairs, just a different notation.
- Json, (or JavaScript Object Notation) is a standard used to transmit human-readable text data, made of unordered attribute - values pairs. A colon separates the keys from the values, and a comma separates the pairs.
- .each if you need to iterate thru a collection, that way you won't have to keep count of anything.
- `[-1]` As a human I expect this to give me the last element of an array, thank you Ruby for fulfilling my expectation.

**:shell: Quotes of the day :**  

`"When choosing technologies,  would it actually solve the job ?" John Barton `