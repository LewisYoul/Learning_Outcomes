# Quines

A Quine is a program that has the ability to print out its own source code, in it's entirity.

#### A Quine in Ruby

```ruby
source = "\n\ndef hello\n\  puts \"hello\"\nend\n\nputs source =  + source.inspect + source"

def hello
  puts "hello"
end

puts "source = " + source.inspect + source
```

The above code is a quine I have generated. I will go through it and explain what each part does.

The original code in the program is the `hello` method.

```ruby
def hello
  puts "hello"
end
```

So in order for our program to print this code out we need to write it literally within a string such as :

```ruby
"def hello\n\  puts \"hello\"\nend"

def hello
  puts "hello"
end
```
Which will print out:

```
def hello
  puts "hello"
end
```

As you can see we have now printed out the `hello` method, however because we've added the string that prints it to the top of the file, we're going to need to print that out too! The easiest way to do this is to save the contents of a string in a variable,m in this case `source`. We can then `puts source` at the end of the file to print out the contents. Also, because we're adding new code to the bottom of the file we're also going to have to add that code to the string in the `source` variable. We can then call `.inspect` on `source` to literally print out the contents of the `source` variable. The resulting code should look like this:

```ruby
source = "\n\ndef hello\n\  puts \"hello\"\nend\n\nputs source.inspect + source"

def hello
  puts "hello"
end

puts source.inspect + source
```

Which will print out:

```
"\n\ndef hello\n\  puts \"hello\"\nend\n\nputs source.inspect + source"

def hello
  puts "hello"
end

puts source.inspect + source
```

Now we're only missing one piece of information, the `source =` on the first line. This can be fixed by simply printing it before we can the `source.inspect + source`, Like so:

```ruby
source = "\n\ndef hello\n\  puts \"hello\"\nend\n\nputs source =  + source.inspect + source"

def hello
  puts "hello"
end

puts "source = " + source.inspect + source
```

Which will print out exactly:

```
source = "\n\ndef hello\n\  puts \"hello\"\nend\n\nputs source =  + source.inspect + source"

def hello
  puts "hello"
end

puts "source = " + source.inspect + source
```
