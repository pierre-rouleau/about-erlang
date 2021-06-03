==============================================
Install Erlang OTP Documentation and Man Files
==============================================

:Home page: https://github.com/pierre-rouleau/about-erlang
:Navigation: Prev_, Top_, Next_
:Time-stamp: <2021-06-03 15:40:03, updated by Pierre Rouleau>
:Copyright:  Copyright © 2020, 2021, Pierre Rouleau
:License: `MIT <../LICENSE>`_

.. _Prev:  installing-erlang-asdf.rst
.. _Top:   installing-erlang.rst
.. _Next:  whatis-files.rst

.. contents::  **Table of Contents**
.. sectnum::

.. ---------------------------------------------------------------------------


Manual installation of Erlang OTP Documentation and Man Files
-------------------------------------------------------------

It's useful to store man files and official documentation locally.
Erlang OTP man files and HTML documentation is available.

Download them from the `Erlang/OTP download`_ page.  It has a list of all
Erlang/OTP versions on the right hand side with links that lead to a version
specific page where you can download the documentation files as well as the
source code archive and the Windows binaries.

.. caution::
   ⚠️  Be aware that the list of Erlang versions are on the right hand
   side of the `Erlang/OTP download`_ page but will show **only if
   your browser window is wide enough!**

I store these files inside the ``~/docs/Erlang/otp-XX.Y`` directory,
where ``XX.Y`` is the OTP version number. I extract the content of both the
html and the man zip tarball files into the corresponding ``otp-XX.Y``
directory.  The html and the man zip tarball files contain a couple of files
at the root that are the same so the files first copied are written over by
the second set but the files are identical anyway.  By doing this I end up
with a directory structure that conforms to the normal OTP directory tree.

Here's the directory layout with a view limited to a depth of 2:

.. code:: shell

      > tree -d docs/Erlang -L 2 -A
      docs/Erlang
      ├── otp-17.5
      │   ├── doc
      │   ├── erts-6.4
      │   ├── lib
      │   └── man
      ├── otp-18.3
      │   ├── doc
      │   ├── erts-7.3
      │   ├── lib
      │   ├── man
      │   └── mn
      ├── otp-19.3
      │   ├── doc
      │   ├── erts-8.3
      │   ├── lib
      │   └── man
      ├── otp-20.3
      │   ├── doc
      │   ├── erts-9.3
      │   ├── lib
      │   └── man
      ├── otp-21.3
      │   ├── doc
      │   ├── erts-10.3
      │   ├── lib
      │   └── man
      ├── otp-22.2
      │   ├── doc
      │   ├── erts-10.6
      │   ├── lib
      │   └── man
      ├── otp-22.3
      │   ├── doc
      │   ├── erts-10.7
      │   ├── lib
      │   └── man
      ├── otp-23.0
      │   ├── doc
      │   ├── erts-11.0
      │   ├── lib
      │   └── man
      └── otp-23.3
          ├── doc
          ├── erts-11.2
          ├── lib
          └── man

      46 directories
      >


Each of the ``otp_XX.Y`` directory have a layout similar to what is shown
here:

.. code:: shell

    > tree -d docs/Erlang/otp-20.3 -L 2 -A
    docs/Erlang/otp-20.3
    ├── doc
    │   ├── design_principles
    │   ├── docbuild
    │   ├── efficiency_guide
    │   ├── embedded
    │   ├── getting_started
    │   ├── installation_guide
    │   ├── js
    │   ├── oam
    │   ├── pdf
    │   ├── programming_examples
    │   ├── reference_manual
    │   ├── system_architecture_intro
    │   ├── system_principles
    │   └── tutorial
    ├── erts-9.3
    │   └── doc
    ├── lib
    │   ├── asn1-5.0.5
    │   ├── common_test-1.15.4
    │   ├── compiler-7.1.5
    │   ├── cosEvent-2.2.2
    │   ├── cosEventDomain-1.2.2
    │   ├── cosFileTransfer-1.2.2
    │   ├── cosNotification-1.2.3
    │   ├── cosProperty-1.2.3
    │   ├── cosTime-1.2.3
    │   ├── cosTransactions-1.3.3
    │   ├── crypto-4.2.1
    │   ├── debugger-4.2.4
    │   ├── dialyzer-3.2.4
    │   ├── diameter-2.1.4
    │   ├── edoc-0.9.2
    │   ├── eldap-1.2.3
    │   ├── erl_docgen-0.7.2
    │   ├── erl_interface-3.10.1
    │   ├── et-1.6.1
    │   ├── eunit-2.3.5
    │   ├── hipe-3.17.1
    │   ├── ic-4.4.3
    │   ├── inets-6.5
    │   ├── jinterface-1.8.1
    │   ├── kernel-5.4.3
    │   ├── megaco-3.18.3
    │   ├── mnesia-4.15.3
    │   ├── observer-2.7
    │   ├── odbc-2.12.1
    │   ├── orber-3.8.4
    │   ├── os_mon-2.4.4
    │   ├── otp_mibs-1.1.2
    │   ├── parsetools-2.1.6
    │   ├── public_key-1.5.2
    │   ├── reltool-0.7.5
    │   ├── runtime_tools-1.12.5
    │   ├── sasl-3.1.1
    │   ├── snmp-5.2.10
    │   ├── ssh-4.6.6
    │   ├── ssl-8.2.4
    │   ├── stdlib-3.4.4
    │   ├── syntax_tools-2.1.4
    │   ├── tools-2.11.2
    │   ├── wx-1.8.3
    │   └── xmerl-1.3.16
    └── man
        ├── man1
        ├── man3
        ├── man4
        ├── man6
        └── man7

    69 directories
    >

The ``docs/Erlang/otp_XX.Y/man`` directories contain 5 sub_directories:

- man1 : Commands
- man3 : Modules
- man4 : Files
- man6 : Applications
- man7 : SNMP MIBs



.. _Erlang/OTP download: https://www.erlang.org/downloads


.. ---------------------------------------------------------------------------
