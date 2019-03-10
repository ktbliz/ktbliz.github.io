---
layout: post
title:      "My Ruby Cheat Sheet "
date:       2019-02-28 16:05:29 -0500
permalink:  my_ruby_cheat_sheet
---


Even though the internet is the ultimate cheat sheet, I've found it really helpful to make my own cheat sheet as I learn Ruby so that I can quickly remind myself of the range of things I've learned how to do. 

My cheat sheet just covers Ruby concepts at a high level (akak: has very minimal explanations), so that when I'm trying to solve a problem I can glance through and locate potential solutions/approaches. I keep my full cheat sheet in a One Note document that has grown quite long, but for my own use - and hopefully others' use as well - I wanted to try to condense it further. Here goes! 

Note: I will try to update this cheat sheet as the course goes along, but for now it just covers the first couple weeks of material.



## Ruby Cheat Sheet 


### Basics

To run a Ruby program:  
```ruby <file_name>```

Comment:   #


### Variables

Variable assignment: variable_name = variable_value
camel_case is the naming convention

#### Variable Types
Local variables: Names start with a lowercase letter

`my_variable`

Global variables: Names start with a $

`$my_variable`

Constants: Names start with an uppercase letter

`My_variable`


### Methods

* To define a method: 

```
def method_name(argument1, argument2 = "default")
   puts "Insert basic method here"
end
```

### Strings 

* Literal constructor: my_string = "here is my string"
* Interpolation:   #{ } (double quotes only)
* Alternative interpolation: 'Beginning of string' +variable_name+ 'end of string.' (single and double quotes)
* Methods for strings: 
 * size (or length) 
 * upcase 
 * downcase 
 * reverse
 * capitalize
 * reverse 
 * concat (or: my_string << "something to add") 
 * start_with?(" ") 
 * end_with?(" ")
 * include? 
 * chars (creates an array of the characters in the string)
 * my_string[0..139] (in this example, to get the first 140 characters of the string)
 * to_i   

### Numbers

* Fixnums: integers
* Floats: decimal numbers
* Methods for numbers: 
 * floor
 * ciel
 * next
 * even? 
 * odd? 
* Math in Ruby 
 * +
 * -
 * *
 * /
 * % (modulo, returns the remainder of a division operation)
 * Math.sqrt( )
 * Square: ** 2
 * Cube: ** 3
 * To the power of anything: ** 7
 * abs (e.g., -7.abs)

### Booleans
* Not: !
* And: &&
* Or: ||
* Equal to: ==
* Not equal to: !=
* Less than: <
* Lean than or equal to: <=
* Greater than: >
* Greater than or equal to: >=

### Arrays

* Literal constructor: my_array = [item1, item2, item3]
* Methods for arrays: 
 * length
 * sort
 * reverse

### Symbols
Denoted with a colon in front of the name, e.g., :my_symbol

### Ranges
* (100..200) two dots includes the last number
* (100...200) three dots excludes the last number

### Hashes

* Literal constructor: my_hash = { }

### Miscellaneous keywords 

* puts 
* prints
* return
* Time.now
* Time.now.year
* rand (e.g., rand(1..10))
* sleep (e.g., sleep 2, sleep(4.minutes), sleep(0.5), seconds is the default unit) 
* Add-and-assignment: +=
* Subtract-and-assignment: -=
* gets
 * gets.chomp (removes extra line)
 * gets.strip (removes extra line and white space)
* 

### Conditionals
1) if, elsif, else

```
if condition
   puts "a"
elsif condition
   puts "b"
else
   puts "c"
end
#conditions can be booleans / anythig that will return a true or false
``` 

2) Ternary operator

`condition ? action_if_true : action_if_false`

* Statement modifiers
 * Append "if" or "unless" to the end so execute a statement conditionally 
 * puts "Hey it's 2019" if Time.now.year == 2019
 * puts"Hey it's not 2019 unles Time.now.year == 2019

3) Case statements

```
case value_or_variable_to_test
   when condition 1
	    action1
	when condition2
	   action2
	when condition3
	   action3
end
#note that case statments use === to evaluate
```

### Looping

1) times

```
10.times do 
   puts "Hi" 
end 
```

2) loop

```
counter = 0
loop do
   counter += 1
	 puts "Hi"
	 break if counter >= 10
end
#note that the loop keyword will make an infinite loop if the break keyword isn't added in
```

3) while

```
counter = 0
while counter <= 20
   counter += 1
	 puts "The counter is #{counter}"
end 
```

4) until

```
counter = 0
until counter == 21
   counter += 1
	 puts "The counter is #{counter}"
end 
```

5) for

```
for counter in 1..40 do
   puts "The counter is #{counter}"
end 

for individual_element in range
   #execute some code
end
```



 



