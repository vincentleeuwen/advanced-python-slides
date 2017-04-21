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

    And their operations:

    .. rv_code::

        >>> 'hello' in a_list
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

.. revealjs:: String interpolation

    Positional:

    .. rv_code::

        >>> print('Let me {0}, that is {1}'.format('see', 'strange'))
        Let me see, that is strange

    Key based:

    .. rv_code::

        >>> print('Hi {name}, you are {age} years old.'.format(name='joeri', age=35))
        Hi joeri, you are 35 years old

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


.. revealjs:: Boolean logic

    .. rv_code::

        >>> print(True and False)
        False
        >>> print(not(True or False))
        False

.. revealjs:: Comparisons

    .. rv_code::

        a = 3
        b = None

        >>> print(a == 3)  # Compares equality
        True
        >>> print(b is None)  # Compares identity: reference to same object
        True

    And all the usual suspects: < <= > >= != ==

.. revealjs:: What is False?

    - None
    - False
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


.. revealjs:: For loops

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

.. revealjs:: While loops

    .. rv_code::

        temperature = 115
        while temperature > 112: # first while loop code
            print(temperature)
            temperature = temperature - 1

        print('The tea is cool enough.')

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

.. revealjs:: Absolute importing

    Stuff that you want to import should be on your python path.
    Pip takes care of that for you.

    .. rv_code::

        >>> import os.path
        >>> os.path.join('my', 'path')
        'my/path'
        >>> from os import path
        >>> path.join('my', 'path')
        'my/path'
        >>> from os.path import join
        >>> join('my', 'path')
        'my/path'

    Never do this:

    .. rv_code::

        >>> from os.path import *  # DON'T DO THIS

    Unless you know what you are doing ;)

.. revealjs:: Relative importing

    .. rv_code::

        .
        └── hello_world
            ├── properties
            │   ├── tests
            |   │   ├── __init__.py
            |   |   └── test_models.py
            │   ├── __init__.py
            │   ├── forms.py
            │   └── models.py
            ├── __init__.py
            └── main.py

    In forms.py:

    .. rv_code::

        from .models import MyModel
        from ..main import some_function
        from .tests.test_models import MyTest

    Can also do absolute:

    .. rv_code::

        from hello_world.properties.models import MyModel  # can be less flexible

.. revealjs:: List comprehensions

    .. rv_code::

        >>> [x * 2 for x in range(10) if x % 2 == 0]
        [0, 4, 8, 12, 16]

.. revealjs:: Lambda functions
    :subtitle: Anonymous functions

    Instead of:

    .. rv_code::

        def filterfunc(x):
            return x % 3 == 0

        >>> filter(filterfunc, [1, 2, 3, 4, 5, 6, 7, 8, 9])
        [3, 6, 9]

    Allows you to do:

    .. rv_code::

        >>> filter(lambda x: x % 3 == 0, [1, 2, 3, 4, 5, 6, 7, 8, 9])
        [3, 6, 9]


.. revealjs:: Exceptions

    .. rv_code::

        import sys

        try:
            f = open('myfile.txt')
            s = f.readline()
            i = int(s.strip())
        except IOError as e:
            print "I/O error({0}): {1}".format(e.errno, e.strerror)
        except ValueError:
            print "Could not convert data to an integer."
        except:
            print "Unexpected error:", sys.exc_info()[0]
            raise
        else:
            print "only when try has no exception raised"
        finally:
            print "I'm always executed"

.. revealjs:: Ternary operator

    .. rv_code::

        >>> 'true' if True else 'false'
        'true'
        >>> 'true' if False else 'false'
        'false'

.. revealjs:: Now for the Python ecosystem

.. revealjs:: Virtualenv

    Isolated Python environments.

    Create one by:

    .. rv_code::

        $ virtualenv myenv
        New python executable in myenv/bin/python2.7
        Also creating executable in myenv/bin/python
        Installing setuptools, pip...done.

    Then activate it:

    .. rv_code::

        $ source myenv/bin/activate
        (myenv) $ pip install Django
        Downloading/unpacking Django
            Downloading Django-1.7.4-py2.py3-none-any.whl (7.4MB): 7.4MB downloaded
        Installing collected packages: Django
        Successfully installed Django
        Cleaning up...

.. revealjs:: pip

    Tool for installing Python packages

    Add dependencies in requirements.txt:

    .. rv_code::

        Django==1.7.4
        ipython==2.3.1

    Install with:

    .. rv_code::

        $ pip install -r requirements.txt

.. revealjs:: iPython / bPython

    Better Python shells:

    .. image:: ../images/python_vs_ipython.jpg
        :alt: Python vs iPython shell

.. revealjs:: PEP-8

    The python styleguide: https://www.python.org/dev/peps/pep-0008/


.. revealjs:: Documentation links

    - https://docs.python.org/2/library/index.html

.. revealjs:: End

    :ref:`Back to Python Basics <python-basics-index>`
