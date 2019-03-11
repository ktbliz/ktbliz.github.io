---
layout: post
title:      "My Ruby Cheat Sheet"
date:       2019-02-28 16:05:29 -0500
permalink:  my_ruby_cheat_sheet
---

## A Beginner's Quick Reference for Ruby Syntax  

Even though the internet is the ultimate cheat sheet, I've found it really helpful to make my own cheat sheet as I learn Ruby so that I can quickly remind myself of the range of things I've learned how to do. 

My cheat sheet mostly covers Ruby syntax and key concepts at a high level (aka: it contains very minimal explanations of these concepts). I made it so that, when I'm trying to solve a problem, I can quickly glance through and locate potential approaches and the correct syntax. I keep my full cheat sheet in a One Note document that has grown quite long, but for my own use - and hopefully others' use as well - I wanted to try to condense it further. Here goes! If anyone does find this useful and/or has ideas for improvement and/or finds any errors (I am a newb after all), let me know!

Note: I will try to update this cheat sheet as the course goes along, but for now it just covers the first couple weeks of material.



# Ruby Cheat Sheet 


## Basics

To run a Ruby program:  

* `ruby <file_name.rb>`

Comment:   #

To enter Interactive Ruby (IRB) shell, type: irb 

puts 
* Adds a new line after ouput

prints 
* Does not add a new line after output

return

require relative 

class

* `my_variable.class`

object_id

Add-and-assignment: +=

Subtract-and-assignment: -=

gets
 
gets.chomp
* Removes extra line that comes with the gets
 
gets.strip
* Removes extra line that comes with the gets, plus any white space



## Miscellaneous

Time.now

Time.now.year

rand

* `rand(1..10)`

sleep (default unit is seconds)

* `sleep(4.minutes)`
* `sleep(0.5)`



## Variables

Variable assignment: 

`variable_name = variable_value`

camel_case is the naming convention

### Variable Types

Local variables: Names start with a lowercase letter

`my_variable`

Global variables: Names start with a $

`$my_variable`

Constants: Names start with an uppercase letter

`My_variable`



## Methods

To define a method: 

```
def method_name(argument1, argument2 = "default")
   puts "Insert basic method here"
end
```



## Strings 

Literal constructor: 

`my_string = "here is my string"`

Interpolation with #{ } (use with double quotes only):  

`my_string = "I need to interpolate this: #{variable_etc } into my string"` 

Alternative interpolation (use with single and double quotes): 

`'Beginning of string' + variable_name + 'end of string.' `

### Methods for Strings

NOTE: Unless otherwise noted, call these methods on strings using dot notation: 

`my_string.method_name`


size

length 

upcase 

downcase

capitalize

reverse

concat( ) 

Alternative method for concatenation with << 

* `my_string << "something to add"`

start_with?( ) 

end_with?( )

include?( ) 

chars
* Creates an array of the characters in the string

Slicing a string with [ ]
* `my_string[0..139]` 
* In this example, you get the first 140 characters of the string

to_i   



## Numbers

Fixnums: integers

Floats: decimal numbers

### Methods for Numbers
 
NOTE: Unless otherwise noted, call these methods on numbers using dot notation: 

`my_numeric_variable.method_name`


floor
 
 ciel
 
 next
 
 even? 
 
 odd? 

### Math in Ruby 
 
Addition, subtraction, multiplication, division: 

```
a + b
a - b
a * b
a / b
```

Modulo (returns the remainder of a division operation):

`a % b`

Square root:

`Math.sqrt(a)`

Square:

`a ** 2`

Cube: 

`a ** 3`

To the power of anything (e.g. to the power of 7): 

`a ** 7`

Absolute value: 

`-7.abs`



## Booleans

Not: !

And: 

`a && b`

Or: 

`a || b`

Equal to: ==

Not equal to: !=

Less than: <

Lean than or equal to: <=

Greater than: >

Greater than or equal to: >=



## Arrays

Literal constructor: 

`my_array = [item1, item2, item3]`

Arrays are indexed starting at 0, the first element has an index of 0, the second element has an index of 1, etc.

### Basic Methods for Arrays

NOTE: Unless otherwise noted, call these methods on arrays using dot notation: 

`my_array.method_name`


length

size

inspect
* Returns a string representation of the array
* `puts my_array.inspect`

sort

shuffle
* Randomizes an array

reverse

Shovel method: << 
* Adds an item to the end of an array
* `array_name << "new item"`

push( )
* Adds an element to the end of an array

unshift( )
* Adds an element to the front of an array

pop( )
* Removes the last element of an array
* pop(2) and pop(3), etc. will remove the last two and three elements, respectively

shift( )
* Removes the first element of the array
* shift(2) and shift(3), etc. will remove the last two and three elements, respectively

insert(index, element)

delete_at(index)

delete(element)
* Deletes all instances of the element specified in parentheses

Retrieving elements from an array with bracket notation [ ]
* Retrieve the fourth element: `my_array[3]`
* Retrieve the last element: `my_array[-1]`

first

last

index( )
* This will return the index of the (first instance of the) element specified in parentheses

include?( )

Slicing an array:
* my_array[0..10]  
* my_array[index, length]


### More Array Methods 

uniq

flatten

count


## Symbols

Denoted with a colon in front of the name:

`:my_symbol`




## Ranges

Two dots: Includes the last number

`(100..200)` 

Three dots: Exlcudes the last number

`(100...200)`




## Conditionals

1) if, elsif, else

```
if condition
   puts "a"
elsif condition
   puts "b"
else
   puts "c"
end

#conditions can be booleans or anything that will return a true or false
``` 

2) Ternary operator

`condition ? action_if_true : action_if_false`

3) Statement modifiers

 Append "if" or "unless" to the end of a statement to execute that statement conditionally 
 
```
puts "Hey it's 2019" if Time.now.year == 2019
puts" Hey it's not 2019 unless Time.now.year == 2019
```

4) Case statements

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




## Blocks 

Two types of syntax for blocks:

1) do / end 

```
10.times do 
   puts "Hello"
end 
```

2) { }

```
10.times {
   puts "Hello"
}
```



## Looping

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



## Hashes

Literal constructor: 

`my_hash = { }`
 



