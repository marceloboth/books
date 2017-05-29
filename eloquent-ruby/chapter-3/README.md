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

