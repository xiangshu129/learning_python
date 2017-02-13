Python Library
==============

Python Standard Library
-----------------------

`logging <https://docs.python.org/2/library/logging.html>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The basic classes defined by the module, together with their functions, are listed below

- Loggers expose the interface that application code directly uses.
- Handlers send the log records (created by loggers) to the appropriate destination.
- Filters provide a finer grained facility for determining which log records to output.
- Formatters specify the layout of log records in the final output.

**Logger**

Loggers have the following attributes and methods. Note that Loggers are never instantiated directly, but always through the module-level function logging.getLogger(name). Multiple calls to getLogger() with the same name will always return a reference to the same Logger object.

::

    >>> import logging
    >>> logging.basicConfig(filename="log.txt", level=logging.DEBUG, format='%(asctime)s - %(name)s - %(levelname)s - %(message)s')
    >>> a = logging.getLogger()
    >>> a.info("from info")
    >>> a.debug("from debug")
    >>> b = logging.getLogger()
    >>> a is b
    True

`subprocess <https://docs.python.org/2/library/subprocess.html>`_
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The subprocess module allows you to spawn new processes, connect to their input/output/error pipes, and obtain their return codes. This module intends to replace several older modules and functions

- os.system
- os.spawn*
- os.popen*
- popen2.*
- commands.*

::

    >>> import subprocess
    >>> subprocess.check_output(['ls', '/']).split()
    ['Applications', 'Library', 'Network', 'System', 'Users', 'Volumes', 'bin', 'cloudconfig', 'cores', 'dev', 'etc', 'home',   'installer.failurerequests', 'net', 'opt', 'private', 'sbin', 'tmp', 'usr', 'var']

`os.path <https://docs.python.org/2/library/os.path.html>`_

::

    >>> a
    '~/.myopenid'
    >>> os.path.expanduser(a)
    '/Users/derek/.myopenid'
    >>> os.path.dirname(a)
    '~'
    >>> os.path.basename(a)
    '.myopenid'

`os.environ <https://docs.python.org/2/library/os.html>`_

**Note** Calling putenv() directly does not change os.environ, so it’s better to modify os.environ

::

    >>> import os
    >>> os.environ['PATH']
    '/Users/derek/.rvm/gems/ruby-2.3.3/bin:/Users/derek/.rvm/gems/ruby-2.3.3@global/bin:/Users/derek/.rvm/rubies/ruby-2.3.3/bin:/Users/derek/.nvm/versions/node/v6.9.5/bin:.:/Users/derek/derek/bin:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/opt/X11/bin:/Users/derek/.rvm/bin'

os.getcwd

os.getpid

os.uname

Python other library
--------------------

