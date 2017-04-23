==============================
Part 0: Introduction to Python
==============================

.. revealjs:: Introduction to Python

    | Python is an interpreted, object-oriented, high-level programming language with dynamic semantics.
    |
    | Python's simple, easy to learn syntax emphasizes readability and therefore reduces the cost of program maintenance.

.. revealjs:: History of Python

    .. image:: images/monty_python.png
       :height: 400px

    - Invented 1989 by Guido van Rossum, implemented in C
    - Named after Monty Python's Flying Circus (BBC TV-show)


.. revealjs:: History of Python
    :subtitle: started by Guido van Rossum in 1989

    .. image:: images/guido_rossum.png
       :height: 300px


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
    - Instagram
    - nu.nl
    - NASA
    - Industrial Light and Magic
    - Walt Disney
    - CIA.gov

.. revealjs:: Welcome to the World of Python

    .. image:: images/lotr.png
       :height: 500px

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
    - Frontend development (doesn't run in browser like JS)


.. revealjs:: Bootstrapping

    If you have the vagrant box already installed, do the following:

    .. rv_code::

        $ vagrant ssh
        $ /opt/rh/python27/root/bin/virtualenv env
        $ source env/bin/activate
        $ cd /vagrant


.. revealjs:: Virtualenv

    Isolated Python environments.

    Create one by:

    .. rv_code::

        $ virtualenv -p python3 myvenv
        Running virtualenv with interpreter /usr/local/bin/python3
        Using base prefix '/usr/local/Cellar/python3/3.6.1/Frameworks/Python.framework/Versions/3.6'
        New python executable in /Users/vincentvanleeuwen/Desktop/venv/bin/python3.6
        Also creating executable in /Users/vincentvanleeuwen/Desktop/venv/bin/python
        Installing setuptools, pip, wheel...done.

    Then activate it:

    .. rv_code::

        $ source myenv/bin/activate
        (myenv) $ pip install ipython
        Collecting ipython
        Downloading ipython-6.0.0-py3-none-any.whl (736kB)
          100% |████████████████████████████████| 737kB 1.3MB/s

        etc...

.. revealjs:: pip

    Tool for installing Python packages

    Add dependencies in requirements.txt:

    .. rv_code::

        ipython==6.0.0

    Install with:

    .. rv_code::

        $ pip install -r requirements.txt

.. revealjs:: iPython / bPython

    Better Python shells:

    .. image:: images/python_vs_ipython.jpg
        :alt: Python vs iPython shell


.. revealjs:: iPython

    You should now see the iPython shell:

    .. rv_code::

        Python 3.6.1 (default, Apr  4 2017, 09:40:51)
        [GCC 4.2.1 Compatible Apple LLVM 8.0.0 (clang-800.0.42.1)] on darwin
        Type "help", "copyright", "credits" or "license" for more information.

        Python 3.6.1 (default, Apr  4 2017, 09:40:51)
        Type 'copyright', 'credits' or 'license' for more information
        IPython 6.0.0 -- An enhanced Interactive Python. Type '?' for help.

        In [1]:

    Type: 'hello world'

    .. rv_code::

        In [1]: 'hello world'
        Out[1]: 'hello world'

    Yay, our first running code in Python!

.. revealjs:: Build the slides

    If you want the slides locally on your computer:

    .. rv_code::

        $ git clone https://bitbucket.org/cours/advanced-python-slides.git
        $ cd advanced-python-slides
        $ pip install -r requirements.txt
        $ mkdir _static
        $ make html
        $ open _build/html/index.html

.. revealjs:: End

    :ref:`Back to overview <slides-index>`
