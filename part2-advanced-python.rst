=======================
Part 2: Advanced Python
=======================

.. revealjs::

   .. image:: images/advanced_python.jpg
      :height: 650px


.. revealjs:: Decimal

    .. rv_code::

        from decimal import Decimal
        Decimal('0.6')

    Float is approx if number can't be built from exact powers of two


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

.. revealjs:: list comprehensions

    .. rv_code::

        >>> [x * 2 for x in range(10) if x % 2 == 0]
        [0, 4, 8, 12, 16]


.. revealjs:: dict comprehensions

    .. rv_code::

        >>> {x: x * 2 for x in range(10) if x % 2 == 0}
        {0: 0, 2: 4, 4: 8, 6: 12, 8: 16}

.. revealjs:: set comprehensions

    .. rv_code::

        >>> squared = {x**2 for x in [1, 1, 2]}
        {1, 4}

.. revealjs:: Decorators

    .. rv_code::

        @lru_cache(maxsize=None)
        def fib(n):
            if n < 2:
                return n
            return fib(n-1) + fib(n-2)

        >>> print([fib(n) for n in range(16)])
        [0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233, 377, 610]

        >>> print(fib.cache_info())
        CacheInfo(hits=28, misses=16, maxsize=None, currsize=16)


.. revealjs:: Lambda functions / map

    Instead of:

    .. rv_code::

        def square(x):
            return x * x

        >>> list(map(square, [2, 3, 4]))
        [4, 9, 16]

    Allows you to write:

    .. rv_code::

        >>> list(map(lambda x: x * x, [2, 3, 4]))
        [4, 9, 16]


.. revealjs:: With statement (context managers)

    .. rv_code::

        >>> with open('/tmp/workfile', 'r') as f:
        ...     read_data = f.read()
        >>> f.closed
        True


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


.. revealjs:: Pretty printing code

    .. rv_code::

        from pprint import pprint

        my_dict = {'name': 'Yasoob', 'age': 'undefined', 'personality': 'awesome'}
        pprint(my_dict)


.. revealjs:: Project time!

    Time for some more hands on practice

    :ref:`Back to overview <slides-index>`
