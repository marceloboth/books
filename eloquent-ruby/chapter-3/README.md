Notes
------

## Literals Shortcuts

From arrays like:
```
poem_words = [ 'twinkle', 'little', 'star', 'how', 'I', 'wonder' ]
```

to:

```
poem_words = %w{ twinkle little star how I wonder }
```

From hashes like:

```
book_info = { :first_name => 'Russ', :last_name => 'Olsen' }

```

to:

```
book_info = { first_name: 'Russ', last_name: 'Olsen' }
```

## Instant Arrays and Hashes from Method Calls

Rely on Ruby to manufacture an array:

```
def echo_all(*args)
  args.each { |arg| puts arg }
end

echo_all('arg1', 'arg2')
```

better than:

```
def echo_all(args)
  args.each { |arg| puts arg }
end

echo_all(['arg1', 'arg2'])
```

Other way is using Hashes:

```
def load_font( specification_hash )
end

# Tradicional form
load_font( { :name => 'times roman', :size => 12 })

# Shorten call
load_font( :name => 'times roman', :size => 12 )

# Call like a command
load_font :name => 'times roman', :size => 12
```

## Running Through Your Collection

The way of running through an Array Collection:

```
words.each { |word| puts word }
```

Hashes also come with a have a `each` method:

```
movie = { title: '2001', genre: 'sci fi', rating: 10 }
movie.each { |entry| pp entry }
```

.find_index:

```
words.find_index { |this_word| word == this_word }
```

.map: Map takes a block and runs through the collection calling the block for each element.

```
words.map { |word| word.size }
```

.inject: Inject passes in two arguments to the block: Along with each element, you get the current result—the current sum if you are adding up all of the word lengths. Each time inject calls the block, it replaces the current result with the return value of the previous call to the block. When inject runs out of elements, it returns the result as its return value.

```
total = words.inject(0.0){ |result, word| word.size + result}
```

If you don’t supply an initial value, inject will skip calling the block for the first element of the array and simply use that element as the initial result.

## Beware the Bang!

Using `!` method changes the collection and methods without `!` makes a copy of the collection don't changing the properly collection.

This only return a copy of the array in a reverse mode:

```
a = [1, 2, 3]
a.reverse => [3,2,1]
a => [1, 2, 3]
```

This will change the entire collection:

```
a = [1, 2, 3]
a.reverse! => [3, 2, 1]
a => [3, 2, 1]
```

Be sure you know what a method is going to do to your collection before you call it with `!` (Bang).

## Rely on the Order of Your Hashes

Arrays and Hashes are ordered by default, even when an existing value is changed.

## In the wild

Ruby Collection are powerful, that often there is no practical reason to create a custom-tailored collection simply to get some specialized feature.

All things being equal, Ruby programmers actually prefer to work with generic collections. To the Ruby way of thinking, one less class is one less thing to go wrong.

## Staying out of trouble

Never change a Collection from a underneath method.

`In coding, as in carpentry, you need the right tool for the job.`
