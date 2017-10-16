# Regular Expressions (RegEx)

A regular expression is a sequence of characters that define a search pattern. Regular expressions are gnerally used by string searching algorithms in "find" or "find and replace" operations.

### The Pattern Matching Operator

When one operand is a regular expression and the other is a string, the `=~` operator is used to "match" the regular expression pattern against the string. **If a match is found, the operator returns the index of the first match in the string, otherwise it returns nil**

Given that in Ruby, everything except `nil` and `false` evaluate to the boolean `true` the `=~` operator can be used to evaluate whether a string contains/matches a specific pattern and return a `true` or `false` value. Very handy!

### Matching a Letter

I will use the `.gsub` method for a lot of these examples. `.gsub.` allows you to replace the contents of a string that match your RegEx pattern's criteria. It is possible to match a single letter using RegEx in the same way that you would a string.

For example:

```ruby
words = "alphabet"

words.gsub("a", "_")

#will have the same result as

word.gsub(/a/, "_")

words #=> _lph_bet
```

### Matching a Number

To match a specific number you can use the same approach as above, but replacing the a with the digit required.

However to more powerfully search for ANY digit you can use `\d`. The preceding `\` highlights that `\d` is a meta-character and distinguishes it from `d`.

```ruby
string = "string123"

string.gsub(/\d/, "_") #=> "string___"
```

Here `.gsub` will replace all instances of any digit with `"_"`.

### The Dot

`.` represents a wildcard. That is designating `/./` can match ANY single character. This means that in order to specifically match the `.` period character the dot has to be escaped like so `/\./`.

Thus:

```ruby
string = "1.2.3"
string.gsub(/./, "_") #=> "_____"

#while

string = "1.2.3"
string.gsub(/\./, "_") #=> "1_2_3"
```

Notice the escaped dot `(/\./)` in the second example.

### Matching Specific characters

It is possible to match multiple specific characters by using square brackets `[]`. For example the pattern `/[abc]/` will match a single a, b or c and nothing else.

```ruby
"abacus" =~ /[abc]/ #=> 0
```

In the above example, the first index at which ANY of the letters a, b or c appear is index 0. A neat trick, if you absolutely want to return a boolean value is to place `!!` in front of your code like so.

```ruby
!!("abacus" =~ /[abc]/) #=> true
```
`!` converts a value to its opposite boolean value, so two converts it to it's real boolean.
