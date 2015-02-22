Annotations
-----------

## Comments
- Indentation only with two spaces and never use tabs to messure.
- Comments only when are necessary, Ruby code must be clear and redundant comments must be avoided.
- Good Ruby code should speak for itself, and most of the time you should let it
do its own talking.
- There good reasons for adding comments to your code, the best being to
explain how to use your software masterpiece. These kinds of “how to” comments
should focus on exactly that: how to use the thing. Don’t explain why you wrote it,
the algorithm that it uses, or how you got it to run faster than fast. Just tell me how
to use the thing and remember that examples are always welcome
- The danger in comments that explain how the code works is that they can easily
slide off into the worst reason for adding comments: to make a badly written program somewhat comprehensible.
- Remember, good code is like a good joke: It needs no explanation.

## Classes names and methods
- Classes with CamelCase
- Everywhere else with snake_case_name and constants with UPPER_CASE_NAME

## Parentheses
- Not use when call a method without params:
  
  '''
    @user.all()
  '''
  
  try this way

  '''
    @user.all
  '''

- the same case for method definition

  '''
    def words()

    end
  '''

  try

  '''
    def words

    end
  '''

- and in statements like

  '''
    if (words.size > 100)

    end
  '''

  use

  '''
    if words.size > 100

    end
  '''


