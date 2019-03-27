# String Interpolation

## Learning Goals

- Define string interpolatation
- Practice interpolating variables into strings

## Introduction

You're a party planner for Beyonce's next birthday and you're using Ruby to help
you out with the arrangements. There is a variable called `num_of_attendees` and
since she's very popular, this variable points to the integer 547. You try and
print the value of `num_of_attendees` to the screen with the code below:

```ruby
num_of_attendees = 547
puts "There are num_of_attendees people coming to Beyonce's birthday party."
```

You expect this to print "There are 547 people coming to Beyonce's birthday
party" but instead it prints "There are num_of_attendees people coming to
Beyonce's birthday party." Why is this?

Variables cannot just be referenced by their name inside a string. We could
try writing this instead:

```ruby
num_of_attendees = 547
puts "There are " + num_of_attendees + " people coming to Beyonce's birthday party."
```

But that produces an error! Specifically, it produces `TypeError (no implicit
conversion of Integer into String)`. Remember that Ruby won't automatically
convert one data type to another. We would need to convert the integer 547 into
a string. One way to do this is to use a built in method for the Integer class,
`to_s`, that converts an integer to a string:

```ruby
num_of_attendees = 547
puts "There are " + num_of_attendees.to_s + " people coming to Beyonce's birthday party."
```

This works! There is, however, a shorter way to handle this known as
string interpolation. In this lesson, we're going to explore string
interpolation and how we use it.

## Define String Interpolation

String interpolation allows us to include variables inside a string without
having to explicitly convert them to the string data type. By wrapping a
variable like `#{this}`, Ruby will know to convert it to a string.

```ruby
num_of_attendees = 547
puts "There are #{num_of_attendees} people coming to Beyonce's birthday party."
```

This prints `There are 547 people coming to Beyonce's birthday party.`. Yay!
We did not have to deal with adding pieces of strings or converting data. String
interpolation allows us to format a string the way we would like, and add in
dynamic content with variables.

## Practice Interpolating Variables into Strings

Let's drop into IRB and copy and paste the code from the following example.

Let's say you have a super hard question on your biology test asking you to
identify the technical term for a group of flamingos.

```ruby
answer = "< fill in your answer here >"
puts "A group of flamingos is called a #{answer}."
```

Now, set the `answer` variable equal to `"flamboyance"` and run the following
code in IRB:

```ruby
answer = "flamboyance"
puts "A group of flamingos is called a #{answer}."
```

This prints `A group of flamingos is called a flamboyance.` to the screen.

**Note:** Here, you're declaring the variable `answer` before calling `puts`.
You need to do it in this order, because our program is read by the computer
sequentially. When your computer gets to `#{answer}`, it won't know what that is
if `answer` isn't defined yet.

Interpolation isn't restricted to variables:

```ruby
puts "2 + 2 = #{2+2}"
```

This prints `2 + 2 = 4`.

### Double Quotes Only

Interpolation will only work on Strings wrapped in double quotes (`""`). Single
quotes (`''`) **do not support string interpolation**, so running:

```ruby
answer = 'Flamboyance'
puts 'A group of flamingos is called a #{answer}.'
```

Will just print `A group of flamingos is called a #{answer}.`

If you were committed to using single quotes in such a case, it would be the
right time to use the alternative method (`'A group of flamingos is called a ' + answer + '.'`) which would work just fine.

## Conclusion

It is perfectly acceptable to add strings and variables together as
we saw initially:

```ruby
rating = "fine"
puts "This method is perfectly " + rating + " to use."
```

String interpolation is a simply tool for us to use. It takes care of some steps
for us, such as converting data types. We will be frequently using strings as we
built applications with user interfaces, and it is often the case that we need
to include dynamic content into text. String interpolation is a useful way to
solve this problem.

<p class='util--hide'>View <a href='https://learn.co/lessons/interpolation-readme'>String Interpolation </a> on Learn.co and start learning to code for free.</p>
