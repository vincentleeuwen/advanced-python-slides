=======================================
Part 1: Python Syntax and Core Features
=======================================

.. revealjs:: Python Syntax and Core Features

.. revealjs:: Indents matter

    Whitespaces and indents are important in python.

    .. rv_code::

        if condition:
            print('True!')
        else:
            print('False')
        print('moving on')

    VS:

    .. rv_code::

        if condition:
            print('True!')
        else:
            print('False')
            print('moving on')

    Best to use space indentation of 4 spaces.

.. revealjs:: Naming

    - lowercase
    - undescore_between_words (**snake_case**)
    - don't start with numbers

    See https://www.python.org/dev/peps/pep-0008/

.. revealjs:: Variables
    :subtitle: Python is Strongly, Dynamically typed

    Dynamically:

    .. rv_code::

        >>> my_var = 'a string'
        >>> my_var = 5  # run time keeps track of type

    Strongly:

    .. rv_code::

        >>> a_string = 'Hello it is now '
        >>> a_number = 1980
        >>> a_string + a_number
        TypeError: cannot concatenate 'str' and 'int' objects
        >>> a_string + str(a_number)
        'Hello it is now 1980'

.. revealjs:: Objects

   Everything in Python is an object that has:

      - an identity (id)
      - a value (mutable or immutable)

.. revealjs:: ID

   .. rv_code::

      >>> a = 4
      >>> id(a)
      140308434146016

.. revealjs:: Value

   - **Mutable**: When you alter the item, the *id* is still the same.

     - Dictionary, List.

   - **Immutable**

     - String, Integer, Tuple

.. revealjs:: Mutable

   .. rv_code::

      >>> b = []
      >>> id(b)
      4560462696
      >>> b.append(3)
      >>> b
      [3]
      >>> id(b)
      4560462696 # SAME!

.. revealjs:: Immutable

   .. rv_code::

      >>> a = 4
      >>> id(a)
      4322130288
      >>> a = a + 1
      >>> id(a)
      4322130320 # DIFFERENT!

.. revealjs:: Math

   ``+, -, *, /, ** (power), % (modulo)``

  .. rv_code::

     >>> 6 % 2
     0

.. revealjs:: Strings

   .. rv_code::

      name = 'remco'
      with_quote = "I ain't gonna"
      longer = """This string has
      multiple lines
      in it"""

   Escape with backslash

   .. rv_code::

      >>> print('He said, "I\'m sorry"')
      He said, "I'm sorry"

.. revealjs:: String interpolation

   Positional:

   .. rv_code::

       >>> print('Let me {0}, that is {1}'.format('see', 'strange'))
       Let me see, that is strange

   Key based:

   .. rv_code::

       >>> print('Hi {name}, you are {age} years old.'.format(name='joeri', age=35))
       Hi joeri, you are 35 years old

.. revealjs:: Methods & dir

   List attributes and methods:

   .. rv_code::

      >>> dir("a string")
      ['__add__', '__class__', '__contains__', ... , 'translate', 'upper', 'zfill']

      >>> "a string".upper()
      'A STRING'

.. revealjs:: Help

    .. rv_code::

       >>> help("a string".upper)
       Help on built-in function upper:
        upper(...) method of builtins.str instance
            S.upper() -> str

            Return a copy of S converted to uppercase.

.. revealjs:: Base types

    - numerics
    - sequences
    - mappings
    - files
    - classes
    - instances
    - exceptions

.. revealjs:: Sequences

    String, List, Tuple (unmutable list), Set

    .. rv_code::

        >>> a_string = 'Hello world'  # ' and " are the same in Python
        >>> a_list = ['hello', 'world']
        >>> a_tuple = ('hello', 'world')  # Mind single element form: ('hello', )
        >>> a_set = {'hello', 'world'}


.. revealjs:: List operations

   .. rv_code::

       >>> a_list = ['hello']
       >>> a_list.append('world')
       >>> 'world' in a_list
       True

   .. rv_code::

       >>> a_list + ['again']  # Concatenation
       ['hello', 'world', 'again']

       >>> new_list = ['get', 'only', 'part', 'of', 'me', 'now']
       >>> new_list[2:5]  # slicing
       ['part', 'of', 'me']

   .. rv_code::

       >>> len(a_list)  # length
       2

       >>> max([1, 99, 6])  # also min()
       99
       >>> a_list.index('world')
       1

.. revealjs:: Handy list methods

   - l.append(x)

     - Insert x at end of list

   - l.sort()

     - In place sort

   - l.reverse()

     - Reverse list in place

   - l.remove(item)

     - Remove first *item* found

   - l.pop()

     - Remove / return item at end of list

   .. rv_code::

      >>> dir([])
      ['__add__', '__class__', ..., 'insert', 'pop', 'remove', 'reverse', 'sort']

.. revealjs:: Set special powers

    Set is unordered collection of distinct objects

    .. rv_code::

        >>> {'hello', 'hello'}
        {'hello'}

    Can compute mathematical operations with them:

    .. rv_code::

        >>> {'hello', 'world'} & {'other', 'world'}  # intersection
        {'world'}

        >>> {'hello', 'world'} ^ {'other', 'world'}  # symmetric difference
        {'hello', 'other'}

.. revealjs:: Mappings

    Dictionary

    .. rv_code::

        >>> a_dict = {'key': 'value', 'another_key': 'another_value'}

    And its operations:

    .. rv_code::

        >>> a_dict['key']
        'value'
        >>> 'key' in a_dict
        True
        >>> a_dict['key'] = 'new_value'
        {'key': 'new_value', 'another_key': 'another_value'}
        >>> del a_dict['another_key']
        {'key': 'new_value'}

.. revealjs:: Dictionary

    - Also called *hashmap* or *assiociative array* elsewhere
    - Syntax shows similiarities to ``JSON``

    .. rv_code::
        // JSON
        {
          "name": "Bruce Wayne",
          "age": 30,
          "superhero": true
        }

    .. rv_code::
        # Python
        {
          "name": "Bruce Wayne",
          "age": 30,
          "superhero": True
        }

.. revealjs:: Boolean logic

    .. rv_code::

        >>> print(True and False)
        False
        >>> print(not(True or False))
        False

.. revealjs:: Boolean note

    Parenthesis are only required for precedence

    .. rv_code::

        if (x > 10):
            print("Big")

    Same as:

    .. rv_code::

        if x > 10:
            print("Big")

.. revealjs:: Comparisons

    .. rv_code::

        a = 3
        b = None

        >>> print(a == 3)  # Compares equality
        True
        >>> print(b is None)  # Compares identity: reference to same object
        True

    And all the usual suspects: ``< <= > >= != ==``

.. revealjs:: Chained comparisons

    .. rv_code::

        if 3 < x < 5:
            print("Four!")

    Same as:

    .. rv_code::

        if x > 3 and x < 5:
            print("Four!")

.. revealjs:: What is False?

    - ``None``

      - Pythonic way of saying ``NULL``. Evaluates to ``False``

    - ``False``
    - zero of any numeric type, for example: 0, 0.0
    - any empty sequence, for example: '', (), []
    - any empty mapping, for example: {}

.. revealjs:: If statements

    .. rv_code::

        if age > 50:
            print('old & wise')
        elif age >= 40:
            print('getting there')
        elif age >= 30:
            print('rookie')
        else:
            print('youngster')

.. revealjs:: Iteration (1)

    For loops always iterate over items in a sequence:

    .. rv_code::

        >>> words = ['cat', 'window', 'defenestrate']
        >>> for w in words:
        ...     print w, len(w)
        cat 3
        window 6
        defenestrate 12

    To iterate over numbers, use range():

    .. rv_code::

        >>> range(5, 10)
        [5, 6, 7, 8, 9]
        >>> range(0, 10, 3)
        [0, 3, 6, 9]
        >>> range(-10, -100, -30)
        [-10, -40, -70]

.. revealjs:: Iteration (2)

    Java/C-esque style of objects in array access (BAD)

    .. rv_code::

        animals = ['cat', 'dog', 'bird']
        for index in range(len(animals)): # DON'T DO THIS!
            print(index, animals[index])

.. revealjs:: Iteration (3)

    .. rv_code::

        animals = ['cat', 'dog', 'bird']
        for animal in animals:
            print(animal)

    If you need indices, use ``enumerate``

    .. rv_code::

        animals = ['cat', 'dog', 'bird']
        for index, value in enumerate(animals):
            print(index, value)

.. revealjs:: Iteration (4)

    Can ``break`` out of nearest loop

    .. rv_code::

        for item in sequence:
            # process until first negative
            if item < 0:
                break
            # process item

.. revealjs:: Iteration (5)

    Can ``continue`` to skip over items

    .. rv_code::

        for item in sequence:
            if item < 0:
                continue
            # process all positive items

.. revealjs:: Iteration (6)

    Loop over dictionaries:

    .. rv_code::

        my_dict = {"name":"matt", "cash": 5.45}

        for key in my_dict.keys():
            # process keys

        for value in my_dict.values():
            # process values

        for key, value in my_dict.items():
            # process items

.. revealjs:: While loops

    .. rv_code::

        temperature = 115
        while temperature > 112: # first while loop code
            print(temperature)
            temperature = temperature - 1

        print('The tea is cool enough.')

.. revealjs:: Hint

    .. image:: images/train.jpeg
      :height: 300px

    Don't modify *list* or *dictionary* contents while looping over them.

.. revealjs:: Functions

    .. rv_code::

        def add(x, y):
            return x + y

        >>> add(1, 3)
        4

    With default value for parameter:

    .. rv_code::

        def add(x, y=0, z=1):
            return (x + y) * z

        >>> add(1, 3)
        4
        >>> add(1)
        1
        >>> add(1, z=2)
        2

.. revealjs:: *args and **kwargs

    .. rv_code::

        def add(*args):
            return args[0] + args[1]

        >>> add(1, 3)
        4

    .. rv_code::

        def add(**kwargs):
            return kwargs['x'] + kwargs['y']

        >>> add(x=1, y=3)
        4

.. revealjs:: Nested functions

    .. rv_code::

        def add(x, y):
            def inner_add(x,y)
                return x + y

            return inner_add(x, y)

        >>> add(1, 3)
        4

.. revealjs:: Classes

    .. rv_code::

        class Animal:
            def __init__(self, name):
                self.name = name

        def talk(self):
            print("Generic animal sound")

        animal = Animal(name="thing")
        animal.talk()

.. revealjs:: Classes (2)

    Notes:

    - *dunder* ``__init__`` (constructor)
    - all methods take ``self`` as first parameter

.. revealjs:: Classes (3)

    Subclassing

    .. rv_code::

        class Cat(Animal):
            def talk(self):
                print('{0} says, "Meow!"'.format(self.name))

        cat = Cat('Felix')
        cat.talk() # invoke method

.. revealjs:: Classes (4)

    Naming

    - CamelCase
    - Don't start with numbers
    - Nouns

      *A noun is a word that functions as the name of some specific thing or set of things, such as living creatures, objects, places, actions, qualities, states of existence, or ideas.*

.. revealjs:: Comments

    .. rv_code::

        # Make funny remark about age
        if age > 50:
            print('old & wise')  # Inline comment

.. revealjs:: Docstrings

    .. rv_code::

        def square_root(n):
            """Calculate the square root of a number.

            Args:
                n: the number to get the square root of.
            Returns:
                the square root of n.
            Raises:
                TypeError: if n is not a number.
                ValueError: if n is negative.

            """
            pass

.. revealjs:: Docstrings (2)

    Function *docstrings* are accessible via **__doc__** or **help**

    .. rv_code::

        >>> help(square_root)
        Help on function square_root in module __main__:

        square_root(n)
            Calculate the square root of a number.

            Args:
                n: the number to get the square root of.
            Returns:
                the square root of n.
            Raises:
                TypeError: if n is not a number.
                ValueError: if n is negative.

.. revealjs:: Docstrings (3)

    Classes

    .. rv_code::

        class Cheetah(Cat):
        '''classes can have
        docstrings'''

            def talk(self):
                print('Growl')

.. revealjs:: Now for the Python ecosystem

.. revealjs:: PEP-8

    The python styleguide: https://www.python.org/dev/peps/pep-0008/

.. revealjs:: Documentation links

    - https://docs.python.org/3/library/index.html

.. revealjs:: End

    :ref:`Back to overview <slides-index>`
