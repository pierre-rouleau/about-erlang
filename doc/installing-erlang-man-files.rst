==============================================
Install Erlang OTP Documentation and Man Files
==============================================

:Home page: https://github.com/pierre-rouleau/about-erlang
:Time-stamp: <2021-05-15 17:54:09, updated by Pierre Rouleau>
:Copyright:  Copyright © 2020-2021, Pierre Rouleau
:License: `MIT <../LICENSE>`_

.. contents::  **Table of Contents**
.. sectnum::

.. ---------------------------------------------------------------------------


Manual installation of Erlang OTP Documentation and Man Files
-------------------------------------------------------------

I normally have a directory where I store the extra documentation files I
download from various sites.  Something like Python documentation, Erlang
documentation and Man files.  By having these files locally I can perform
search in the help files using my local tools and I can also integrate help
providing tools with my editor.  I avoid having to perform web requests
reducing my network traffic, my impact on overall energy consumption and
my dependence on being connected to the public Internet.

I download the OTP HTML documentation files and the Man page files from
the `Erlang/OTP download`_  page.  This page has a list of all Erlang/OTP
versions on the right hand side that leads to a version specific page where
you can download the documentation files as well as the source code archive and
the Windows binaries.

.. caution::
   ⚠️  Be aware that the list of Erlang versions are on the right hand
   side of the `Erlang/OTP download`_ page but will show **only if
   your browser window is wide enough!**.

I normally store these files in the ``~/docs`` directory and rename the
directory extracted from the zip tarballs downloaded from the `Erlang/OTP
download`_ page.  Here's the content of one such directory tree, listed with
the tree command line utility, with a view limited to a depth of 3:

.. code:: shell


    > tree -d docs/Erlang -L 3 -A
    docs/Erlang
    ├── otp-17.5
    │   ├── html
    │   │   ├── doc
    │   │   ├── erts-6.4
    │   │   └── lib
    │   └── man
    │       └── man
    ├── otp-18.3
    │   ├── html
    │   │   ├── doc
    │   │   ├── erts-7.3
    │   │   └── lib
    │   └── man
    │       └── man
    ├── otp-19.3
    │   ├── html
    │   │   ├── doc
    │   │   ├── erts-8.3
    │   │   └── lib
    │   └── man
    │       └── man
    ├── otp-20.3
    │   ├── html
    │   │   ├── doc
    │   │   ├── erts-9.3
    │   │   └── lib
    │   └── man
    │       └── man
    ├── otp-21.3
    │   ├── html
    │   │   ├── doc
    │   │   ├── erts-10.3
    │   │   └── lib
    │   └── man
    │       └── man
    ├── otp-22.2
    │   ├── html
    │   │   ├── doc
    │   │   ├── erts-10.6
    │   │   └── lib
    │   └── man
    │       └── man
    ├── otp-22.3
    │   ├── html
    │   │   ├── doc
    │   │   ├── erts-10.7
    │   │   └── lib
    │   └── man
    │       └── man
    └── otp-23.0
        ├── html
        │   ├── doc
        │   ├── erts-11.0
        │   └── lib
        └── man
            └── man

    56 directories
    >


.. _Erlang/OTP download: https://www.erlang.org/downloads


.. ---------------------------------------------------------------------------
