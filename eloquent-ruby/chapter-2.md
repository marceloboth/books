Notes
------

## Control Structure

- Remember to always use ``unless @something`` for negative clauses, instead of ``ìf not @something``
- In exactly the same way that if has unless, while has a negative doppelganger in until: An until 
loop keeps going until its conditional part becomes true. In the same way that Ruby coders avoid 
negated conditions in ifs, we also shy away from negated conditions in while loops.

from:

  ```
    while ! document.is_printed?
      document.print_next_page
    end

  ```

to:

  ```
    until document.is_printed?
      document.print_next_page
    end

  ```

## Modifier forms

- unless:

  ``@title = new_title unless @read_only``

- if:

  ``title = new_title if @writable``

- while:

  ``document.print_next_page while document.pages_available?``

- until:

  ``document.print_next_page until document.printed?``

## Loops

- Avoid ``for loop`` in arrays
- Use each method, the reason is eliminating one level of indirection. When for is called, 
Ruby will call inside the each method.

  ```
    fonts = ['red', 'blue', 'white']

    fonts.each do |font|
      puts font
    end
  ```

## Case

exemple one:

  ```
     author = case title
              when 'War And Peace' the 'Tolstoy'
              when 'Romeo And Juliet' then 'Shakespeare'
              else "Don't know"
              end
  ```

example two:

  ```
    case
    when title == 'War And Peace'
      puts 'Tolstoy'
    when title == 'Romeo And Juliet'
      puts 'Shakespeare'
    else
      puts 'Absolutely no idea...'
    end
  ```

## Staying out of trouble

- Only ``false`` and ``nil`` are treated as false. Everything else are true.
- Because that, using ``nil`` in comparations is dangerous.
- If you are looking for nil and there is any possibility of false turning up, then look
for nil explicitly.

  like:
  
    ``until(next_object = get_next_object) == nil``
    ``until(next_object = get_next_object).nil?``

## Ternary operators

- ``file = all ? 'specs' : 'latest_specs'``
- and: ``@first_name = '' unless @first_name`` to ``@first_name ||= ''``
- Translated into English, the expansion says “Set the new value of @first_name to
the old value of @first_name, unless that is nil, in which case set it to the empty
string.”
- Don’t try to use ||= to initialize things to booleans.

