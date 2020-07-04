=====================================================
About the Erlang Programming Language and Environment
=====================================================

:Home page: https://github.com/pierre-rouleau/about-erlang
:Time-stamp: <2020-07-04 17:33:06, updated by Pierre Rouleau>
:Copyright: Copyright © 2020 by Pierre Rouleau
:License: `MIT <LICENSE>`_


This document is a top level view of Erlang and its environment; it provides
overviews and links to important resources.
It is a work in progress and will evolve over time.
Any suggestion and contribution are welcome!


.. contents::  **Table Of Contents**
.. sectnum::

Learning Erlang
===============


======================================================= ===============================================================
Topic                                                   Comment
======================================================= ===============================================================
**Authority**
`Erlang Project Homepage`_                              Erlang/OTP project home page.
                                                        They control all official releases, provide
                                                        the official implementation, documentation,
                                                        tools and reference to important books and
                                                        documents.

`Erlang On-Line Documentation, Books & Papers`_         Official documentation about Erlang and OTP with links to
                                                        books and `Joe Armstrong`_ paper.  This includes:

                                                        - `Erlang/OTP Documentation`_ (latest official version)
                                                        - `Erlang/OTP Documentation with Search`_ (works in Chrome,
                                                          Firefox 74.0.1 but not in Safari 13.1).
                                                        - `Erlang/OTP FAQ`_
                                                        - erldocs.com_, an alternative to the official Erlang
                                                          documentation.
                                                        - `Erlang Reference Manual - User's Guide`_
                                                        - `Efficiency Guide - User's Guide`_
                                                        - `Systems Principles - User's Guide`_
                                                        - `OTP Design Principles - User's Guide`_
                                                        - `OTP Versions Tree`_

`Erlang Community`_                                     Erlang.org page listing, among other things:

                                                        - Erlang Development repositories  (see below)
                                                        - Erlang IDE and editor support
                                                        - Free online courses
                                                        - Erlang Tutorials
                                                        - Mailing Lists
                                                        - Chat
                                                        - StackOverflow Q&A
                                                        - Erlang Resources

**Erlang GitHub Repositories**
`Erlang @ Github`_                                      Holds the official Erlang repositories:

                                                        - `Erlang/OTP @ Github`_
                                                        - `Erlang/Erlang-org @ Github`_ (the Erlang website)
                                                        - `Erlang/rebar3 @ Github`_
                                                        - `Erlang/docker-erlang-otp @ Github`_ (the Official Erlang OTP
                                                          image on Docker Hub)
                                                        - `Erlang/cd @ Github`_ (continuous delivery of Erlang/OTP artifacts)
                                                        - `Erlang/EEP @ Github`_  (Erlang Enhancement Proposals)
                                                        - and several others...

**Erlang Software License**                             As explained in the `Wikipedia Erlang Public License`_ page,
                                                        Ericsson has changed the license under which Erlang is
                                                        published as of Erlang/OTP version 18.0.
Erlang/OTP 18.0 and later: `Apache License 2.0`_
Erlang/OTP prior to 18.0: `Erlang Public License`_



**Erlang Sites: References**
`Erlang (programming language) @ Wikipedia`_            Outsider's view of the Erlang programming language with some
                                                        history, language overview  and several links to interesting
                                                        articles and sites.
`Category:Erlang (programming language) @ Wikipedia`_   Links to Wikipedia pages related to Erlang and its libraries.



**Erlang Sites: Books**
`Erlang Books @ Erlang Central`_

**Erlang Devoted Sites**
`Erlang Central`_ - Erlang Community                    A community of Erlang developers with links to documentation,
                                                        books and several packages and libraries.

`Erlang Solutions`_                                     An organization devoted to Erlang based software solutions,
                                                        which provides design services but also provides open source
                                                        and pre-package Erlang installations.

`Spawned Shelter`_                                      A collection of articles, videos and books for learning Erlang,
                                                        and other BEAM languages like Elixir, LFE and EFene.
**Erlang Tools**
kerl_                                                   Easy building and installing of Erlang/OTP
asdf-vm_                                                Package manager - can install Erlang, Elixir and other
                                                        systems.

**Erlang Libraries**
`Erlang Libraries @ Erlang.org`_                        Describes what is an Erlang OTP library.

`Awesome Erlang`_                                       A curated list of amazingly awesome Erlang libraries.


======================================================= ===============================================================



.. _Erlang Project Homepage:                      https://www.erlang.org
.. _Erlang On-Line Documentation, Books & Papers: https://www.erlang.org/docs
.. _Joe Armstrong:                                https://en.wikipedia.org/wiki/Joe_Armstrong_(programmer)
.. _Erlang/OTP Documentation:                     https://erlang.org/doc/
.. _Erlang/OTP Documentation with Search:         https://erlang.org/doc/search/
.. _erldocs.com:                                  https://erldocs.com/
.. _Erlang Reference Manual - User's Guide:       https://erlang.org/doc/reference_manual/users_guide.html
.. _Efficiency Guide - User's Guide:              https://erlang.org/doc/efficiency_guide/users_guide.html
.. _Systems Principles - User's Guide:            https://erlang.org/doc/system_principles/system_principles.html
.. _OTP Design Principles - User's Guide:         https://erlang.org/doc/design_principles/users_guide.html
.. _OTP Versions Tree:                            https://erlang.org/download/otp_versions_tree.html
.. _Erlang/OTP FAQ:                               http://erlang.org/faq/faq.html
.. _Erlang Community:                             https://www.erlang.org/community
.. _Erlang Books @ Erlang Central:                https://erlangcentral.org/books/
.. _Erlang (programming language) @ Wikipedia:    https://en.wikipedia.org/wiki/Erlang_(programming_language)
.. _Category\:Erlang (programming language) @ Wikipedia: https://en.wikipedia.org/wiki/Category:Erlang_(programming_language)
.. _Apache License 2.0:                           https://en.wikipedia.org/wiki/Apache_License
.. _Erlang Public License:                        https://www.erlang.org/EPLICENSE
.. _Wikipedia Erlang Public License:              https://en.wikipedia.org/wiki/Erlang_Public_License
.. _Erlang Central:                               https://erlangcentral.org/
.. _Erlang Solutions:                             https://www.erlang-solutions.com
.. _Erlang @ Github:                              https://github.com/erlang
.. _Erlang/OTP @ Github:                          https://github.com/erlang/otp
.. _Erlang/Erlang-org @ Github:                   https://github.com/erlang/erlang-org
.. _Erlang/rebar3 @ Github:                       https://github.com/erlang/rebar3
.. _Erlang/docker-erlang-otp @ Github:            https://github.com/erlang/docker-erlang-otp
.. _Erlang/cd @ Github:                           https://github.com/erlang/cd
.. _Erlang/EEP @ Github:                          https://github.com/erlang/eep
.. _kerl:                                         https://github.com/kerl/kerl
.. _asdf-vm:                                      https://asdf-vm.com/#/
.. _Erlang Libraries @ Erlang.org:                http://erlang.org/faq/libraries.html
.. _Awesome Erlang:                               https://github.com/drobakowski/awesome-erlang
.. _Spawned Shelter:                              https://spawnedshelter.com

..
   -----------------------------------------------------------------------------


Installing Erlang
=================

Erlang can be installed from source or from pre-built packages.

Instruction on how to install Erlang depends on the Operating System and are
available on the `Erlang OTP Download page`_.

The following section describes the various ways to install Erlang on macOS.

Installing Erlang on macOS
--------------------------

To install Erlang on your macOS system you can use one of the following ways:

#. `Using Homebrew`_, the simplest to get going, but also the least flexible way.
   A good first step for experimentation.
#. `Using Erlang Installer from Erlang Solutions`_.  With Erlang Solutions'
   ``ErlangInstaller`` macOS native application you can quickly install
   pre-built versions of Erlang for macOS and select which one you want to
   use.  I provide extra information on how to extends this.
#. `Using Kerl`_ to build from source code using clones of the official Erlang
   git repositories.
#. `Using asdf-vm`_ to build from source.  asdf-vm extends Kerl and provide
   the ability to build lots of other tools, Elixir for instance.
   At the moment (and from what I currently know) this seems to be a very good
   choice because you can install Erlang but also Elixir and several other
   tools with it.


Also, see the section titled
`Manual installation of Erlang OTP Documentation and Man Files`_
to get a local copy of Erlang HTML documentation and Erlang Man pages.



Some extra information specific to macOS is available of my `macOS Development Environment`_ document.

.. _Installing Erlang on macOS: https://github.com/pierre-rouleau/about-macOS/blob/master/doc/macos-env.rst#environment-for-erlang
.. _Erlang OTP Download page:   https://www.erlang.org/downloads
.. _macOS Development Environment: https://github.com/pierre-rouleau/about-macOS/blob/master/doc/macos-env.rst

Using Homebrew
~~~~~~~~~~~~~~


Homebrew_ is a popular package manager for macOS (and now also for Linux).  It
is very easy to install Erlang with Homebrew.  However, Homebrew installs a
version that it will eventually want to upgrade.  It is fine when just
experimenting with Erlang but this will not help you if you want to create a
system that will be running for a long time.

- First, install the Homebrew command line utility (``brew``)using the
  instructions right on the `Homebrew home page`_.
- You can then use the various commands:

  - ``brew search`` to search for a package.  For Erlang: ``brew search
    erlang`` will do.
  - ``brew info`` to get more info about a package. Something like ``brew info
    erlang``.  This will describe the version and its dependencies.
  - ``brew install`` to install a given package.  To install Erlang with
    Homebrew, the command is: ``brew install erlang``.


For example:

.. code:: shell


    > brew search erlang
    ==> Formulae
    erlang ✔                   erlang@20                  erlang@21                  erlang@22
    > brew info erlang
    erlang: stable 23.0.2 (bottled), HEAD
    Programming language for highly scalable real-time systems
    https://www.erlang.org/
    /usr/local/Cellar/erlang/22.3.4 (5,790 files, 282MB) *
      Poured from bottle on 2020-05-12 at 14:53:10
    From: https://github.com/Homebrew/homebrew-core/blob/HEAD/Formula/erlang.rb
    ==> Dependencies
    Build: autoconf ✔, automake ✔, libtool ✘
    Required: openssl@1.1 ✔, wxmac ✘
    ==> Options
    --HEAD
            Install HEAD version
    ==> Caveats
    Man pages can be found in:
      /usr/local/opt/erlang/lib/erlang/man

    Access them with `erl -man`, or add this directory to MANPATH.
    >

You'll probably want to put the directory where Homebrew places all binaries
in your path.  This way you'll be able to invoke these tools without a
path. The Erlang binary is placed in the same directory.  This means that the
Homebrew-installed version of Erlang will be available to the shell
directly. But not the Erlang Man pages.

On my systems I like to be able to have quick commands to setup shells.
I write a shells script that is meant to be sourced and then I write a shell
alias to source it.  I can then have various commands that setup the shell to
what I want and I can save all of this logic in a VCS.

For a Bash shell, for a Homebrew-installed Erlang, all that needs to be done
is to setup the MANPATH shell variable.  I also setup a shell variable to
prevent multiple execution and add a title to the top of my terminal window.

Here's a copy of the script that I named ``envfor-erlang-22.3.4`` store it in
a directory that's on my system's PATH and made executable:

.. code:: bash


    #!/usr/bin/env bash
    # Abstract: Complete Homebrew system Erlang 22.3.4
    # Last Modified Time-stamp: <2020-07-02 23:32:18, updated by Pierre Rouleau>
    #
    # This file *must* be sourced.
    #
    # Run with:  use-erlang
    #
    if [ "$DIR_ERLANG_DEV" == "" ]; then
        export DIR_ERLANG_DEV="$HOME/dev/erlang"
        MANPATH=/usr/local/Cellar/erlang/22.3.4/lib/erlang/man:`manpath`
        export MANPATH
        echo "+ Erlang 22.3.4 environment set."
        echo "+ Using Cellar/Erlang/22.3.4 Man pages."
        settitle "Erlang 22.3.4 HB"
    else
        echo "! Erlang environment was already set for this shell: nothing done this time."
    fi


The ``settitle`` is another quick shell script that sets the terminal title:

.. code:: shell

    #!/bin/sh
    # Abstract: Set the title of the current Terminal window.
    echo "\033]0;${1}\007\c"


The ``.bashrc`` file holds the alias:

.. code:: bash

   alias use-erlang='source envfor-erlang-22.3.4'


To use it I start a new Bash sell and type ``use-erlang``, as shown here:

.. code:: bash


    > use-erlang
    + Erlang 22.3.4 environment set.
    + Using Cellar/Erlang/22.3.4 Man pages.
    > echo $MANPATH
    /usr/local/Cellar/erlang/22.3.4/lib/erlang/man:/usr/local/share/man:/usr/share/man:/opt/X11/share/man:/Library/Developer/CommandLineTools/SDKs/MacOSX.sdk/usr/share/man:/Applications/Xcode.app/Contents/Developer/usr/share/man:/Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/share/man
    > man man
    > man -w erl
    /usr/local/Cellar/erlang/22.3.4/lib/erlang/man/man1/erl.1
    > man -w lists
    /usr/local/Cellar/erlang/22.3.4/lib/erlang/man/man3/lists.3
    > version-erl
    22.3.4
    >

The version-erl is another script I wrote to display the version of the Erlang
system available in the shell.  It runs Erlang code from the command line:

.. code:: bash


    #!/usr/bin/env bash
    # Abstract: print version of currently available Erlang on stdout
    # -----------------------------------------------------------------------------
    erl -eval '{ok, Version} = file:read_file(filename:join([code:root_dir(), "releases", erlang:system_info(otp_release), "OTP_VERSION"])), io:fwrite(Version), halt().' -noshell
    # -----------------------------------------------------------------------------


.. _Homebrew home page:
.. _Homebrew: https://brew.sh


Using Erlang Installer from Erlang Solutions
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

`Erlang Solutions`_ provide a tool called the Erlang Installer that allows the
installation of several versions of Erlang on a macOS computer.  You can get
that tool on `Erlang Solution Download page`_.  Select Erlang OTP and the Mac
OS X platform and you should get a link to ErlangInstaller.1.0.2.dmg_ or
something more recent.

With this tool you can install several pre-compiled versions of Erlang for
macOS.  It's a bit like Homebrew except that it's easier to download several
versions and have several versions on your system.

The latest version of this tool installs all versions under the
``~/.erlanginstaller`` root, along with a JSON file that contains a list of
available versions and a symlink to the version you identify as a default via
the erlangInstaller Preference dialog.

Here's what the top level view of the ``~/.erlanginstaller`` directory looks
like:

.. code:: shell


    > tree -L 1 -A .erlanginstaller
    .erlanginstaller
    ├── 19.3
    ├── 20.3.8
    ├── 21.3.8.7
    ├── 22.3.4.1
    ├── 23.0.2
    ├── available-releases.json
    └── default -> /Users/roup/.erlangInstaller/22.3.4.1

    6 directories, 1 file
    >

Here again, listing only the directories at a depth of 2, with the Erlang
versions I had installed at the time.

.. code:: shell

    >
    > tree -d -L 2 -A .erlanginstaller
    .erlanginstaller
    ├── 19.3
    │   ├── bin
    │   ├── erts-8.3
    │   ├── lib
    │   ├── misc
    │   ├── releases
    │   └── usr
    ├── 20.3.8
    │   ├── bin
    │   ├── erts-9.3.3
    │   ├── lib
    │   ├── misc
    │   ├── releases
    │   └── usr
    ├── 21.3.8.7
    │   ├── bin
    │   ├── erts-10.3.5.5
    │   ├── lib
    │   ├── misc
    │   ├── releases
    │   └── usr
    ├── 22.3.4.1
    │   ├── bin
    │   ├── erts-10.7.2.1
    │   ├── lib
    │   ├── misc
    │   ├── releases
    │   └── usr
    ├── 23.0.2
    │   ├── bin
    │   ├── doc
    │   ├── erts-11.0.2
    │   ├── lib
    │   ├── misc
    │   ├── releases
    │   └── usr
    └── default -> /Users/roup/.erlangInstaller/22.3.4.1

    37 directories
    >

With this application you can install or removed versions of Erlang easily.

Their Erlang implementations work fine but the HTML documentation and the Man pages
are missing.  You must install these files separately.
See the section titled
`Manual installation of Erlang OTP Documentation and Man Files`_ which
describes how to do it.

I use the same strategy as for Homebrew here and I create shell scripts and
alias to activate the various Erlang versions instead of using the Erlang
Installer tool that can launch pre-configured shell with specific version of
Erlang.  The reason I do this is to add access to the Man pages and to setup
other things if I need to.  For example, I'm thinking of setting up my Emacs
environment to be able to access the local HTML documentation of a the
module:function:arity at the cursor location or on request.  For that I need
to identify the location of the root where the files are stored and I do this
with an environment variable that I could set in the script.

For Erlang versions installed with the Erlang Installer from Erlang Solutions
I use the ``-ei`` suffix to the script and alias names.  For example, here's
the alias and the script for Erlang 23.0.2 installed with the tool inside
``~/.erlanginstaller/23.0.2``:

The alias, stored inside ``.bashrc``:

.. code:: bash

    alias use-erlang-23-ei='source envfor-erlang-23-ei'

And the bash script file that is source by it, stored in a directory that is
on my system's path:

.. code:: bash

    #!/usr/bin/env bash
    # Abstract: Complete Erlang Solutions' Erlang Installer 23.0.2
    # Last Modified Time-stamp: <2020-07-02 19:18:12, updated by Pierre Rouleau>
    # -----------------------------------------------------------------------------
    # This file *must* be sourced.
    #
    # Run with: use-erlang-23-ei

    # -----------------------------------------------------------------------------
    if [ "$DIR_ERLANG_DEV" == "" ]; then
        export DIR_ERLANG_DEV="$HOME/dev/erlang"
        PATH=$HOME/.erlangInstaller/23.0.2/lib/erl_interface-4.0/bin:$HOME/.erlangInstaller/23.0.2/bin:${PATH}
        export PATH
        MANPATH=$HOME/docs/Erlang/otp-23.0/man/man:`manpath`
        export MANPATH
        echo "+ Erlang 23.0.2 (from Erlang Solutions Erlang Installer) environment set."
        echo "+ Using OTP-23.0 Man pages."
        settitle "Erlang 23.0.2 EI"
    else
        echo "! Erlang environment was already set for this shell: nothing done this time."
    fi

    # -----------------------------------------------------------------------------

To use this, I start a new shell and I issue the ``use-erlang-23-ei`` command:

.. code:: shell

    > use-erlang-23-ei
    + Erlang 23.0.2 (from Erlang Solutions Erlang Installer) environment set.
    + Using OTP-23.0 Man pages.
    > version-erl
    23.0.2
    > which erl
    /Users/roup/.erlangInstaller/23.0.2/bin/erl
    > man -w erl
    /Users/roup/docs/Erlang/otp-23.0/man/man/man1/erl.1
    > man -w lists
    /Users/roup/docs/Erlang/otp-23.0/man/man/man3/lists.3
    > erl
    Erlang/OTP 23 [erts-11.0.2] [source] [64-bit] [smp:8:8] [ds:8:8:10] [async-threads:1]

    Eshell V11.0.2  (abort with ^G)
    1> q().
    ok
    2>
    >
    >

.. _Erlang Solutions: https://www.erlang-solutions.com
.. _Erlang Solution Download page: https://www.erlang-solutions.com/resources/download.html
.. _ErlangInstaller.1.0.2.dmg: https://packages.erlang-solutions.com/os-x-installer/ErlangInstaller1.0.2.dmg
.. _Erlang/OTP download: https://www.erlang.org/downloads


Manual installation of Erlang OTP Documentation and Man Files
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

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

.. caution:: Be aware that the list of Erlang versions are on the right hand
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


Using kerl
~~~~~~~~~~

...coming soon...

Using asdf-vm
~~~~~~~~~~~~~

...coming soon...


..
   -----------------------------------------------------------------------------
