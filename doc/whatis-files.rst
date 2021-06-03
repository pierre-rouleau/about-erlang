==========================================
Creating whatis files for Erlang man pages
==========================================

:Home page: https://github.com/pierre-rouleau/about-erlang
:Navigation: Prev_, Top_, Next_
:Time-stamp: <2021-06-03 16:15:44, updated by Pierre Rouleau>
:Copyright:  Copyright © 2020, 2021, Pierre Rouleau
:License: `MIT <../LICENSE>`_

.. _Prev:  installing-erlang-man-files.rst
.. _Top:   installing-erlang.rst
.. _Next:  erlang-man-with-emacs.rst


.. contents::  **Table of Contents**
.. sectnum::

.. ---------------------------------------------------------------------------

The whatis utility
==================

Several tools, including Emacs, take advantage of the Unix `whatis utility`_.
With ``whatis`` you can query the list of topics available in the various ``man``
pages installed in your system.  Here's a session using ``whatis`` to get man
topics about ``man`` and ``whatis``:

.. code:: shell

    > whatis erl
    ct_telnet(3)             - Common Test specific layer on top of Telnet client ct_telnet_client.erl
    erl(1)                   - The Erlang emulator
    >

    > whatis epmd
    epmd(1)                  - Erlang Port Mapper Daemon
    erl_epmd(3)              - Erlang interface towards epmd
    >

    > whatis mnesia
    mnesia(3)                - A distributed telecommunications DBMS
    mod_auth(3)              - User authentication using text files, Dets, or Mnesia database
    qlc(3)                   - Query interface to Mnesia, ETS, Dets, and so on
    >

    > whatis lfe
    lfe(1)                   - Lisp Flavoured Erlang (LFE) shell
    lfe_bits(3)              - Lisp Flavoured Erlang (LFE) common binary functions
    lfe_cl(3)                - LFE Common Lisp interface library
    lfe_clj(3), clj(3)       - LFE Clojure interface library
    lfe_comp(3)              - Lisp Flavoured Erlang (LFE) compiler
    lfe_doc(3)               - Lisp Flavoured Erlang (LFE) documentation parser
    lfe_gen(3)               - Lisp Flavoured Erlang (LFE) dynamic code generator
    lfe_io(3)                - Lisp Flavoured Erlang (LFE) io functions
    lfe_lib(3)               - Lisp Flavoured Erlang (LFE) library module
    lfe_macro(3)             - Lisp Flavoured Erlang (LFE) macro expander
    lfe_types(7)             - LFE Types and Functions Specifications
    lfescript(1)             - Lisp Flavoured Erlang (LFE) scripting support
    >

    > whatis elixir
    elixir(1)                - The Elixir script runner
    elixirc(1)               - The Elixir compiler
    iex(1)                   - The Elixir shell
    >

The ``whatis`` utility uses a whatis file.  On most Unix-like systems, the man
page directory contains the whatis file. Unfortunately the man directories
available in the `Erlang/OTP download`_ page do not have this file preventing
you from being able to get a list of topics for Erlang.

The next section show how you can build this file for the Erlang man files.

.. ---------------------------------------------------------------------------

Create the whatis file for Erlang man directories
=================================================

To build a missing whatis file,
you need the `makewhatis command line utility`_.
On macOS, this executable is stored in ``/usr/libexec/makewhatis``.

To only create the missing whatis file, you must first set ``MANPATH`` to the
directory holding the ``man1``, ``man3``, ``man4`` and ``man6``
directories.

Once you have that set up, you can run ``/usr/libexec/makewhatis`` and it will
create the whatis file in that directory and will not touch anything else.

To simplify the process you can copy the ``make-local-whatis`` script to a
directory on your path and use that.


The make-local-whatis script
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

I wrote the following Bash script to simplify the process:

.. code::  bash

    #!/bin/sh
    # SH FILE: make-local-whatis
    #
    # Purpose   : Create a man whatis file for local man directory tree.
    # Created   : Friday, July 17, 2020
    # Author    : Pierre Rouleau <prouleau001@gmail.com>
    # Time-stamp: <2021-05-18 17:19:52, updated by Pierre Rouleau>
    # Copyright © 2020, 2021, Pierre Rouleau
    # License   : MIT
    # ----------------------------------------------------------------------------
    # Description
    # -----------
    #
    #
    # Usage: make-local-whatis directory
    #
    # Examples:
    #      make-local-whatis ~/docs/Erlang/otp-22.3/man
    #
    #  or:
    #      cd ~/docs/Erlang/otp-22.3/man
    #      make-local-whatis `pwd`
    #

    # ----------------------------------------------------------------------------
    # Script
    # ------
    #
    if [ "$1" == "" ]; then
        echo "Error: please specify a root directory that contains man1, etc.."
        exit 2
    elif [ -d "$1/man1" ]; then
        if [ -f "$1/whatis" ]; then
            echo "$1/whatis already exists!"
            exit 1
        else
            export MANPATH=$1
            /usr/libexec/makewhatis
            exit 0
        fi
    else
        echo "Error: $1 does not contain a man1 directory!"
        exit 3
    fi
    # -----------------------------------------------------------------------------

Using the make-local-whatis script
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Here's a session that demonstrates using the above script, starting with
a shell that uses the man directory where the whatis file is missing.

.. code:: shell

    Last login: Fri Jul 17 17:00:30 on ttys004
    > echo $MANPATH

    > cd docs/Erlang/otp-22.3/man
    > ls
    man1	man3	man4	man6	man7
    > MANPATH=`pwd`
    > echo $MANPATH
    /Users/roup/docs/Erlang/otp-22.3/man
    > export MANPATH
    > man -w erl
    /Users/roup/docs/Erlang/otp-22.3/man/man1/erl.1
    > whatis erlang
    erlang: nothing appropriate

Nothing is found for erlang.  With a whatis file you should see a rather long
list of topics for Erlang.

So, next, I execute the script while inside the man directory:

.. code:: shell

    > make-local-whatis `pwd`
    > ls
    man1	man3	man4	man6	man7	whatis
    > man -w erl
    /Users/roup/docs/Erlang/otp-22.3/man/man1/erl.1
    > whatis erlang
    auth(3)                  - Erlang network authentication server
    code(3)                  - Erlang code server
    compile(3)               - Erlang Compiler
    cover(3)                 - A Coverage Analysis Tool for Erlang
    crashdump(3), crashdump_viewer(3) - A WxWidgets based tool for browsing Erlang crashdumps
    ct_rpc(3)                - Common Test specific layer on Erlang/OTP rpc
    debugger(3)              - Erlang Debugger
    dialyzer(3)              - Dialyzer, a DIscrepancy AnaLYZer for ERlang programs
    driver_entry(3)          - The driver-entry structure used by Erlang drivers
    edoc(3)                  - EDoc - the Erlang program documentation generator
    edoc_run(3)              - Interface for calling EDoc from Erlang startup options
    ei(3)                    - Routines for handling the Erlang binary term format
    ei_connect(3)            - Communicate with distributed Erlang
    epmd(1)                  - Erlang Port Mapper Daemon
    epp(3)                   - An Erlang code preprocessor
    epp_dodger(3)            - epp_dodger - bypasses the Erlang preprocessor
    eprof(3)                 - A Time Profiling Tool for Erlang
    erl(1)                   - The Erlang emulator
    erl_anno(3)              - Abstract datatype for the annotations of the Erlang Compiler
    > whatis erlang | wc
          71     564    4819
    >

The Erlang topics are now detected by whatis.


Using man for Erlang - exclusively
==================================

When learning Erlang, it might be useful to create an
environment where the only ``man`` topics available are the ones related to
Erlang.  It's easy: set ``MANPATH`` to the directory holding the Erlang man
pages files, exclusively.

Using man for Erlang inside Emacs
=================================

If you are also using Emacs, Emacs man auto-completion fails to work if the
MANPATH environment variable is set to *only* list the Erlang man pages when
the whatis file is missing.

This is another reason to create the whatis file for the Erlang man directory.




.. _whatis utility: https://en.wikipedia.org/wiki/Apropos_(Unix)#Related_utilities
.. _makewhatis command line utility: https://man.openbsd.org/makewhatis
.. _Erlang/OTP download: https://www.erlang.org/downloads

.. ---------------------------------------------------------------------------
