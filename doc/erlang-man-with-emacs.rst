=======================================
Using the Erlang Man files within Emacs
=======================================

:Home page: https://github.com/pierre-rouleau/about-erlang
:Navigation: Prev_, Top_, Next_
:Time-stamp: <2021-06-06 17:48:13, updated by Pierre Rouleau>
:Copyright:  Copyright © 2020, 2021, Pierre Rouleau
:License: `MIT <../LICENSE>`_

.. _Prev:  whatis-files.rst
.. _Top:   installing-erlang.rst
.. _Next:  specialized-shells.rst

.. contents::  **Table of Contents**
.. sectnum::

.. ---------------------------------------------------------------------------

Setup Goal
==========

Emacs provides excellent support for `man pages`_. The `erlang.el`_ library
provides a menu providing access to the Erlang man files when it is configured
properly.

The goal here is:

- to be able to use this facility to easily access Erlang man pages while also
  having the choice to do the following:

  - *limit* access to non-Erlang man files so that when we search for a man page
    we'll only hit Erlang man pages, or
  - don't limit at all and provide access to *all* man pages available on the
    computer, including the Erlang man pages.

- To also be able to concurrently run several instances of Emacs inside
  specialized OS shells that provide access to a given version of Erlang and
  their version specific man pages and being able to access them from Emacs.
  So if we have a OS shell that runs Erlang 17 and another that runs Erlang
  23, and each one run Emacs in them, then the Emacs running in the first
  shell would have access to the Erlang 17 man pages while the other would
  have access to Erlang 23 man pages.

This document describes how to setup Emacs to achieve this.


For more information on Emacs man page support see:

- `Emacs Man Page Lookup`_
- `WoMan: Browse Unix Manual Pages "W.O. (without) Man"`_

.. ---------------------------------------------------------------------------


Step 1 - Organize your Erlang Man Files
=======================================

Your Erlang installation may or may not include the Erlang man files.
That really depends on how you installed Erlang on your system
as described in the page titled `Installing Erlang`_ sections.
You may also have installed several versions of Erlang.

The method promoted here is to install all Erlang man files inside a directory
tree as described inside the `Install Erlang OTP Documentation and Man Files`_
document.

For example, the man1, man3 and other directories that contain the Erlang man
files for Erlang/OTP 23.3 would be stored inside the directory
``~/docs/Erlang/otp-23.3``.  Note that ``otp-23.3`` could also be a symlink to
the directory holding the ``manN`` directories if the files have been stored
somewhere else.



Step 2 - Configure Emacs Erlang Support
=======================================

Several Emacs packages support Erlang.

The `erlang.el`_ package is required and used by the others.  It provides a
menu listing the man pages by sections.  But it also supports only *one*
version of Erlang at any given time.

The EDTS_ package extends it and does support several versions of Erlang.

You may or may not want to use EDTS_.  Therefore we'll provide a mechanism
that configures `erlang.el`_ for the Erlang version used in the current OS
shell.

The next 2 sections describe how these package handle the Erlang man pages.

Man files Used by the standard Erlang mode (erlang.el)
------------------------------------------------------

The `erlang.el`_ package which is part of the `Erlang source code repo`_,
supports one version of Erlang.

It uses the user-option variable ``erlang-root-dir`` to control the location
of the Erlang man files.  Despite its name of the user-option variable the
directory does not need to hold the Erlang bin or other OTP directory.

The ``erlang-root-dir`` may hold 2 types of values:

- A string that identifies the parent directory of the ``manN`` directories
  holding the man page.  The string must not end with a slash or backslash.
- The nil symbol.  In this case the `erlang.el`_ package checks for the
  presence of the directory ``~/.emacs.d/cache/erlang-mode-man-pages`` and the
  presence of the ``man`` sub-directory holding the ``manN`` directories.

  - If ``~/.emacs.d/cache/erlang-mode-man-pages/man/manN`` is present it uses
    it.
  - If that directory is not present it asks the user to download the man
    files and then installs them inside that directory.

It is therefore possible to force the use of a specific directory for a given
version of Erlang by dynamically setting the value of ``erlang-root-dir``
after the `erlang.el`_ is loaded but before the `erlang-start.el`_ file is loaded.

Man Files Used by EDTS
----------------------

The EDTS_ external package supports multiple versions of Erlang.
And it has the ability to download the Erlang man files for each of them
and store them in a directory specific to that version of Erlang.

The EDTS_ package stores the Erlang man page files inside the directory
``~/.emacs.d/edts/doc/VV/man`` where ``VV`` is the Erlang version.  There can be
several ``VV`` directories, one per Erlang version supported.

For example, EDTS_ would store the files for Erlang version 23.0 inside
``~/.emacs.d/edts/doc/23.0``.  The directory it creates would hold:

.. code:: ls

        -rw-r--r--   1 roup  staff  16239 12 May 17:41 COPYRIGHT
        -rw-r--r--   1 roup  staff    842 12 May 17:41 PR.template
        -rw-r--r--   1 roup  staff   4167 12 May 17:41 README.md
        drwxr-xr-x   7 roup  staff    224 12 May 17:30 man

The important one is the man directory that holds the man1, man3, man4 and
man6 directories that which the Erlang man files.


The Erlang man directory tree
-----------------------------

The Erlang man directory tree for each version of Erlang is similar and looks
like this::

    otp-17.5
      ├── man
          ├── man1
          ├── man3
          ├── man4
          ├── man6
          ├── man7
          └── whatis

Each of the manN contain the Erlang man files except for man7. These
directories contain:

  - man1 : Commands
  - man3 : Modules
  - man4 : Files
  - man6 : Applications
  - man7 : SNMP MIBs

The whatis file is important and provides support for the `whatis utility`_ for
the Erlang man pages.  See `Creating whatis files for Erlang man pages`_ for
more information.


A Consolidation Strategy
------------------------

To limit the copies of Erlang man directory trees, the strategy is to store
the man directories, or symlinks to these directories in on or two locations:

- inside a directory like ``~/docs/Erlang`` that will also hold the Erlang HTML
  documentation files, and
- inside ``~/.emacs.d/edts/doc`` to support EDTS_.


Follow the instructions in the page titled
`Install Erlang OTP Documentation and Man Files`_ if this is not already done,
to store the HTML documentation and man files inside ``~/docs/Erlang``.

Then create the symlinks to the man directory parents inside
``~/.emacs.d/edts/doc/V`` for each Erlang version V.
After creating the symlinks, you should have something like this:

.. code:: shell

    > tree -L 2  ~/.emacs.d/edts/doc
    /Users/roup/.emacs.d/edts/doc
    ├── 17.5
    │   └── man -> /Users/roup/Erlang/docs/otp-17.5/man
    ├── 18.3
    │   └── man -> /Users/roup/Erlang/docs/otp-18.3/man
    ├── 19.3
    │   └── man -> /Users/roup/Erlang/docs/otp-19.3/man
    ├── 20.3
    │   └── man -> /Users/roup/Erlang/docs/otp-20.3/man
    ├── 21.3
    │   └── man -> /Users/roup/Erlang/docs/otp-21.3/man
    ├── 22.2
    │   └── man -> /Users/roup/Erlang/docs/otp-22.2/man
    ├── 22.3
    │   └── man -> /Users/roup/Erlang/docs/otp-22.3/man
    ├── 23.0
    │   └── man -> /Users/roup/docs/Erlang/otp-23.0/man
    └── 23.3
        └── man -> /Users/roup/Erlang/docs/otp-23.3/man

    10 directories, 8 files
    >

Each ~/.emacs.d/edts/doc/otp-XX.Y directory holds one man symlink that points
to the real man directory that holds the manN directories: inside the ~/Erlang/docs/otp-XX.Y directory.

For each of them, the man directories holds the manN directories which contain
the Erlang man files:

::

    ├── man
    │   ├── man1
    │   ├── man3
    │   ├── man4
    │   ├── man6
    │   ├── man7
    │   └── whatis
    └── readme.txt

The ``erlang_man_download_url`` file is created and used
by EDTS_. It contains the URL where the man files can be downloaded.  The
file contains the following single line of text::

  https://erlang.org/download/otp_doc_man_17.5.tar.gz


Once you have this you might want specialized OS shells that will be
supporting a specific version of Erlang. This is described next_.


.. _Installing Erlang: installing-erlang.rst
.. _erlang.el:  https://github.com/erlang/otp/blob/maint/lib/tools/emacs/erlang.el
.. _edts:  https://github.com/sebastiw/edts#readme
.. _Creating whatis files for Erlang man pages:  whatis-files.rst
.. _Erlang source code repo: https://github.com/erlang/otp
.. _erlang.el:  https://github.com/erlang/otp/blob/maint/lib/tools/emacs/erlang.el
.. _man pages: https://en.wikipedia.org/wiki/Man_page
.. _Emacs Man Page Lookup: https://www.gnu.org/software/emacs/manual/html_node/emacs/Man-Page.html
.. _WoMan\: Browse Unix Manual Pages "W.O. (without) Man": https://www.gnu.org/software/emacs/manual/html_node/woman/index.html
.. _Install Erlang OTP Documentation and Man Files: installing-erlang-man-files.rst
.. _erlang-start.el: https://github.com/erlang/otp/blob/maint/lib/tools/emacs/erlang-start.el
.. _whatis utility: https://en.wikipedia.org/wiki/Apropos_(Unix)#Related_utilities
.. _Install Erlang OTP Documentation and Man Files:  installing-erlang-man-files.rst

.. ---------------------------------------------------------------------------
