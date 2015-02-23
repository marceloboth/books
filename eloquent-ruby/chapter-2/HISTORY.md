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

