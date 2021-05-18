==========================================
Creating whatis files for Erlang man pages
==========================================

:Home page: https://github.com/pierre-rouleau/about-erlang
:Time-stamp: <2021-05-18 17:21:23, updated by Pierre Rouleau>
:Copyright:  Copyright © 2020, 2021, Pierre Rouleau
:License: `MIT <../LICENSE>`_

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

    > whatis man
    groff_man(7)             - groff `man' macros to support generation of man pages
    groffer(1)               - display groff files and man~pages on X and tty
    man(1)                   - format and display the on-line manual pages
    man.conf(5)              - configuration data for man
    zshall(1)                - the Z shell meta-man page
    > whatis whatis
    apropos(1)               - search the whatis database for strings
    awacsd(8)                - Apple Wide Area Connectivity Service daemon " Name Description for whatis database
    dns-sd(1)                - Multicast DNS (mDNS) & DNS Service Discovery (DNS-SD) Test Tool " For whatis
    dnsextd(8)               - BIND Extension Daemon " Name Description for whatis database
    mDNSResponder(8)         - Multicast and Unicast DNS daemon " Name Description for whatis database
    mDNSResponderHelper(8)   - mDNS privilege separation helper " Name Description for whatis database
    makewhatis(8)            - create whatis database
    whatis(1)                - search the whatis database for complete words
    >


The ``whatis`` utility uses a whatis file.  On most Unix-like systems, the man
page directory contains the whatis file. Unfortunately the man directories
available in the `Erlang/OTP download`_ page do not have this file.

Using man for Erlang - exclusively
==================================

When learning Erlang, it might be useful to create an
environment where the only ``man`` topics available are the ones related to
Erlang.  It's easy: set ``MANPATH`` to the directory holding the Erlang man
pages files.

Using man for Erlang exclusively inside Emacs
---------------------------------------------

If you are also using Emacs, then Emacs man auto-completion will
only include the Erlang-related topics.

Unfortunately, the Emacs man command auto-completion fails to work if the
MANPATH environment variable is set to *only* list the Erlang man pages when
the whatis file is missing.

So you'll need to create the missing whatis file.

For that, you'll use the `makewhatis command line utility`_. On macOS, this
executable is stored in ``/usr/libexec/makewhatis``.

To only create the missing whatis file, you must first set ``MANPATH`` to the
directory holding the ``man1``, ``man3``, ``man7`` and other ``manX``
directories.
Once you have that set up, you can run ``/usr/libexec/makewhatis`` and it will
create the whatis file in that directory and will not touch anything else.

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
    # Copyright © 2021, Pierre Rouleau
    # License   : MIT
    # ----------------------------------------------------------------------------
    # Description
    # -----------
    #
    #
    # Usage: make-local-whatis directory
    #
    # Examples:
    #      make-local-whatis ~/docs/Erlang/otp-22.3/man/man
    #
    #  or:
    #      cd ~/docs/Erlang/otp-22.3/man/man
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

Here's a session that demonstrates using the above script:

.. code:: shell

    Last login: Fri Jul 17 17:00:30 on ttys004
    > echo $MANPATH

    > cd docs/Erlang/otp-22.3/man/man
    > ls
    man1	man3	man4	man6	man7
    > MANPATH=`pwd`
    > echo $MANPATH
    /Users/roup/docs/Erlang/otp-22.3/man/man
    > export MANPATH
    > man -w erl
    /Users/roup/docs/Erlang/otp-22.3/man/man/man1/erl.1
    > whatis erlang
    erlang: nothing appropriate
    > make-local-whatis `pwd`
    > ls
    man1	man3	man4	man6	man7	whatis
    > man -w erl
    /Users/roup/docs/Erlang/otp-22.3/man/man/man1/erl.1
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




.. _whatis utility: https://en.wikipedia.org/wiki/Apropos_(Unix)#Related_utilities
.. _makewhatis command line utility: https://man.openbsd.org/makewhatis
.. _Erlang/OTP download: https://www.erlang.org/downloads

.. ---------------------------------------------------------------------------
