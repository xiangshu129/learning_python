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
- `IPython <https://ipython.org/>`_
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

===================================  ============================================
command                              purppose
===================================  ============================================
pip install SomePackage              install package
pip list -o                          list outdated packages
pip show --files SomePackage         show installed files for specified package
pip install --upgrade SomePackage    upgrade a package
pip uninstall SomePackage            uninstall a package
===================================  ============================================

- `virtualenv <https://virtualenv.pypa.io/en/stable/>`_

virtualenv is a tool to create isolated Python environments.

install:
    pip install virtualenv

example::

    virtualenv myenv
    source venv/bin/activate
    deactivate