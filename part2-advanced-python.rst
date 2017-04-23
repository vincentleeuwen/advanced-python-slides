=======================
Part 2: Advanced Python
=======================

.. revealjs::

   .. image:: images/advanced_python.jpg
      :height: 650px

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

.. revealjs:: End

    :ref:`Back to overview <slides-index>`
