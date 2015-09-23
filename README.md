

# Getting User Data in the Command Line

## Overview

Up to this point, we've been able to create simple Ruby programs by using the `puts` method to output a string to the command line. In this codealong, we'll use the `gets` method to get data from the user and assign it to a variable for future use.

## Objectives

1. Use the `gets` method to get data from the user.
2. Assign the return value of `gets` to a variable
3. Understand that `gets` always returns a string.
3. Show that gets has a trailing space, so we usually use `.chomp` to remove it.

## Using `gets`

We're going to create a simple program called `greeter.rb`, that takes in a name from a user, and `puts` a welome phrase based on their input. Start by creating a new ruby file called `greeter.rb` and prompt the user for their name:

```ruby
puts "What is your name?"
```
Run the program to ensure that your program works.

In order to create a prompt in Ruby, use the `gets` method, like so:

```ruby
puts "What is your name?"
gets
```
Now when you run your program, it will pause until you fill in the prompt and hit the return key. Your program should then end.

We now have a prompt, but the value that the user has given us isn't being saved for us to use. Why don't we use a variable to hold the data that our user is giving us? That way we can use the data further on in the program:

```ruby
puts "What is your name?"
name = gets
puts "Welcome to the Flatiron School, " + name + "!"
```
Run your program again. You'll now be able to input your name, and will get back a welcome phrase that looks something like this:

```
Welcome to the Flatiron School, Danny
!
```
### Trailing Newlines 
Do you notice anything weird about the output of the string? The "!" is on the next line! The reason we see this is that when we use the gets method to input our name, we have to hit `return` to move on to the next line of the program. This `return` is actually counted as part of the string we're saving to the `name` variable. This is called a "trailing newline", and has an easy fix. We use the `.chomp` method to remove trailing newline characters:

```ruby
puts "What is your name?"
name = gets.chomp
puts "Welcome to the Flatiron School, " + name + "!"
```
Run your program again - it should work!


### Gets with Numbers
**Note**: `gets` will always return a string, regardless of whether the user is inputting numbers or letters in the prompt. As such, if you're planning on using the input as an integer or a float, you'll need to convert the input to the correct data type, using `.to_i` for integers and `.to_f` for floats. In fact, gets is actually short for 'get string'! Check out this "Addition program" that uses `.to_i` to convert the user input to integers for addition:

```ruby
puts "Welcome to the addition machine. Please input your first number:"
number1 = gets.to_i
puts "Input your second number:"
number2 = gets.to_i
sum = number1 + number2
puts "The sum of the two numbers is " + sum
``` 
We're very close, but this will give us the error `TypeError: String can't be coerced into Fixnum` - that's because we're trying to add together a string and an integer in our last line. We need to convert the integer back to a string using `.to_s` (to string) in order to use concatenation.


## Resources
[RubyLearning: Getting Input](http://rubylearning.com/satishtalim/getting_input.html)

