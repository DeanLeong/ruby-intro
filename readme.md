# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png)  SOFTWARE ENGINEERING IMMERSIVE

# Ruby

### Objectives
*After this lesson, students will be able to:*
- Be familiar with basic Ruby data types
- Know how to compare and mutate Ruby objects
- Understand basic iterators and control in Ruby
- Compare/contrast Ruby objects/methods to Javascript objects/functions

### Preparation
*Before this lesson, students should:*
- Be comfortable with Javascript
- Have Ruby installed


## What is Ruby?

[Ruby](https://www.ruby-lang.org/en/about/) is a high-level  programming language that gives us a lot of nice features out of the box.

It is meant to be pretty, unobtrusive, and super readable.

Ruby does **not** run in the browser.  It is most commonly used for backend web development with frameworks like [Sinatra](http://www.sinatrarb.com/) and [Rails](http://rubyonrails.org/).

## What's Ruby like? 

### M.I.N.A.S.W.A.N.

* "Matz Is Nice And So We Are Nice"
* Mentality not only applies to how you should treat your fellow developers, but also the philosophy behind Ruby itself.
* Yukihiro Matsumoto ("Matz") created Ruby to increase developer happiness.

> "Programmers often feel joy when they can concentrate on the creative side of programming, so Ruby is designed to make programmers happy." — Yukihiro "Matz" Matsumoto  

### A **Natural** Language

While it isn't exactly simple, a lot of its features are going to feel intuitive.  

> "Ruby is simple in appearance, but is very complex inside, just like our human body." — Yukihiro "Matz" Matsumoto  


## Running Ruby

Just run `ruby FILENAME.rb`.  You can also run [`pry`](http://pryrepl.org/) this is a Ruby `repl`.

> [`irb`](https://www.tutorialspoint.com/ruby/interactive_ruby.htm) is the official ruby repl but `pry` is much better

## What is a variable in Ruby?

A variable is an identifier that is assigned to an object, and which may hold a value. Ruby variables are not declared, nor are they statically typed. Instead, the type of value is assigned at runtime. Ruby uses duck typing, which is a kind of dynamic typing. If a value behaves or acts like a certain type (duck), such as an integer, Ruby gives it a context and treats it as such (it’s probably a duck). If a variable is able to act like an integer, for example, then it is legal and appropriate to use it in that context.

## Examples:
```ruby
welcome = 'Welcome to Ruby Programming' # => String
one     = 1 # => Integer
price   = 10.25 # => Float
```

## Numbers

Numbers in Ruby are in the [`Numeric`](https://ruby-doc.org/core-2.5.1/Numeric.html) class.  It's subclasses include [`Integer`](https://ruby-doc.org/core-2.5.1/Integer.html) and [`Float`](https://ruby-doc.org/core-2.5.1/Float.html)

```ruby
1.class
 => Integer
1.0.class 
 => Float
1+1
 => 2 
3-1
 => 2 
3*3
 => 9 
10/2
 => 5 
1 / 2 
 => 0 # (rounds down)
1 / 2.0 
 => 0.5 # (does not round float)
2.next
 => 3 # (.next provides the next integer value)
2.pred
 => 1 # (.pred provides the preceding integer value)
2.lcm(3)
 => 6 # (.lcm gives us the least common multiple of the integer to which the method is applied and the value passed)
2.gcd(3)
 => 1 # (.gcd provides the greatest common divisor of the integer to which the method is applied and the value passed)
```

There are a number of methods available for the integer class, which you can play around with. Simply check them by using .methods on the integer.

```ruby
2.methods
 => [:-@, :**, :<=>, :upto, :<<, :<=, :>=, :==, :chr, :===, :>>, :[], :%, :&, :inspect, :*, :+, :ord, :-, :/, :size, :succ, :<, :>, :to_int, :coerce, :to_s, :to_i, :to_f, :divmod, :to_r, :fdiv, :modulo, :remainder, :abs, :magnitude, :integer?, :floor, :ceil, :round, :truncate, :^, :odd?, :even?, :allbits?, :anybits?, :nobits?, :downto, :times, :pred, :pow, :bit_length, :digits, :numerator, :denominator, :rationalize, :gcd, :lcm, :gcdlcm, :next, :div, :|, :~, :imag, :abs2, :+@, :phase, :to_c, :polar, :angle, :conjugate, :conj, :eql?, :singleton_method_added, :i, :real?, :zero?, :nonzero?, :finite?, :infinite?, :step, :positive?, :negative?, :clone, :dup, :arg, :quo, :rectangular, :rect, :real, :imaginary, :between?, :clamp, :instance_variable_defined?, :remove_instance_variable, :instance_of?, :kind_of?, :is_a?, :tap, :instance_variable_set, :protected_methods, :instance_variables, :instance_variable_get, :private_methods, :public_methods, :public_send, :method, :public_method, :singleton_method, :define_singleton_method, :extend, :to_enum, :enum_for, :=~, :!~, :respond_to?, :freeze, :object_id, :send, :display, :nil?, :hash, :class, :singleton_class, :itself, :yield_self, :then, :taint, :tainted?, :untaint, :untrust, :untrusted?, :trust, :frozen?, :methods, :singleton_methods, :equal?, :!, :instance_exec, :!=, :instance_eval, :__id__, :__send__] 
```

## Constants

Constant names must begin with a capital letter (Pi) and by convention frequently use all capitals (PI), making them easy to spot. Class names, for example, are constants. As their name suggests, constants are not expected to have their values changed after initial assignment. You can reassign a value to a constant, but Ruby will generate a warning if you do. Second, and more importantly, since constants refer to objects, the contents of the object to which the constant refers might change without Ruby generating a warning. Thus, Ruby constants are called mutable because although a constant is only expected to refer to a single object throughout the program, the value of that object may vary. Finally, constants must have a value assigned to them to exist.

## Parallel Variable Assignment

With parallel assignment, you can assign several values to several variables in a single expression, based on order. A list of variables, separated by commas, can be placed to the left of the equals sign, with the list of values to assign them on the right. Here are a few examples:

```ruby
name, grade, gpa = 'Suresh', 89, 3.6
a, b, c = "cash", 1.99, 100
```

## [Strings](https://ruby-doc.org/core-2.6/String.html)

A string is a series of text characters. You can use strings to hold names, email addresses, phone numbers, and a million other things. Ruby’s strings are special because even very large strings are highly efficient to work with (this isn’t true in many other languages). Strings in Ruby are derived from the String class, and there are over 100 methods to manipulate and operate on strings. This is perhaps because, in programming, a lot revolves around strings, and Ruby reduces the headache by managing a lot out of the box.

The easiest way to specify a string is to surround it either with double quotes (") or single quotes ('). The two types of quotes work a little differently

- Ruby’s string literal syntax, as well as the String operators for concatenation (+), appends (<<), repetition (*), and indexing ([]).

```ruby
s = "hello"
s.concat(" world") # Synonym for <<. Mutating append to s. Returns new s
s.insert(5, " there") # Same as s[5] = " there". Alters s. Returns new s
s.slice(0,5) # Same as s[0,5]. Returns a substring
s.slice!(5,6) # Deletion. Same as s[5,6]="". Returns deleted substring
s.eql?("hello world") # True. Same as ==
```

### There are several methods for querying the length of a string:

```ruby
s.length # => 5: counts characters in 1.9, bytes in 1.8
s.size # => 5: size is a synonym
s.bytesize # => 5: length in bytes; Ruby 1.9 only
s.empty? # => false
"".empty? # => true
```

### Finding the position of a substring or pattern match
- String methods for searching a string and for replacing content include the following:

```ruby
s = "hello"
s.index('l') # => 2: index of first l in string
s.index(?l) # => 2: works with character codes as well
s.index(/l+/) # => 2: works with regular expressions, too
s.index('l',3) # => 3: index of first l in string at or after position 3
s.index('Ruby') # => nil: search string not found
s.rindex('l') # => 3: index of rightmost l in string
s.rindex('l',2) # => 2: index of rightmost l in string at or before 2
```

### Checking for prefixes and suffixes

```ruby
s.start_with? "hell" # => true. Note singular "start" not "starts"
s.end_with? "bells" # => false
```

## Testing for presence of substring

```ruby
s.include?("ll") # => true: "hello" includes "ll"
s.include?(?H) # => false: "hello" does not include character H
```

### Pattern matching with regular expressions

```ruby
s =~ /[aeiou]{2}/ # => nil: no double vowels in "hello"
s.match(/[aeiou]/) {|m| m.to_s} # => "e": return first vowel
```

## Splitting a string into substrings based on a delimiter string or pattern

```ruby
"this is it".split # => ["this", "is", "it"]: split on spaces by default
"hello".split('l') # => ["he", "", "o"]
"1, 2,3".split(/,\s*/) # => ["1","2","3"]: comma and optional space delimiter
```

### Split a string into two parts plus a delimiter
- These methods always return arrays of 3 strings:

```ruby
"banana".partition("an") # => ["b", "an", "ana"]
"banana".rpartition("an") # => ["ban", "an", "a"]: start from right
"a123b".partition(/\d+/) # => ["a", "123", "b"]: works with Regexps, too
```

### Interpolation

To interpolate strings in Ruby, you must use double quotes

```ruby
"I have #{13 * 4} cards" # => "I have 52 cards"
'I have #{13 * 4} cards' # => 'I have #{13 * 4} cards'
```

### Concatenation

You can also concatenate strings but this is NOT recommend

```ruby
'foo' + 'bar' # => 'foobar'
'foo' + 2 # => TypeError: no implicit conversion of Integer into String
'foo' + 2.to_s # => 'foo2'
```

Above we see that we can NOT implicitly convert a non-string into a string (unlike what we have seen in JS).

Use single quotes for strings that are not interpolated

## Symbols

A [Symbol](https://ruby-doc.org/core-2.5.1/Symbol.html) is similar to a `String`.  It cannot be mutated or manipulated.  It is used represent _things_ rather than _text_.  Symbols start with `:`.

```ruby
:foo # => :foo
:foo == :foo # => true
:foo == :bar # => false
:foo == 'foo' # false
```

The more you see them the more you will understand the use-case.
Symbols use memory more efficiently
```ruby
string1 = 'hello'
string2 = 'hello'
symbol1 = :hello
symbol2 = :hello

string1.object_id #=> 1234
string2.object_id #=> 4567

symbol1.object_id #=> 7890
symbol2.object_id #=> 7890
```

## Booleans

Of course Ruby has two booleans `true` and `false`

Each object has a `==` method that compares to another object.

```ruby
1 == 1 # => true
1 == '1' # => false
1 == 1.0 # => true
[:foo, :bar] == [:foo, :bar] # => true
[:foo, :bar] == [:bar, :foo] # => false
{a: 1, b: 2} == {b: 2, a: 1} # => true
```

> Do NOT use `===`. This is not the same as what it means in JS.  (Look it up if you are curious)

### Truthy and Falsy

Ruby only has **two** falsy values: `nil` and `false`.

So unlike JS `0` and `''` are truthy.  (There is no `null`, `undefined`, `NaN`, `-0`)

```ruby
!! false # => false
!! nil # => false

!! 0 # => true
!! '' # => true
```

## Local Variables
A local variable has a local scope or context. If defined within a method, for example, its scope is kept within that method. Local variable names must begin with either a lowercase letter or an underscore (_), and must not be prefixed with @, @@, or $ because they are reserved for other types of variables. Following are a few examples of local variables:

```ruby
x = 1.0    # x is a Float
y = "Yes"  # y is a String
_temp = 16 # _temp is a Integer
``` 

## Instance Variables
An instance variable belongs to a particular instance of a class, hence the name. It can only be accessed from outside that instance via an accessor (helper) method. Instance variables are always prefixed with a single at sign (@), as in @hello.

## Class Variables
A class variable is shared among all instances of a class. Only one copy of a class variable exists for a given class. It is prefixed by two at signs (@@), such as @@times. You have to initialize (declare a value for) a class variable before you use it.

## Global Variables
Global variables are globally available to a program, inside any structure. Their scope is the whole program. They are prefixed by a dollar sign ($), such as $amount.


## Boolean States, Boolean Objects, and nil

Every expression in Ruby evaluates to an object, and every object has a Boolean value of either true or false. Furthermore, true and false are objects. This idea isn’t as convoluted as it sounds. If true and false weren’t objects, then a pure Boolean expression like

```
100 > 80
```

would have no object to evaluate to. (And > is a method and therefore has to return an object.)

In many cases where you want to get at a truth/falsehood value, such as an if statement or a comparison between two numbers, you don’t have to manipulate these special objects directly. In such situations, you can think of truth and falsehood as states, rather than objects.

## The special object nil

The special object nil is, indeed, an object (it’s the only instance of a class called NilClass). But in practice, it’s also a kind of nonobject. The Boolean value of nil is false, but that’s just the start of its nonobjectness.

nil denotes an absence of anything. You can see this graphically when you inquire into the value of, for example, an instance variable you haven’t initialized:

```ruby
puts @x
```

This command prints an empty string and returns nil. (If you try this with a local variable, you’ll get an error; local variables aren’t automatically initialized to anything, not even nil.) nil is also the default value for nonexistent elements of container and collection objects. For example, if you create an array with three elements, and then you try to access the tenth element (at index 9, because array indexing starts at 0), you’ll find that it’s nil:

```ruby
["one","two","three"][9]
 => nil 
```

nil is sometimes a difficult object to understand. It’s all about absence and nonexistence; but nil does exist, and it responds to method calls like other objects:

```ruby
nil.to_s
 => "" 
nil.to_i
 => 0 
nil.object_id
 => 8 
```

The to_s conversion of nil is an empty string (""); the integer representation of nil is 0; and nil’s object ID is 8. (nil has no special relationship to 8; that just happens to be the number designated as its ID.)

It’s not accurate to say that nil is empty, because doing so would imply that it has characteristics and dimension, like a number or a collection, which it isn’t supposed to. Trying to grasp nil can take you into some thorny philosophical territory. You can think of nil as an object that exists and that comes equipped with a survival kit of methods but that serves the purpose of representing absence and a state of being undetermined.

Coming full circle, remember that nil has a Boolean value of false. nil and false are the only two objects that do. They’re not the only two expressions that do; 100 < 50 has a Boolean value of false, because it evaluates to the object false. But nil and false are the only two objects in Ruby with a Boolean value of false. All other Ruby objects—numbers, strings, instances of MyCoolClass—have a Boolean value of true. Tested directly, they all pass the if test.

Boolean values and testing provide a segue into the next topic: comparisons between objects. We’ll look at tests involving two objects and ways of determining whether they’re equal—and, if they aren’t, whether they can be ranked as greater/lesser, and based on what criteria.

## Arrays

A Ruby [`Array`](https://ruby-doc.org/core-2.5.1/Array.html) is similar to a JS Array.

```ruby
arr = ["apple", "mango", "pear", "kiwi"]
arr.length # => 4

arr.first # => "apple"
arr.last # => "kiwi"
arr[1] # => "mango"
arr[100] # => nil

arr.include?("mango") # => true

arr.push("orange") # => ["apple", "mango", "pear", "kiwi", "orange"]
arr                # => ["apple", "mango", "pear", "kiwi", "orange"]
```
- Another way to add elements to an array is by means of the << operator. There are operators in Ruby that are aliases to functions or methods, and they are used to achieve the same result, but with shortcuts:
```ruby
my_array  = [1,2,3]
my_array  << 4 # => [1, 2, 3, 4]
```

To get the last few elements we can use negative indexes

```ruby
arr[-1] # => "orange"
arr[-2] # => "kiwi"
```

We can also concatenate arrays

```ruby
[1, 2, 3] + [4, 5] # => [1, 2, 3, 4, 5]
# (this is a new array. neither is mutated)
```

## Iterating over an array

Ruby supports for loops and the other iteration constructs found in most modern programming languages, but its prefered idiom is a code block fed to an method like each or collect.

```ruby
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9]
numbers.each { |x| p x }
```
If you want to produce a new array based on a transformation of some other array, use Enumerable#collect along with a block that takes one element and transforms it:
```ruby
numbers = [1,2,3]
numbers_two = numbers.collect {|x| x+1 }
p numbers_two
```
Methods like each and collect are called generators or iterators: they iterate over a data structure, yielding one element at a time to whatever code block you’ve attached.

If you need to have the array indexes along with the array elements, use Enumerable#each_with_index.

```ruby
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9]

numbers.each_with_index do |item, index|
  puts "At position #{index}: #{item}"
end
```
To iterate over a list in reverse order, use the reverse_each method:
```ruby
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9]
numbers.reverse_each {|x| puts x }
```

The map method acts just like collect, but instead of creating a new array to hold the return values of its calls to the code block, it replaces each item in the old array with the corresponding value from the code block. This saves memory and time, but it destroys the old array
```ruby
students = %w(John Suresh Casey)
puts students[0].object_id
puts students.collect! { |x| x.upcase }
puts students[0].object_id
puts students.map! { |x| x.downcase }
puts students[0].object_id
```
Like most other programming languages, Ruby lets you define for, while, and until loops—but you shouldn’t need them very often. The for construct is equivalent to each, whether it’s applied to an array or a range:
```ruby
students = %w(John Suresh Casey)
for element in students
  puts element
end
```

```ruby
students = %w(John Suresh Casey)
students.each { |element|
  puts element
}
```
The while and until constructs take a boolean expression and execute the loop while the expression is true (while)or until it becomes true (until). All three of the following code snippets generate the same output:
```ruby
names = ['John', 'Suresh', 'Casey']

for index in (0...names.length)
  puts "At position #{index}: #{names[index]}"
end

index = 0
while index < names.length
  puts "At position #{index}: #{names[index]}"
  index += 1
end

index = 0
until index == names.length
  puts "At position #{index}: #{names[index]}"
  index += 1
end
```
- <b>Note</b> These constructs don’t make for very idiomatic Ruby. You should only need to use them when you’re iterating over a data structure in a way that doesn’t already have an iterator method. 

## Creating an array that cannot be modified

- This can come in handy when we want to limit the size of an array or prevent further modification. The freeze function can be used on objects other than arrays with the same result:
```ruby
my_array  = [1,2,3]
my_array.freeze
my_array << 4 # this will cause an error
```

## Team Exercise 1

```ruby
# Write a program that prints the number of times the string 'bob' occurs in s. For example, if s = 'azcbobobegghakl',
# then your program should print 
# Number of times bob occurs is: 2
```

## Team Exercise 2

```ruby
# Write a program that accepts a comma-separated sequence of words as input and prints the words in a comma-separated 
# sequence after sorting them alphabetically. 
# Suppose the following input is supplied to the program: without, hello, bag, world
# Then, the output should be: bag, hello, without, world
```

## Range

A [`Range`](http://ruby-doc.org/core-2.5.1/Range.html) allows you to define a range of values. You can then turn that range into an array and get all the sweet array methods. This is a great technique to avoid for loops. you can use three dots instead of two for an exclusive range.
```ruby
(1..10).to_a #=> [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
(1...10).to_a #=> [1, 2, 3, 4, 5, 6, 7, 8, 9]
```

## Hashes

A [`Hash`](https://ruby-doc.org/core-2.5.1/Hash.html) is similar to a JS object.

```ruby
gustave = { 'name' => 'Gustave', 'age' => 2.5 }
gustave['name'] # => 'Gustave'
gustave['foo'] # => nil
```

We use ONLY bracket notation to get and set values

```ruby
gustave['age'] # => 2.5
gustave.age # => NoMethodError: undefined method `age' for Hash

gustave['age'] = 10
gustave['age'] # => 10

gustave.age = 25 # => NoMethodError: undefined method `age=' for Hash
```

By convention, `Hash` keys are usually `Symbol`s not `String`s

```ruby
gustave = { :name => 'Gustave', :age => 24 }
gustave[:name] # => 'Gustave'
gustave['name'] # => nil
```

Since using symbols as keys is so common, there is a nice short-hand

This is exactly the same as what we saw above.

```ruby
gustave = { name: 'Gustave', age: 24 }
```

Notice that is looks exactly like a JS object except the keys are symbols, not strings.


## Iteration

In JS if we wanted to print numbers 0 through 3 we would:

```javascript
for(var i = 0; i < 3; i++) {
  console.log(i);
}
// > 0
// > 1
// > 2
```

In Ruby this is much cleaner:

```ruby
3.times { |i| puts i }
# > 0
# > 1
# > 2
```

`times` is a method that takes a _block_.  A block is just a chunk of code that may or may not take arguments.  The closest thing to a block in ES6-land would be an (anonymous) arrow function.

> Yes there _are_ `for` loops in Ruby but we DO NOT use them

We can also iterate over arrays:

```ruby
arr = [10, 20, 30]

arr.each { |num| puts num }
# > 10
# > 20
# > 30

arr.map { |num| num / 10 }
# => [1, 2, 3]
```

`each` and `map` also take blocks (just like `forEach` and `map` take callbacks in JS).

For blocks with longer lines or multiple lines, replace `{` and `}` with `do` and `end`

```ruby
arr.map do |num|
  "#{num / 10} is great!"
end
# => ["1 is great!", "2 is great!", "3 is great!"]
```

And we can iterate over hashes:

```ruby
hash = { a: 1, b: 2, c: 3 }
hash.each do |key, val|
  puts "the value of #{key} is #{val}"
end
# > the value of a is 1
# > the value of b is 2
# > the value of c is 3
```

## Methods

In Ruby everything is a [`Method`](https://ruby-doc.org/core-2.5.1/Method.html).  There are NO functions!


```ruby
def add(a, b)
  a + b
end

add(1, 2) # => 3

add(1, 2, 3)
# > ArgumentError: wrong number of arguments (given 3, expected 2)
```

Notice we do not need the keyword `return`.  The last line hit by the method will always be the return value.  This is called an _implicit return_.

We can add default arguments

```ruby
def add(a, b=10)
  a + b
end

add(1, 2) # => 3
add(1) # => 11 (b defaults to 10)
```

We can also have an arbitrary number of arguments

```ruby
def add(*nums)
  return 0 if nums.empty?
  nums.reduce { |sum, n| sum + n }
end
```

Above, the `nums` object is just an array of the arguments given.  If there are no arguments given, the `nums` will be empty and we will `return` early.

We also do NOT use parentheses when calling a method without arguments

```ruby
def say_hi(name = 'World')
  puts "Hello, #{name}!"
end

say_hi('Gustave')
# > Hello, Gustave!
say_hi
# > Hello, World!
```

We called the method without using parens!

### Bonus: [defining methods that `yield` blocks](blocks.md)



## Control Flow

Ruby and JS (and many languages) have similar control flow patterns.

### `if`/`elsif`/`else` and ternary


```ruby
def number_message(num)
  if num < 10
    puts 'what a small number'
  elsif num > 10
    puts 'That is a big number!'
  else
    puts 'That number is just right!'
  end
end
```

#### `if` / `unless`
We also have single-line ifs

```ruby
puts 'you are old!' if age >= 100
```

You may even see `unless`

```ruby
puts 'you are old!' unless age < 100
```
When you see an `unless foo`, read it as `if !foo`

> `if !foo` can always be written as `unless foo` which creates a more readable line


#### Ternary operator  

A ternary operator looks just like we have seen in JS

```ruby
num.even? ? "#{num} is even!" : "#{num} is odd!"
```

### `while` loops

```ruby
a = 10
while a.positive?
  puts a
  a -= 1
end
```

> There are also `until` loops. While is to `until` as `if` is to `unless`

### Binary operators `&&`/`||`

Binary operators are pretty much the same as in JS :)

```ruby
1 && 2 # => 2 (truthy)
nil && 2 # => nil (falsy)
1 && nil # => nil (falsy)

1 || nil # => 1 (truthy)
nil || 2 # => 2 (truthy)
false || nil # => nil (falsy)
```

## Error-handling

In Ruby we have `raise` to throw errors and `rescue` to catch them.

These are most common when using and creating external APIs but probably don't need to be used in your own internal code.

If you are interested flex your google muscles and learn it on your own ;)

## Style Things

The Ruby community is very opinionated about styling.  As you are starting out, you MUST follow [these rules](https://github.com/bbatsov/ruby-style-guide).

Here are the most important rules

**Casing**

* All variables and methods must use `snake_case`
* All classes and modules must use `CamelCase`
* All constants (besides classes and modules) must use `SCREAMING_SNAKE_CASE`

**Blocks**

* A single line block must use `{` and `}`
* A multi-line must use `do` and `end`
* If an argument is unused it should start with `_` (or just be named `_`)
  * `hash.each { |_key, val| puts val }`

**Methods**

* A method should end with a `?` if an only if it always returns a boolean
  * These are called _predicate methods_
* A method ending in `!` should be a _dangerous_ version of the method sans `!`
  * _dangerous_ means either that it can mutate the object _or_ that can raise an error
* Don't name methods like `get_foo`, `set_foo`. They should be `foo` and `foo=`
* **Do** use `attr_reader` and `attr_writer`
* Do not use parens when calling a method without args
  * `super` is one possible exception
* **Do** use parens for every method except for DSLs (and a small list of other common methods)
  * `attr_reader`, `puts`, `require`, `include`, `it`, `has_many`, ...


## Resources

* [Ruby docs](https://ruby-doc.org/core-2.5.1/)
  - [`Array`](http://ruby-doc.org/core-2.5.1/Array.html), [`Hash`](http://ruby-doc.org/core-2.5.1/Hash.html), [`String`](http://ruby-doc.org/core-2.5.1/String.html), [`Symbol`](http://ruby-doc.org/core-2.5.1/Symbol.html), [`Numeric`](http://ruby-doc.org/core-2.5.1/Numeric.html),
  [`Object`](http://ruby-doc.org/core-2.5.1/Object.html), ...
* [Ruby Style Guide](https://github.com/bbatsov/ruby-style-guide)
* [Reserved words](http://www.java2s.com/Code/Ruby/Language-Basics/Rubysreservedwords.htm)

## Conclusion
- Why is Ruby awesome?
- What are some differences between Ruby and Javascript?
  - Where can they each run? What are the differences between Ruby objects and JS object?  Ruby methods and JS methods?

---

