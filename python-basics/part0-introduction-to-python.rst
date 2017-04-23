==============================
Part 0: Introduction to Python
==============================

.. revealjs:: Introduction to Python

    | Python is an interpreted, object-oriented, high-level programming language with dynamic semantics.
    |
    | Python's simple, easy to learn syntax emphasizes readability and therefore reduces the cost of program maintenance.

.. revealjs:: History of Python

    .. image:: ../images/monty_python.png

    - Invented 1989 by Guido van Rossum, implemented in C
    - Named after Monty Python's Flying Circus (BBC TV-show)


.. revealjs:: History of Python
    :subtitle: started by Guido van Rossum in 1989

    .. image:: ../images/guido_rossum.png


.. revealjs:: History of Python

    1989: Python 0.0
      - Exception handling
      - Functions
      - Core datatypes (list, dict, str etc.)
    1994: Python 1.0
      - Lambda, map, filter, reduce
    2000: Python 2.0
      - Backward compatible with 1.6
      - Garbage collection
      - Unicode support
      - List comprehensions
    2008: Python 3.0
      - Backward incompatible

.. revealjs:: Python 2 vs Python 3

    - Little difference for beginners, except print vs print()
    - Python 2.x ends at 2.7, no new major releases
    - 3.x is under active development, latest version is 3.6.1
    - Possible to run both on same machine


.. revealjs:: Python 2 vs Python 3
    :subtitle: print vs print()

    Python 2:

    .. rv_code::

        print 'Foo'

    Python 3:

    .. rv_code::

        print('Foo')


.. revealjs:: Python 2 vs Python 3
    :subtitle: Arithmetic

    Python 2:

    .. rv_code::

        1/2 = 0

    Python 3:

    .. rv_code::

        1 / 2 = 0.5
        1 // 2  = 0 # old behaviour


.. revealjs:: Python 2 vs Python 3
    :subtitle: Comparisons

    Python 2:

    .. rv_code::

        >>> 42 < 'hello'
        True

    Python 3:

    .. rv_code::

        >>> 42 < 'hello'
        Traceback (most recent call last):
        File "<stdin>", line 1, in <module>
        TypeError: unorderable types: int() < str()

.. revealjs:: What is Python?
    :subtitle: An implementation

    - cPython (reference implementation)
    - Jython (Python running on Java Virtual Machine)
    - IronPython (C#, C++ compatible)
    - PyPy
    - Stackless Python
    - MicroPython

.. revealjs:: Who uses it?

    - Google
    - Youtube
    - NASA
    - Industrial Light and Magic
    - Walt Disney
    - CIA.gov

.. revealjs:: Welcome to the World of Python

    .. image:: ../images/lotr.png

.. revealjs:: What is Python?
    :subtitle: The language

     High level, general purpose, interpreted programming language.

    - And a funny mix of programming paradigms:
        - Imperative
        - Object Oriented
        - Functional
        - Reflective & Dynamic

.. revealjs:: What is Python?
    :subtitle: Design philosophy

    - Programmer productivity, by emphasizing:
        - Readability
        - Expressiveness


.. revealjs:: What is Python?
    :subtitle: An ecosystem

    An ecosystem of high quality, well tested, well documented code.

    https://pypi.python.org

.. revealjs:: What is Python?
    :subtitle: A community

    | An open, welcoming and engaged community of people that care about software.
    |
    | Code of conduct: be open, considerate, respectful
    |
    | https://www.python.org/psf/codeofconduct/


.. revealjs:: When to use Python

    - Websites & APIs (Django, Flask, Bottle)
    - Data science / AI (Scipy, Numpy, Tensorflow)
    - Internet of things (Raspberry pi, Arduino)
    - Desktop apps
    - Scripting
    - Scraping / Web crawling (Beautifulsoup / Scrapy)

.. revealjs:: When NOT to use Python

    - Mobile apps on iOS or Android
    - Frontend development


.. revealjs:: Bootstrapping

    If you have the vagrant box already installed, do the following:

    .. rv_code::

        $ vagrant ssh
        $ /opt/rh/python27/root/bin/virtualenv env
        $ source env/bin/activate
        $ cd /vagrant

    Add the following line to requirements.txt:

    .. rv_code::

        ipython==2.3.1

    Then run:

    .. rv_code::

        $ pip install -r requirements.txt
        $ ipython

.. revealjs:: iPython

    You should now see the iPython shell:

    .. rv_code::

        Python 2.7.8 (default, Oct 19 2014, 16:03:53)
        Type "copyright", "credits" or "license" for more information.

        IPython 2.3.1 -- An enhanced Interactive Python.
        ?         -> Introduction and overview of IPython's features.
        %quickref -> Quick reference.
        help      -> Python's own help system.
        object?   -> Details about 'object', use 'object??' for extra details.

        In [1]:

    Type: 'hello world'

    .. rv_code::

        In [1]: 'hello world'
        Out[1]: 'hello world'

    Yay, our first running code in Python!

.. revealjs:: Build the slides

    If you want the slides locally on your computer:

    .. rv_code::

        $ git clone https://bitbucket.org/django-bootcamp/slides.git
        $ cd slides
        $ pip install -r requirements.txt
        $ make html
        $ open _build/html/index.html

.. revealjs:: End

    :ref:`Back to Python Basics <python-basics-index>`
