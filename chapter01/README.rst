Introduction
============

Python is a widely used high-level programming language used for general-purpose programming.

History
-------

- created by `Guido van Rossum <https://en.wikipedia.org/wiki/Guido_van_Rossum>`_
- Python was conceived in the late 1980s, and its implementation began in December 1989
- first released in 1991
- Python 2.0 was released on 16 October 2000
- Python 3.0 was released on 3 December 2008. Many of its major features have been backported to the backwards-compatible Python 2.6.x[33] and 2.7.x version series.

Philosophy
----------

- Beautiful is better than ugly
- Explicit is better than implicit
- Simple is better than complex
- Complex is better than complicated
- Readability counts

Features
--------

- Open source
- Dynamic scripting language
- OO and functional
- Free
- Portable
- Powerful
- Easy to learn and to use

Interpreter
-----------

- `CPython <http://www.python.org>`_
- `PyPy <http://pypy.org/>`_
- `JPython <http://www.jython.org/>`_
- `IronPython <http://ironpython.net/>`_

tips
----

- Python Shell auto completion

生成文件`.pythonrc`::

    # ~/.pythonrc
    # enable syntax completion
    try:
        import readline
    except ImportError:
        print("Module readline not available.")
    else:
        import rlcompleter
        readline.parse_and_bind("tab: complete")

然后加入bash(~/.bashrc)或zsh(~/.zshrc)的rc脚本::

    export PYTHONSTARTUP=~/.pythonrc

- `pip <https://pip.pypa.io/en/stable/>`_

===================================  ==================================================
command                              purppose
===================================  ==================================================
pip install SomePackage              install package
pip list -o                          list outdated packages
pip install --upgrade SomePackage    upgrade a package
pip show --files SomePackage         show installed files for specified package
pip uninstall SomePackage            uninstall a package
pip freeze > requirements.txt        Output installed packages in requirements format
===================================  ==================================================

- `setuptools <https://setuptools.readthedocs.io/en/latest/>`_

Setuptools is a fully-featured, actively-maintained, and stable library designed to facilitate packaging Python projects, where packaging includes::

    * Python package and module definitions
    * Distribution package metadata
    * Test hooks
    * Project installation
    * Platform-specific details
    * Python 3 support

Setuptools is a collection of enhancements to the Python distutils (for Python 2.6 and up) that allow developers to more easily build and distribute Python packages, especially ones that have dependencies on other packages.

syntax reference for `setup.py <https://packaging.python.org/distributing/>`_

example::

    # requirements.txt, whose contents populated by command 'pip freeeze > requirements.txt'
    commentjson==0.6
    selenium==3.0.2

    # file setup.py:
    import os
    import glob
    from setuptools import setup

    requirements = open(
        os.path.join(os.path.dirname(__file__),
                     'requirements.txt')).readlines()

    setup(
        name='caesar',
        version='0.1',
        description='Automatic UI testing framework',
        packages=['caesar'],
        scripts=glob.glob('scripts/*.py'),
        install_requires=requirements,
    )

command example::

    # get help
    python setup.py --help-commands
    # install
    # -e here means using **developer mode** which will link the developing packages directly instead of install it
    pip install -e .
    # or
    python setup.py -e
    # build
    python setup.py build
    python setup.py clean
    python setup.py sdist
    python setup.py bdist

- `virtualenv <https://virtualenv.pypa.io/en/stable/>`_

virtualenv is a tool to create isolated Python environments.

install:
    pip install virtualenv

example::

    virtualenv myenv
    source myenv/bin/activate
    deactivate

- Debug

启动Python解释器时可以用-O参数来关闭assert。关闭后，你可以把所有的assert语句当成pass来看。

::

    $ python err.py
    Traceback (most recent call last):
      ...
    AssertionError: n is zero!

    $ python -O err.py
    Traceback (most recent call last):
      ...
    ZeroDivisionError: integer division or modulo by zero

pdb::

    # err.py
    import pdb

    s = '0'
    n = int(s)
    pdb.set_trace() # 运行到这里会自动暂停
    print 10 / n

- `IPython <http://ipython.org/>`_

Installation::

    pip install ipython

