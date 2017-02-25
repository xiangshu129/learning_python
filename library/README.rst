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
    >>> os.path.isfile('log.txt')
    True
    >>> os.path.isdir('log.txt')
    False
    >>> os.path.pathsep
    ':'
    >>> os.path.sep
    '/'
    >>> os.path.abspath('log.txt')
    '/Users/derek/derek/git_repo/devops/caesar/log.txt'
    >>> os.path.abspath('log.txt').split()
    ['/Users/derek/derek/git_repo/devops/caesar/log.txt']
    >>> os.path.exists('log.txt')
    True
    >>> os.path.getsize('log.txt')
    128
    >>> os.sep
    '/'
    >>> os.path.abspath('log.txt').split(os.sep)
    ['', 'Users', 'derek', 'derek', 'git_repo', 'devops', 'caesar', 'log.txt']

`os.environ <https://docs.python.org/2/library/os.html>`_

**Note** Calling putenv() directly does not change os.environ, so it’s better to modify os.environ

::

    >>> import os
    >>> os.environ['PATH']
    '/Users/derek/.rvm/gems/ruby-2.3.3/bin:/Users/derek/.rvm/gems/ruby-2.3.3@global/bin:/Users/derek/.rvm/rubies/ruby-2.3.3/bin:/Users/derek/.nvm/versions/node/v6.9.5/bin:.:/Users/derek/derek/bin:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/opt/X11/bin:/Users/derek/.rvm/bin'

os.getcwd

os.getpid

os.uname

`time <https://docs.python.org/2/library/time.html>`_

::

    >>> time.sleep(2)
    >>> time.time()
    1487056436.678085
    >>> time.sleep(1)

`timedelta <https://docs.python.org/2/library/datetime.html>`_

::

    >>> from datetime import timedelta
    >>> timedelta(minutes=100)
    datetime.timedelta(0, 6000)
    >>> str(timedelta(minutes=100))
    '1:40:00'

Python 3rd party library
-------------------------

`selenium <http://selenium-python.readthedocs.io/getting-started.html>`_

example::

    from selenium import webdriver
    from selenium.webdriver.common.keys import Keys

    driver = webdriver.Firefox()
    driver.get("http://www.python.org")
    assert "Python" in driver.title
    elem = driver.find_element_by_name("q")
    elem.clear()
    elem.send_keys("pycon")
    elem.send_keys(Keys.RETURN)
    assert "No results found." not in driver.page_source
    driver.close()

    # another way to check
    assert "No results found." not in driver.page_source

    # import capability which is a dict
    from selenium.webdriver.common.desired_capabilities import DesiredCapabilities
    desired_capabilities=DesiredCapabilities.HTMLUNITWITHJS)

    # drag and drop
    element = driver.find_element_by_name("source")
    target = driver.find_element_by_name("target")

    # alerts
    alert = driver.switch_to_alert()

    # window and frame
    driver.switch_to_window("windowName")
    driver.switch_to_frame("frameName")
    driver.switch_to_default_content()

    from selenium.webdriver import ActionChains
    action_chains = ActionChains(driver)
    action_chains.drag_and_drop(element, target).perform()