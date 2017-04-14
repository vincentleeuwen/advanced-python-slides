==============================
Part 0: Introduction to Python
==============================

.. revealjs:: Introduction to Python

    | Python is an interpreted, object-oriented, high-level programming language with dynamic semantics.
    |
    | Python's simple, easy to learn syntax emphasizes readability and therefore reduces the cost of program maintenance.

.. revealjs:: History of Python

    - Invented 1989 by Guido van Rossum, implemented in C
    - Named after Monty Python's Flying Circus (BBC TV-show)
    - Exception handling, functions, core datatypes (list, dict, str etc.)


.. revealjs:: Who uses it?

    - Google
    - Youtube
    - NASA
    - Industrial Light and Magic
    - Walt Disney
    - CIA.gov (python/zope/plone)

.. revealjs:: Welcome to the World of Python

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
    :subtitle: An implementation

    - cPython (reference implementation)
    - Jython
    - IronPython
    - PyPy

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

.. revealjs:: Python versions

    - Python 2.7 (used by us)
    - Python 3.4

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
