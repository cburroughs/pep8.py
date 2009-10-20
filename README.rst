pep8 - Python style guide checker
=================================

pep8 is a tool to check your Python code against some of the style conventions
in `PEP 8`_.

.. _PEP 8: http://www.python.org/dev/peps/pep-0008/


Features
--------

* Plugin architecture: Adding new checks is easy.

* Parseable output: Jump to error location in your editor.

* Small: Just one Python file, requires only stdlib.  You can use just the
  pep8.py file for this purpose

* Easy_installable, of course!


Installation
------------

Just an ``easy_install pep8`` ought to do the trick.


Example usage and output
------------------------

::

  $ pep8 optparse.py
  optparse.py:69:11: E401 multiple imports on one line
  optparse.py:77:1: E302 expected 2 blank lines, found 1
  optparse.py:88:5: E301 expected 1 blank line, found 0
  optparse.py:222:34: W602 deprecated form of raising exception
  optparse.py:347:31: E211 whitespace before '('
  optparse.py:357:17: E201 whitespace after '{'
  optparse.py:472:29: E221 multiple spaces before operator
  optparse.py:544:21: W601 .has_key() is deprecated, use 'in'

You can also make pep8.py show the source code for each error, and
even the relevant text from PEP 8::

  $ pep8 --show-source --show-pep8 testsuite/E111.py
  testsuite/E111.py:2:3: E111 indentation is not a multiple of four
    print x
    ^
      Use 4 spaces per indentation level.

      For really old code that you don't want to mess up, you can
      continue to use 8-space tabs.

Or you can display how often each error was found::

  $ pep8 --statistics -qq --filename=*.py Python-2.5/Lib
  232     E201 whitespace after '['
  599     E202 whitespace before ')'
  631     E203 whitespace before ','
  842     E211 whitespace before '('
  2531    E221 multiple spaces before operator
  4473    E301 expected 1 blank line, found 0
  4006    E302 expected 2 blank lines, found 1
  165     E303 too many blank lines (4)
  325     E401 multiple imports on one line
  3615    E501 line too long (82 characters)
  612     W601 .has_key() is deprecated, use 'in'
  1188    W602 deprecated form of raising exception

Quick help is available on the command line::

  $ pep8 -h
  usage: pep8 [options] input ...

  options:
    -h, --help           show this help message and exit
    -v, --verbose        print status messages, or debug with -vv
    -q, --quiet          report only file names, or nothing with -qq
    --exclude=patterns   skip matches (default .svn,CVS,*.pyc,*.pyo)
    --filename=patterns  only check matching files (e.g. *.py)
    --ignore=errors      skip errors and warnings (e.g. E4,W)
    --repeat             show all occurrences of the same error
    --show-source        show source code for each error
    --show-pep8          show text of PEP 8 for each error
    --statistics         count errors and warnings
    --benchmark          measure processing speed
    --testsuite=dir      run regression tests from dir
    --doctest            run doctest on myself


Feedback
--------

Your feedback is more than welcome. Write email to
johann@browsershots.org or post bugs and feature requests here:

http://trac.browsershots.org/newticket?component=devtools

As this seems down at the moment, the alternative is:

http://github.com/cburroughs/pep8.py/issues


Source download
---------------

Officially, the file pep8.py (and a regression test suite) is available from
the Browsershots subversion repository, under the Expat license:

http://svn.browsershots.org/trunk/devtools/pep8/

You can also look at the source code and change history online:

http://trac.browsershots.org/browser/trunk/devtools/pep8/pep8.py

**Current alternative location**. NOTE: the browsershots svn repository seems
down, an accessible version is found on github.  This also includes some
extra fixes and a ``setup.py``:

http://github.com/cburroughs/pep8.py/tree/master


