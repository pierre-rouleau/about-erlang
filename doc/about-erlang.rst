=====================================================
About the Erlang Programming Language and Environment
=====================================================

:Home page: https://github.com/pierre-rouleau/about-erlang
:Time-stamp: <2020-08-20 19:04:12, updated by Pierre Rouleau>
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


============================ ============================================================================================
Topic                        Content
============================ ============================================================================================
**Authority**
`Erlang Project Homepage`_   Erlang/OTP project home page.
                             They control all official releases, provide
                             the official implementation, documentation,
                             tools and reference to important books and
                             documents.

                             - `Erlang On-Line Documentation, Books & Papers`_:

                             Official documentation about Erlang and OTP with links to
                             books and `Joe Armstrong`_ paper.  This includes:

                             - `Erlang/OTP Documentation`_ (latest official version)
                             - `Erlang/OTP Documentation with Search`_ (works in Chrome,
                               Firefox 74.0.1, Safari 13.2 but not in Safari 13.1).
                             - `Erlang/OTP FAQ`_
                             - erldocs.com_, an alternative to the official Erlang
                               documentation.
                             - `Erlang Reference Manual - User's Guide`_
                             - `Efficiency Guide - User's Guide`_
                             - `Systems Principles - User's Guide`_
                             - `OTP Design Principles - User's Guide`_
                             - `Erlang Man Page Index`_
                             - `OTP Versions Tree`_

                             The site also holds the following `Erlang Community`_ information:

                             - Erlang Development repositories (on Github, see next row  below)
                             - Erlang IDE and editor support
                             - Free online courses
                             - Erlang Tutorials
                             - Mailing Lists
                             - Chat
                             - StackOverflow Q&A
                             - Erlang Resources

`Erlang @ Github`_           Github holds the official Erlang repositories:

                             - `Erlang/OTP @ Github`_
                             - `Erlang/Erlang-org @ Github`_ (the Erlang website)
                             - `Erlang/rebar3 @ Github`_
                             - `Erlang/docker-erlang-otp @ Github`_ (the Official Erlang
                               OTP image on Docker Hub)

                               - `Erlang/cd @ Github`_ (continuous delivery of Erlang/OTP
                                 artifacts)

                             - `Erlang/EEP @ Github`_  (Erlang Enhancement Proposals)
                             - and several others...

**Erlang Software License**  As explained in the `Wikipedia Erlang Public License`_ page,
                             Ericsson changed the license under which Erlang is
                             published as of Erlang/OTP version 18.0.

                             - Erlang/OTP 18.0 and later: `Apache License 2.0`_
                             - Erlang/OTP prior to 18.0: `Erlang Public License`_

**Code Guidelines**          - `Ericsson Erlang Programming Rules and Conventions`_

                               - Written by Klass Eriksson, Mike Williams and Joe Armstrong.
                                 Describes the programming rules and conventions of Erlang
                                 programming.

                             - `Inaka's Erlang Coding Standards & Guidelines`_

                               - Inaka's corporate Erlang Guideline.

                             - `EDoc User's Guide`_

                               - How to document Erlang code with EDoc annotations.

**Quick-Sheets**
                             - `Learn X in Y minutes, where X=erlang`_

                               - A quick overview of Erlang.

                             - `Erlang Concurrent Programming`_

                               - An Erlang.org quick presentation on Erlang's concurrent
                                 programming concepts.

**References**               **Erlang - Sequential**

                             - **Type Specifications**

                               - `Types and Function Specifications`_  (at `erlang.org`_).

                                 - `Types (or lack thereof)`_ (at `LYSEFGG`_).
                                 - `Type Specifications and Erlang`_ (at `LYSEFGG`_).

                               - `TypEr: A Type Annotator of Erlang Code`_   (at `erlang.org`_).

                                 - `TypEr: A Type Annotator of Erlang Code`_ (Lindahl, Sogonas paper, Uppsala
                                   University, Sweden).

                             - **Data Types**

                               ============================================ ============================================
                               From `erlang.org reference data types`_      From `LYSEFGG`_
                               ============================================ ============================================
                               - Terms_
                               - `Numbers,`_                                - Numbers_,
                               - `atoms,`_                                  - atoms_ and Variables_,
                               - boolean_,                                  - `boolean and comparison operators`_,
                               - pid_ (`Erlang process`_ identifier)
                               - `port identifier`_
                                 (`Erlang port`_ identifier)
                               - reference_
                               - "strings_" and `escape sequences`_
                               - `bit strings and binaries,`_               - bit strings
                               - {`tuples,`_}  and records_                 - {tuples_},
                               - [`lists,`_]                                - [lists_], `list comprehensions`_
                               - map_ and `map expressions`_
                               - `type conversions`_
                               - `Fun (functional object)`_
                               ============================================ ============================================


                             **Erlang Tools**

                             - **Erlang Shell**

                               - `The Shell <https://learnyousomeerlang.com/starting-out#the-shell>`_ ,
                                 `Shell Commands <https://learnyousomeerlang.com/starting-out#shell-commands>`_
                                 (at `LYSEFGG`_).
                               - Man pages: `Shell <https://erlang.org/doc/man/shell.html>`_.
                               - Related modules:
                                 `shell_default <https://erlang.org/doc/man/shell_default.html>`_,
                                 `shell_docs <https://erlang.org/doc/man/shell_docs.html>`_.

**Introduction**             - `Erlang (programming language) @ Wikipedia`_

                               - Outsider's view of the Erlang programming language with
                                 some history, language overview and several links to
                                 interesting articles and sites.

                               - `Category:Erlang (programming language) @ Wikipedia`_

                                 - Links to Wikipedia pages related to Erlang and its
                                   libraries.

**Paper Books**              Books on Erlang. A list is also available on the
                             `Erlang/OTP Documentation`_ page.

                             .. image:: res/books-01.png

                             - `Erlang and OTP in Action`_

                               - Written by Martin Logan, Eric Merrit and Richard Clarsson.
                                 Published in 2010.
                               - Very well written, concise and effective must read book
                                 to learn Erlang and OTP.
                               -  Example code in `GitHub Erlang and OTP in Action`_.

                             - `Property-Based Testing with PropEr, Erlang and Elixir`_

                               - An intermediate/advanced book on property testing in
                                 Erlang and Elixir, written by `Fred Hébert`_, published
                                 by The Pragmatic Bookshelf, 2019.

**Online Books**
                             - `Learn You Some Erlang for Great Good!`_
                               (`TOC <https://learnyousomeerlang.com/content>`_)

                               - A comprehensive introduction to Erlang written by
                                 `Fred Hébert`_.  Also in print. No starch press. 2013

                             - `Stuff Goes Bad: Erlang in Anger`_

                               - A "*collection of tips and tricks to help understand where
                                 failures come from*" and code to help debug Erlang systems.
                               - Written by `Fred Hébert`_.

                             - `Adopting Erlang`_

                               - A book on Erlang system, how to build, how to use
                                 in production. Collectively written by
                                 the `adoptingerlang project contributors`_ which includes
                                 Tristan Sloughter and `Fred Hébert`_.

                             - `The Erlang Runtime System`_

                               - Written by Erik Stenman, this book focuses on tuning Erlang
                                 installation and describes how Erlang works.

                             - PropEr Testing

**Online Courses**           List of online sites providing Erlang courses.

                             - `University of Kent`_ & FutureLearn  Erlang Courses

                               - The following courses are available:

                                 - `Functional Programming in Erlang`_
                                 - `Concurrent Programming in Erlang`_
                                 - `Erlang Master Classes @ University of Kent`_

**Organizations**
                             - `Erlang.org`_ , the official Erlang/OTP home.
                             - `Erlang Solutions`_

                               - An organization devoted to Erlang based software solutions,
                                 which provides design services but also provides open
                                 source and pre-package Erlang installations.

                             - Erlware_

                               - Erlware is an umbrella organization dedicated to bringing
                                 high quality, well tested, reusable libraries and tools to
                                 the Erlang community. They provide the `Erlware Commons`_
                                 Erlang library, the `Relx Erlang release assembler tool`_,
                                 the Joxa Lisp BEAM language, and training.
                                 See also: `The Erlware Blog`_

                             - `Spawned Shelter`_

                               - A collection of articles, videos and books for learning
                                 Erlang, and other BEAM languages like Elixir, LFE and
                                 EFene.

                             - `Erlang Central`_

                               - A community of Erlang developers with links to
                                 documentation,
                                 books and several packages and libraries.  See the related
                                 sites:

                                 - `Erlang Central @ GitHub`_
                                 - `Erlang Books @ Erlang Central`_


**Build/Install Tools**      List of software tools for building and installing Erlang.

                             - Homebrew_

                               - Installs pre-built version of Erlang.

                             - `Erlang Solutions`_ ErlangInstaller_

                               - Installs pre-built versions of Erlang with macOS GUI
                                 application ErlangInstaller_ froom `Erlang Solutions`_.

                             - kerl_

                               - Easy building and installing of Erlang/OTP from source.

                             - asdf-vm_

                               - Package manager - can install Erlang, Elixir and other
                                 tools and systems from source. For Erlang, uses kerl_.

**Development Tools**        Articles on Erlang development tools.

                             - `10 Essential Erlang Tools for Erlang Developers`_

                               - A Pluralsight guide written by Brujo Benavides describing
                                 several very useful tools.

**Libraries**                List of Erlang source code libraries.

                             - `Erlang Libraries @ Erlang.org`_

                               - Describes what is an Erlang OTP library.

                             - `Awesome Erlang`_

                               - A curated list of amazingly awesome Erlang libraries.

**Related Topics**
                             - `The Actor Model @ wikipedia`_

                               - Presentation of the Actor Model. See also:

                                 - `Actor Model of Computation: Scalable Robust
                                   Information Systems`_ from `Carl Hewitt`_
                                 - Youtube video: `Hewitt, Meijer and Szyperski: The Actor
                                   Model`_
                                 - `It's Actors All the Way Down`_

                                   - A collection of topics related to the Actor Model
                                     in relation with Humus, a pure Actor Model programming
                                     language.  Some
                                     articles compare Erlang to the pure Actor Model:

                                     - `Erlang-style Mailboxes`_
============================ ============================================================================================


.. _erlang.org:
.. _Erlang Project Homepage:                      https://www.erlang.org
.. _Erlang On-Line Documentation, Books & Papers: https://www.erlang.org/docs
.. _Joe Armstrong:                                https://en.wikipedia.org/wiki/Joe_Armstrong_(programmer)
.. _Erlang/OTP Documentation:                     https://erlang.org/doc/
.. _Erlang/OTP Documentation with Search:         https://erlang.org/doc/search/
.. _erldocs.com:                                  https://erldocs.com/
.. _erlang.org reference data types:              https://erlang.org/doc/reference_manual/data_types.html
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
.. _Erlang Central @ GitHub:                      https://github.com/ErlangCentral
.. _The Erlang Runtime System:                    https://blog.stenmans.org/theBeamBook/
.. _LYSEFGG:
.. _Learn You Some Erlang for Great Good!:        https://learnyousomeerlang.com
.. _Ericsson Erlang Programming Rules and Conventions: http://www.erlang.se/doc/programming_rules.shtml#REF17122
.. _The Actor Model @ wikipedia:                  http://www.erlang.se/doc/programming_rules.shtml#REF17122
.. _It's Actors All the Way Down:                 http://www.dalnefre.com/wp/
.. _Erlang-style Mailboxes:                       http://www.dalnefre.com/wp/2011/10/erlang-style-mailboxes/
.. _Actor Model of Computation\: Scalable Robust Information Systems: https://arxiv.org/abs/1008.1459
.. _Carl Hewitt:                                  https://en.wikipedia.org/wiki/Carl_Hewitt
.. _Hewitt, Meijer and Szyperski\: The Actor Model: https://www.youtube.com/watch?v=7erJ1DV_Tlo&feature=youtu.be
.. _Erlang Master Classes @ University of Kent:   https://www.cs.kent.ac.uk/ErlangMasterClasses/#
.. _Concurrent Programming in Erlang:             https://www.futurelearn.com/courses/concurrent-programming-erlang/
.. _Functional Programming in Erlang:             https://www.futurelearn.com/courses/functional-programming-erlang/
.. _University of Kent:                           https://www.kent.ac.uk/
.. _Adopting Erlang:                              https://adoptingerlang.org
.. _Stuff Goes Bad\: Erlang in Anger:             https://www.erlang-in-anger.com
.. _adoptingerlang project contributors:          https://github.com/adoptingerlang/adoptingerlang/graphs/contributors
.. _Fred Hébert:                                  https://ferd.ca
.. _Learn X in Y minutes, where X=erlang:         https://learnxinyminutes.com/docs/erlang/
.. _Erlang Concurrent Programming:                https://www.erlang.org/course/concurrent-programming
.. _Erlang and OTP in Action:                     https://www.manning.com/books/erlang-and-otp-in-action
.. _GitHub Erlang and OTP in Action:              https://github.com/erlware/Erlang-and-OTP-in-Action-Source
.. _Erlware:                                      https://www.erlware.org
.. _Erlware Commons:                              https://github.com/erlware/erlware_commons
.. _Relx Erlang release assembler tool:           https://github.com/erlware/relx
.. _The Erlware Blog:                             http://blog.erlware.org/
.. _Property-Based Testing with PropEr, Erlang and Elixir: http://propertesting.com/
.. _Inaka's Erlang Coding Standards & Guidelines: https://github.com/inaka/erlang_guidelines
.. _10 Essential Erlang Tools for Erlang Developers: https://www.pluralsight.com/guides/10-essential-erlang-tools-for-erlang-developers
.. _EDoc User's Guide:                            http://erlang.org/doc/apps/edoc/chapter.html
.. _Types and Function Specifications:            https://erlang.org/doc/reference_manual/typespec.html
.. _TypEr\: A Type Annotator of Erlang Code:      http://user.it.uu.se/~tobiasl/publications/typer.pdf
.. _Types (or lack thereof):                      https://learnyousomeerlang.com/types-or-lack-thereof
.. _Type Specifications and Erlang:               https://learnyousomeerlang.com/dialyzer#plt
.. _Numbers:                                      https://learnyousomeerlang.com/starting-out-for-real#numbers
.. _atoms:                                        https://learnyousomeerlang.com/starting-out-for-real#atoms
.. _Variables:                                    https://learnyousomeerlang.com/starting-out-for-real#invariable-variables
.. _tuples:                                       https://learnyousomeerlang.com/starting-out-for-real#tuples
.. _boolean and comparison operators:             https://learnyousomeerlang.com/starting-out-for-real#bool-and-compare
.. _lists:                                        https://learnyousomeerlang.com/starting-out-for-real#lists
.. _list comprehensions:                          https://learnyousomeerlang.com/starting-out-for-real#list-comprehensions
.. _Erlang Man Page Index:                        https://erlang.org/doc/man_index.html
.. _Numbers,:                                     https://erlang.org/doc/reference_manual/data_types.html#number
.. _atoms,:                                       https://erlang.org/doc/reference_manual/data_types.html#atom
.. _bit strings and binaries,:                    https://erlang.org/doc/reference_manual/data_types.html#bit-strings-and-binaries
.. _boolean:                                      https://erlang.org/doc/reference_manual/data_types.html#boolean
.. _reference:                                    https://erlang.org/doc/reference_manual/data_types.html#reference
.. _pid:                                          https://erlang.org/doc/reference_manual/data_types.html#pid
.. _port identifier:                              https://erlang.org/doc/reference_manual/data_types.html#port-identifier
.. _Terms:                                        https://erlang.org/doc/reference_manual/data_types.html#terms
.. _tuples,:                                      https://erlang.org/doc/reference_manual/data_types.html#tuple
.. _lists,:                                       https://erlang.org/doc/reference_manual/data_types.html#list
.. _strings:                                      https://erlang.org/doc/reference_manual/data_types.html#string
.. _records:                                      https://erlang.org/doc/reference_manual/data_types.html#record
.. _escape sequences:                             https://erlang.org/doc/reference_manual/data_types.html#escape-sequences
.. _map:                                          https://erlang.org/doc/reference_manual/data_types.html#map
.. _map expressions:                              https://erlang.org/doc/reference_manual/expressions.html#map_expressions
.. _type conversions:                             https://erlang.org/doc/reference_manual/data_types.html#type-conversions
.. _Fun (functional object):                      https://erlang.org/doc/reference_manual/data_types.html#fun
.. _Erlang process:                               https://erlang.org/doc/reference_manual/processes.html
.. _Erlang port:                                  https://erlang.org/doc/reference_manual/ports.html

-----------------------------------------------------------------------------


Installing Erlang
=================

Erlang can be installed from source or from pre-built packages.

Instruction on how to install Erlang depends on the Operating System and are
available on the `Erlang OTP Download page`_.  Another good source of
information is available in the `setup section of the Adopting Erlang`_ web site.

The following section describes the various ways to install Erlang on macOS.


.. _setup section of the Adopting Erlang: https://adoptingerlang.org/docs/development/setup/

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
#. Building from source using the Erlang/OTP instructions found in
   the `Erlang/OTP Build and Install instructions`_. I have not yet gone
   through the entire process yet. Once I do I will provide more information.



.. _Erlang/OTP Build and Install instructions: https://github.com/erlang/otp/blob/master/HOWTO/INSTALL.md



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


To use it I start a new Bash shell and type ``use-erlang``, as shown here:

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

`Erlang Solutions`_ provide a macOS application called the Erlang Installer that allows the
installation of several versions of Erlang on a macOS computer.  You can get
that tool on `Erlang Solution Download page`_.  Select Erlang OTP and the Mac
OS X platform and you should get a link to ErlangInstaller.1.0.2.dmg_ or
something more recent.

With this GUI tool you can install or remove several pre-compiled versions of Erlang for
macOS.

.. image:: res/erlanginstaller.png


With the Preferences dialog of ErlangInstaller, you can select one version you
can use by default, specify the directory where the application stores its
files and identify the application used for launching shells.

.. image:: res/erlanginstaller-preferences.png

When the ErlangInstaller application runs, it show up in macOS menu bar you
can quickly open its Preference dialog to manage Erlang versions and also use
the menu to launch a shell specialized with the default Erlang version or any
of the Erlang versions you have installed.

.. image:: res/ei-menu.png

The latest version of this tool installs all versions under the
``~/.erlanginstaller`` root (but that can be changed via the Preference
dialog),
along with a JSON file that contains a list of
available versions and a symlink to the version you identify as a default via
the ErlangInstaller application Preference dialog.

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
.. _ErlangInstaller:
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


Using Kerl
~~~~~~~~~~

If you want to build Erlang from source easily, you can use Kerl_.  This tool
is a shell script that controls the build.  It attempts to be shell agnostic
and requires only ``curl`` and ``git`` as dependencies.

On macOS, to use Kerl, you also need XCode_ and a recent version of OpenSSL_.
The OpenSSL_ version that is available on macOS is outdated.
The easiest way to install a more recent version of OpenSSL_ on macOS is to use
`Homebrew`_ with ``brew install openssl``.

When building Erlang with Kerl (and asdf-vm) you can use the default macOS
C/C++ toolchain part of Xcode, which is Apple's own version of the Clang
compiler suite, or you can also install GCC or the LLVM Clang compiler
suites. I have been able to build with the 3 suites.  However, I must have a
setup problem with my GCC 9 installation because builds with GCC 9 fail to
produce an Erlang debugger that works.  I've had no problem with the Apple
native compiler nor with LLVM 10.

Depending on what you have on your system, you may have to install other tools
to perform the build with Kerl.  You might need to install GNU Make for
instance.  Use Homebrew to install those tools.

Setting the environment for Kerl
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

To use Kerl you need to set several shell environment variables.  The
instructions provided by the Kerl home page describe what to add to your shell
setup.  Instead of doing that I the same strategy and create a shell script to
install the environment along with a shell alias to invoke it.

I use the following ``envfor-kerl`` bash script:

.. code:: bash

    #!/usr/bin/env bash
    # Abstract: setup shell to build Erlang with Kerl.
    # Last Modified Time-stamp: <2020-07-05 12:29:17, updated by Pierre Rouleau>
    # -----------------------------------------------------------------------------
    #
    # This file *must* be sourced.
    #
    # Run with: use-kerl
    #
    # -----------------------------------------------------------------------------
    # References:
    # - Adopting Erlang - Setup : https://adoptingerlang.org/docs/development/setup/
    # - Kerl:  https://github.com/kerl/kerl
    # - Elixir Forum: Installing Erlang with Docs: https://elixirforum.com/t/help-installing-erlang-with-docs/22457
    #
    # Instructions:
    #
    #  - to build:    kerl build {release} {build name}
    #    - example:   kerl build 22.0 22.0
    #  - to install:  kerl install {build name} {target path}
    #    - example:   kerl install 22.0 ~/bin/erls/22.0/
    #  - to activate: . {target path}/activate
    #    - example:   . ~/bin/erls/22.0/activate
    # -----------------------------------------------------------------------------
    if [ "$ROUP_FOR_BUILDING_ERLANG" == "" ]; then
        export ROUP_FOR_BUILDING_ERLANG=$PATH
        SSL_PATH=/usr/local/Cellar/openssl@1.1/1.1.1g/
        export KERL_BUILD_BACKEND="git"
        export KERL_CONFIGURE_OPTIONS="--without-javac --with-dynamic-trace=dtrace --with-ssl=${SSL_PATH}"
        export KERL_BUILD_DOCS=yes
        export KERL_INSTALL_MANPAGES=yes
        export KERL_INSTALL_HTMLDOCS=yes
        use-gmake
    else
        printf "Shell is already setup for building Erlang!\n"
        return 1
    fi
    # -----------------------------------------------------------------------------


This uses another source script: ``envfor-gmake``, invoked via the
``use-gmake`` alias:

.. code:: shell

    #!/bin/sh
    # Abstract: Install latest GNU Make as the main make in the current shell.
    # Last Modified Time-stamp: <2020-07-04 18:24:43, updated by Pierre Rouleau>
    # -----------------------------------------------------------------------------
    # This GNU Make is the latest, and replaces the old GNU Make
    # distributed on macOS (GNU Make 3.81 from 2006)
    # -----------------------------------------------------------------------------
    if [ "$ROUP_USING_GMAKE" == "" ]; then
        export ROUP_USING_GMAKE=$PATH
        export PATH="/usr/local/opt/make/libexec/gnubin:$PATH"
        printf "Now using the Homebrew-installed GNU Make in this shell\n"
        gmake --version
        printf "\n"
    else
        printf "GNU GMAKE is already installed in this shell!\n"
        printf "The original path is inside ROUP_USING_GMAKE\n"
        return 1
    fi
    # -----------------------------------------------------------------------------

The 2 aliases I have in my ``.bashrc`` file for these are the following:

.. code:: bash

    alias use-kerl='source envfor-kerl'
    alias use-gmake='source envfor-gmake'

Kerl Commands
^^^^^^^^^^^^^

The Kerl_ home page describes Kerl commands.  When building Erlang with Kerl,
you use Kerl to get a list of all available Git repositories with Erlang
source code,  clone a Erlang source git repository for the Erlang version you
want to build, build the Erlang version and optionally provide a different
name to recognize it when you have special build setups, and then install the
built Erlang version inside a directory tree, ready to be used.

The important Kerl commands are the following:

- kerl update releases
- kerl build {release} {build name}
- kerl install {build name} {target path}

  - kerl install 21.3 ~/bin/erls/21.3/

And then to activate a specific version of Erlang you source the corresponding
activate script located in the directory where you installed Kerl builds (in
this example this directory is ``~/bin/erls``):

.. code:: bash

   . ~/bin/erls/21.3/activate


Example: Building Erlang 19.3.6.13
++++++++++++++++++++++++++++++++++

Below you can see the commands use to:

- setup a new shell with Kerl: ``use-kerl``,
- use Kerl to list all available Erlang versions: ``kerl update releases``,
- use Kerl to build Erlang 19.3.6.13: ``kerl build 19.3.6.13 19.3.6.13``,
- use Kerl to install Erlang 19.3.6.13 in ~/bin/erls: ``kerl install 19.3.6.13
  ~/bin/erls/19.3.6.13n``.

For this build I do not have Java tools available, so the build did not create
Erlang's JInterface.

.. code:: shell

    Last login: Sat Jul  4 18:25:03 on ttys014
    > use-kerl
    Now using the Homebrew-installed GNU Make in this shell
    GNU Make 4.3
    Built for x86_64-apple-darwin18.7.0
    Copyright (C) 1988-2020 Free Software Foundation, Inc.
    License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
    This is free software: you are free to change and redistribute it.
    There is NO WARRANTY, to the extent permitted by law.

    >Pierres-iMac@Sat Jul 04@18:39:44[~]
    > kerl update releases
    The available releases are:
    R13B03
    R13B04
    R14A
    ...
    19.3.6.13
    ...
    20.3.2.1
    20.3.3
    20.3.4
    20.3.5
    20.3.6
    ...
    20.3.8.26
    21.0-rc1
    21.0-rc2
    21.0
    ...
    22.3.4.1
    22.3.4.2
    23.0-rc1
    23.0-rc2
    23.0-rc3
    23.0
    23.0.1
    23.0.2

    > kerl build 19.3.6.13 19.3.6.13
    Downloading OTP-19.3.6.13.tar.gz to /Users/roup/.kerl/archives
      % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                     Dload  Upload   Total   Spent    Left  Speed
    100   125  100   125    0     0    395      0 --:--:-- --:--:-- --:--:--   394
    100 32.4M    0 32.4M    0     0  5854k      0 --:--:--  0:00:05 --:--:-- 7246k
    Extracting source code
    Building Erlang/OTP 19.3.6.13 (19.3.6.13), please wait...
    APPLICATIONS DISABLED (See: /Users/roup/.kerl/builds/19.3.6.13/otp_build_19.3.6.13.log)
     * jinterface     : Java compiler disabled by user

    Building docs...
    Erlang/OTP 19.3.6.13 (19.3.6.13) has been successfully built
    >

On my system the download and the built took about 20 minutes.

The next step required is to install the Erlang version build:

.. code:: shell

    > kerl install 19.3.6.13 ~/bin/erls/19.3.6.13n
    Installing Erlang/OTP 19.3.6.13 (19.3.6.13) in ~/bin/erls/19.3.6.13n...
    You can activate this installation running the following command:
    . ~/bin/erls/19.3.6.13n/activate
    Later on, you can leave the installation typing:
    kerl_deactivate
    >


Kerl Directory Layout
^^^^^^^^^^^^^^^^^^^^^

Kerl stores its files inside the ``~/.kerl`` directory tree.  The directory
holds 3 files (otp_builds, otp_installations and otp_releases) and 2 sub-directories
(archives and builds).

.. code:: shell

    > tree -L 1 -A .kerl
    .kerl
    ├── archives
    ├── builds
    ├── otp_builds
    ├── otp_installations
    └── otp_releases

    2 directories, 3 files
    >

The ``~/.kerl/archives`` stores the compressed tarballs of downloaded Erlang
archives and the ``~/.kerl/builds`` hold the Erlang builds but not in a layout
ready for execution).  Here's the layout at 3 directory level deep taken
after building 19.3.6.13

.. code:: shell

    > tree -d -L 3 -A .kerl
    .kerl
    ├── archives
    └── builds
        ├── 19.0
        │   ├── otp_src_19.0
        │   └── release_19.0
        ├── 19.3.6.13
        │   ├── otp_src_19.3.6.13
        │   └── release_19.3.6.13
        ├── 22.0
        │   ├── otp_src_22.0
        │   └── release_22.0
        ├── 22.1
        │   ├── otp_src_22.1
        │   └── release_22.1
        ├── 22.2
        │   ├── otp_src_22.2
        │   └── release_22.2
        ├── 22.3
        │   ├── otp_src_22.3
        │   └── release_22.3
        ├── 22.3.3
        │   ├── otp_src_22.3.3
        │   └── release_22.3.3
        ├── 22.3.4.2
        │   ├── otp_src_22.3.4.2
        │   └── release_22.3.4.2
        ├── 22.3.4.2n
        │   ├── otp_src_22.3.4.2
        │   └── release_22.3.4.2
        ├── 23.0
        │   ├── otp_src_23.0
        │   └── release_23.0
        ├── 23.0-llvm
        │   ├── otp_src_23.0
        │   └── release_23.0
        ├── 23.0.2
        │   ├── otp_src_23.0.2
        │   └── release_23.0.2
        └── 23.0.2n
            ├── otp_src_23.0.2
            └── release_23.0.2

    41 directories
    >

Looking at ``~/bin/erls`` at 2 directory level deep, we can see that some builds include the man
directory and some don't.  At this point I do not know why that is the case.

.. code:: shell


    > tree -d -L 2 -A bin/erls
    bin/erls
    ├── 19.3.6.13n
    │   ├── bin
    │   ├── doc
    │   ├── erts-8.3.5.7
    │   ├── lib
    │   ├── man
    │   ├── misc
    │   ├── releases
    │   └── usr
    ├── 22.0
    │   ├── bin
    │   ├── erts-10.4
    │   ├── lib
    │   ├── misc
    │   ├── releases
    │   └── usr
    ├── 22.2
    │   ├── bin
    │   ├── erts-10.6
    │   ├── lib
    │   ├── misc
    │   ├── releases
    │   └── usr
    ├── 22.3
    │   ├── bin
    │   ├── erts-10.7
    │   ├── lib
    │   ├── misc
    │   ├── releases
    │   └── usr
    ├── 22.3.3
    │   ├── bin
    │   ├── doc
    │   ├── erts-10.7.1
    │   ├── lib
    │   ├── man
    │   ├── misc
    │   ├── releases
    │   └── usr
    ├── 22.3.4.2
    │   ├── bin
    │   ├── doc
    │   ├── erts-10.7.2.1
    │   ├── lib
    │   ├── man
    │   ├── misc
    │   ├── releases
    │   └── usr
    ├── 22.3.4.2n
    │   ├── bin
    │   ├── doc
    │   ├── erts-10.7.2.1
    │   ├── lib
    │   ├── man
    │   ├── misc
    │   ├── releases
    │   └── usr
    ├── 23.0
    │   ├── bin
    │   ├── doc
    │   ├── erts-11.0
    │   ├── lib
    │   ├── man
    │   ├── misc
    │   ├── releases
    │   └── usr
    ├── 23.0.2
    │   ├── bin
    │   ├── erts-11.0.2
    │   ├── lib
    │   ├── misc
    │   ├── releases
    │   └── usr
    └── llvm-23.0
        ├── bin
        ├── doc
        ├── erts-11.0
        ├── lib
        ├── misc
        ├── releases
        └── usr

    81 directories
    >


.. _Kerl: https://github.com/kerl/kerl
.. _XCode: https://developer.apple.com/xcode/
.. _OpenSSL: https://en.wikipedia.org/wiki/OpenSSL

Launching a shell with a Kerl-built Erlang
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

I previously built Erlang 23.0.2 using the exact same method described above.
That build was using the macOS native compiler toolchain.  I created a shell
script called ``envfor-erlang-23-kn`` to setup a shell with that version of
Erlang and by ``.bashrc`` file has the alias ``use-erlang-23-kn`` to source
that script.

Here's the script:

.. code:: bash

    #!/usr/bin/env bash
    # Abstract: Install Erlang 23.0.2 (built with Kerl/native Clang)
    # Last Modified Time-stamp: <2020-07-03 11:55:38, updated by Pierre Rouleau>
    # -----------------------------------------------------------------------------
    # This file *must* be sourced.
    #
    # Run with: use-erlang-23-kn
    #
    #
    # It uses Kerl activate to install Erlang 23.0.2

    # -----------------------------------------------------------------------------
    if [ "$DIR_ERLANG_DEV" == "" ]; then
        export DIR_ERLANG_DEV="$HOME/dev/erlang"
        MANPATH=$HOME/docs/Erlang/otp-23.0/man/man:`manpath`
        export MANPATH
        echo "+ Erlang 23.0.2 (built with Kerl/native Clang) environment set."
        echo "+ Using OTP-23 Man pages."
        echo "Use kerl_deactivate to deactivate it."
        settitle "Erlang 23.0.2 Kerl/Native"
        source ~/bin/erls/23.0.2/activate
    else
        echo "! Erlang environment was already set for this shell."
    fi

    # -----------------------------------------------------------------------------

For 23.0.2 the Man pages were not part of the build, so the script sets up
``MANPATH`` to use the manually downloaded version of the OTP-23 man pages.

And the ``.bashrc`` aliases I have for Erlang built with Kerl and macOS native
compiler tool chain:

.. code:: shell

    # Kerl-built Erlang versions
    # - built with macOS native Clang
    alias use-erlang-23-kn='source envfor-erlang-23-kn'
    alias use-erlang-22-kn='source envfor-erlang-22-kn'
    alias use-erlang-19-kn='source envfor-erlang-19-kn'


Then I can use the shell:

.. code:: shell

    Last login: Sat Jul  4 19:25:43 on ttys016
    > use-erlang-23-kn
    + Erlang 23.0.2 (built with Kerl/native Clang) environment set.
    + Using OTP-23 Man pages.
    Use kerl_deactivate to deactivate it.
    > which erl
    /Users/roup/bin/erls/23.0.2/bin/erl
    > version-erl
    23.0.2
    > man -w erl
    /Users/roup/docs/Erlang/otp-23.0/man/man/man1/erl.1
    > man -w lists
    /Users/roup/docs/Erlang/otp-23.0/man/man/man3/lists.3
    > erl
    Erlang/OTP 23 [erts-11.0.2] [source] [64-bit] [smp:8:8] [ds:8:8:10] [async-threads:1] [hipe] [dtrace]

    Eshell V11.0.2  (abort with ^G)
    1> q().
    ok
    2> >
    >


..
   -----------------------------------------------------------------------------


Using asdf-vm
~~~~~~~~~~~~~

With the asdf-vm_ tool, you can "*manage multiple runtime versions with a
single CLI tool*" (as written on the asdf-vm_ site).
You can build, install and activate multiple versions of
Erlang as well as a lot of other things like Elixir and other un-related
programming languages and tools.  To asdf-vm, Erlang, like Elixir and Python
is a *plugin*. The concept of *plugin* here applies to a programming language,
or a specific tool. They are considered at the same level.

The asdf tool does everything.  With it you can list the various languages
that you want to use, their versions, and install them on the system very
easily.  When *installing* a version of a tool, it downloads the source code
and perform the complete build.

On my system I did not have to setup the version of OpenSSL to use with
asdf-vm as I had to do with Kerl.  asdf was able to detect the latest version
of OpenSSL I have on my system (as of this writing, version 1.1.1g released
April 21, 2020).

.. _asdf-vm: https://asdf-vm.com/#/
.. _Get and manage asdf -vm itself: https://asdf-vm.com/#/core-manage-asdf-vm
.. _List available plugins, get the ones you need, manage them.: https://asdf-vm.com/#/core-manage-plugins
.. _Get, compile and install a specific version of the plugin.:  https://asdf-vm.com/#/core-manage-versions
.. _identify a current version: https://asdf-vm.com/#/core-manage-versions?id=set-current-version

Setting the Environment for asdf
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

For asdf-vm_ I wrote the ``use-asdf`` alias to the ``envfor-asdf`` script that
it sources.

The ``envfor-asdf`` script is shown here:

.. code:: bash

    #!/usr/bin/env bash
    # Abstract: Install asdf into a shell : tool to build/manage Erlang, Elixir, Ruby, NodeJs
    # Last Modified Time-stamp: <2020-07-03 14:35:47, updated by Pierre Rouleau>
    # -----------------------------------------------------------------------------
    # This file *must* be sourced.
    #
    # Run with: use-asdf
    #
    # -----------------------------------------------------------------------------
    # References:
    # - Manage asdf-vm          : https://asdf-vm.com/#/core-manage-asdf-vm
    # - Adopting Erlanf - Setup : https://adoptingerlang.org/docs/development/setup/
    #
    # -----------------------------------------------------------------------------
    if [ "$ROUP_ENVFOR_ASDF" == "" ]; then
        export ROUP_ENVFOR_ASDF=1
        export KERL_BUILD_DOCS=yes
        export KERL_INSTALL_MANPAGES=yes
        export KERL_INSTALL_HTMLDOCS=yes
        . $(brew --prefix asdf)/asdf.sh
        . $(brew --prefix asdf)/etc/bash_completion.d/asdf.bash
        printf "ASDF support now installed in this shell.\n"
        printf "ASDF uses "
        $(brew --prefix openssl)/bin/openssl version
        settitle "Using ASDF"
    else
        printf "Shell is already setup for ASDF!\n"
        return 1
    fi
    # -----------------------------------------------------------------------------


The alias in my ``.bashrc`` file is:

.. code:: shell

  alias use-asdf='source envfor-asdf'


Then, to install a new version of Erlang using asdf_vm_,  the important steps are:

#. Set the shell for asdf-vm_ by executing the ``use-asdf`` alias to the
   ``envfor-asdf`` script it sources.
#. `Get and manage asdf -vm itself`_.  These are the instructions to install
   and manage asdf-vm.  You have to do this the very first time and then only
   when you want tu upgrade asdf-vm_ itself.
#. `List available plugins, get the ones you need, manage them.`_  You can
   list all available plugins (such as Erlang) and all versions available for
   this *plugin*.  So you can list all Erlang versions you can build with it.
#. `Get, compile and install a specific version of the plugin.`_  These are
   the commands you use to build and install something like a version of Erlang.


Once this is all done and you have compiled and installed one or several
versions of a given *plugin* (sucha as Erlang)  it's possible to `identify a current version`_ of a given
plugin to be used globally (it persists).  You can also use a command to
activate that version just for the current shell.

On my system I use the mechanism that activates a specific version of Erlang
for the shell using the same mechanism as I do for the other 3 ways of dealing
with Erlang: a ``use-erlang-xx-a`` alias defined in the ``.bashrc`` file to a
shell script it sources.  The shell script has a name like
``envfor-erlang-xx-a``.  The ``xx`` is Erlang version number and the ``-a``
suffix identifies thet asdf-vm toolchain.


asdf commands
^^^^^^^^^^^^^

The asdf commands must be installed in the shell.  For that I execute my
``use-asdf`` alias to source my ``envfor-asdf`` script.  Once done, you can
use all asdf commands to:

- `update asdf-vm`_
- `manage asdf plugins`_
- `manage asdf plugins versions`_ (eg. build and install new versions of Erlang).

More information is available on the asdf-vm_ site.


.. _update asdf-vm: https://asdf-vm.com/#/core-manage-asdf-vm
.. _manage asdf plugins: https://asdf-vm.com/#/core-manage-plugins
.. _manage asdf plugins versions: https://asdf-vm.com/#/core-manage-versions




Example: Building Erlang 22.3.4.2
+++++++++++++++++++++++++++++++++

Here I build 2 different versions of Erlang with asdf-vm_: Erlang 23.0.2 and
22.3.4.2 with the following commands.

First I set the environment:

- ``use-asdf``

Then I check what is available:

- ``asdf plugin list``
- ``asdf plugin update --all``
- ``asdf list all erlang``

I perform the 2 builds:

- ``asdf install erlang 23.0.2``
- ``asdf install erlang 22.3.4.2``

And list the Erlang versions I have built with asdf-vm_ so far.

- ``asdf list erlang``

The asdf_vm_ can identify a version of each *plugin* as being the global
current version.  I list them with the following command and see that I did
not set any since I use a shell script to do that .  However, to have the
version used automatically on system startup you would probably want to
identify a global current version.

- ``asdf current``

Here's the session:

.. code:: shell

    Last login: Fri Jul  3 14:36:46 on ttys004
    > use-asdf
    ASDF support now installed in this shell.
    asdf uses OpenSSL 1.1.1g  21 Apr 2020
    > asdf plugin list
    elixir
    erlang
    > asdf plugin update --all
    Updating elixir...
    Already on 'master'
    Your branch is up to date with 'origin/master'.
    Updating erlang...
    remote: Enumerating objects: 27, done.
    remote: Counting objects: 100% (27/27), done.
    remote: Compressing objects: 100% (17/17), done.
    remote: Total 23 (delta 12), reused 12 (delta 6), pack-reused 0
    Unpacking objects: 100% (23/23), 8.44 KiB | 664.00 KiB/s, done.
    From https://github.com/asdf-vm/asdf-erlang
       13422da..4164f2b  master     -> master
       13422da..4164f2b  master     -> origin/master
    Already on 'master'
    Your branch is up to date with 'origin/master'.
    > asdf list all erlang
    R13B03
    R13B04
    R14A
    ...
    ...
    ...
    22.3.4.2
    23.0-rc1
    23.0-rc2
    23.0-rc3
    23.0
    23.0.1
    23.0.2
    > asdf list erlang
      21.3
      22.3.3
      22.3.4
      23.0
    > asdf install erlang 23.0.2
    asdf_23.0.2 is not a kerl-managed Erlang/OTP installation
    No build named asdf_23.0.2
    Downloading OTP-23.0.2.tar.gz to /Users/roup/.asdf/plugins/erlang/kerl-home/archives
      % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                     Dload  Upload   Total   Spent    Left  Speed
    100   122  100   122    0     0    416      0 --:--:-- --:--:-- --:--:--   417
    100 53.7M    0 53.7M    0     0  6988k      0 --:--:--  0:00:07 --:--:-- 8222k
    Extracting source code
    Building Erlang/OTP 23.0.2 (asdf_23.0.2), please wait...
    APPLICATIONS DISABLED (See: /Users/roup/.asdf/plugins/erlang/kerl-home/builds/asdf_23.0.2/otp_build_23.0.2.log)
     * jinterface     : No Java compiler found

    Building docs...
    Erlang/OTP 23.0.2 (asdf_23.0.2) has been successfully built
    Installing Erlang/OTP 23.0.2 (asdf_23.0.2) in /Users/roup/.asdf/installs/erlang/23.0.2...
    You can activate this installation running the following command:
    . /Users/roup/.asdf/installs/erlang/23.0.2/activate
    Later on, you can leave the installation typing:
    kerl_deactivate
    Cleaning up compilation products for
    Cleaned up compilation products for  under /Users/roup/.asdf/plugins/erlang/kerl-home/builds
    ln: ./erl_call: File exists

    Erlang 23.0.2 has been installed. Activate globally with:

        asdf global erlang 23.0.2

    Activate locally in the current folder with:

        asdf local erlang 23.0.2

    > asdf install erlang 22.3.4.2
    asdf_22.3.4.2 is not a kerl-managed Erlang/OTP installation
    No build named asdf_22.3.4.2
    Downloading OTP-22.3.4.2.tar.gz to /Users/roup/.asdf/plugins/erlang/kerl-home/archives
      % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                     Dload  Upload   Total   Spent    Left  Speed
    100   124  100   124    0     0    443      0 --:--:-- --:--:-- --:--:--   442
    100 53.2M    0 53.2M    0     0  7249k      0 --:--:--  0:00:07 --:--:-- 8223k
    Extracting source code
    Building Erlang/OTP 22.3.4.2 (asdf_22.3.4.2), please wait...
    APPLICATIONS DISABLED (See: /Users/roup/.asdf/plugins/erlang/kerl-home/builds/asdf_22.3.4.2/otp_build_22.3.4.2.log)
     * jinterface     : No Java compiler found

    Building docs...
    Erlang/OTP 22.3.4.2 (asdf_22.3.4.2) has been successfully built
    Installing Erlang/OTP 22.3.4.2 (asdf_22.3.4.2) in /Users/roup/.asdf/installs/erlang/22.3.4.2...
    You can activate this installation running the following command:
    . /Users/roup/.asdf/installs/erlang/22.3.4.2/activate
    Later on, you can leave the installation typing:
    kerl_deactivate
    Cleaning up compilation products for
    Cleaned up compilation products for  under /Users/roup/.asdf/plugins/erlang/kerl-home/builds

    Erlang 22.3.4.2 has been installed. Activate globally with:

        asdf global erlang 22.3.4.2

    Activate locally in the current folder with:

        asdf local erlang 22.3.4.2

    > asdf list erlang
      21.3
      22.3.3
      22.3.4.2
      22.3.4
      23.0.2
      23.0
    > asdf current
    elixir         No version set for elixir; please run `asdf <global | local> elixir <version>`
    erlang         No version set for erlang; please run `asdf <global | local> erlang <version>`
    >

At the end of asdf build, asdf removes the build log file.  There might be an
option to keep it, but I have been too lazy to look for it.  Instead, if I
want to look into the log I use Emacs and open the log file in auto-revert
mode.  I can then watch the build and save a copy somewhere.

.. note::  You may be interested by my `PEL project`_ which describes lots of Emacs commands
           in extensive PDF table files and provide an Emacs system that minimizes the
           need to know Emacs Lisp. See the `PEL File Management PDF table`_ for info on the
           auto-revert mode command.



.. _PEL project:                   https://github.com/pierre-rouleau/pel
.. _PEL File Management PDF table: https://github.com/pierre-rouleau/pel/blob/master/doc/pdf/file-mngt.pdf


Running Erlang built with asdf
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

I use the same strategy as for the others.
In my ``.bashrc`` vile I have aliases to source the shell scripts I need:

.. code:: shell

    # Erlang, Elixir, Ruby, NodeJs : ASDF shell
    # -----------------------------------------
    alias use-asdf='source envfor-asdf'
    alias use-erlang-21-a='source envfor-erlang-21-a'
    alias use-erlang-22-a='source envfor-erlang-22-a'
    alias use-erlang-23-a='source envfor-erlang-23-a'

The script ``envfor-erlang-23-a`` installs Erlang 23.0.2 built with asdf-vm_.
Here's the script:

.. code:: bash

    #!/usr/bin/env bash
    # Abstract: Install Erlang 23.0.2 (built with asdf/native Clang)
    # Last Modified Time-stamp: <2020-07-05 09:26:34, updated by Pierre Rouleau>
    # -----------------------------------------------------------------------------
    # This file *must* be sourced.
    #
    # Run with: use-erlang-23-a
    #
    #
    # This script uses:
    # - `use-asdf` alias to source the `envfor-asdf` script,
    # - `asdf` command to activate Erlang 23.0.2 locally.
    # - settitle script to set the terminal title.

    # -----------------------------------------------------------------------------
    if [ "$DIR_ERLANG_DEV" == "" ]; then
        export DIR_ERLANG_DEV="$HOME/dev/erlang"
        MANPATH=$HOME/docs/Erlang/otp-23.0/man/man:`manpath`
        export MANPATH
        echo "+ Erlang 23.0.2 (built with asdf-vm/native Clang) environment set."
        echo "+ Using OTP-23 Man pages."
        echo "Note: asdf is leaving a .tool-version in the current directory!"
        use-asdf
        asdf local erlang 23.0.2
        settitle "Erlang 23.0.2a asdf/Native"
    else
        echo "! Erlang environment was already set for this shell."
    fi

    # -----------------------------------------------------------------------------

And here's a session using it to install Erlang 23.0.2:

.. code:: shell

    Last login: Sun Jul  5 09:25:56 on ttys003
    > use-erlang-23-
    use-erlang-23-a   use-erlang-23-ei  use-erlang-23-kn
    > use-erlang-23-a
    + Erlang 23.0.2 (built with asdf-vm/native Clang) environment set.
    + Using OTP-23 Man pages.
    Note: asdf is leaving a .tool-version in the current directory!
    ASDF support now installed in this shell.
    > asdf current
    elixir         No version set for elixir; please run `asdf <global | local> elixir <version>`
    erlang         23.0.2   (set by /Users/roup/.tool-versions)
    > which erl
    /Users/roup/.asdf/shims/erl
    > version-erl
    23.0.2
    > man -w erl
    /Users/roup/docs/Erlang/otp-23.0/man/man/man1/erl.1
    > man -w lists
    /Users/roup/docs/Erlang/otp-23.0/man/man/man3/lists.3
    >

**A word of caution**

The asdf software stores the version of the tools used inside a file
called ``.tool-version`` inside the current directory where the asdf commands
were executed.  This can be quite useful: if you use several versions of
several tools you can create a directory that will be the current directory
where you will use all of these tool at the version specified inside the
file ``.tool-version``.  Once set up, open a shell, execute ``use-asdf`` and
then the version of the tool will be identified by the ``.tool-version`` file
stored in the current directory.  So **asdf is sensitive to the current
directory where the erl command is issued**.

Unlike the other tools (Erlang Solutions' Erlang Installer, Kerl-built
versions), you cannot use the same directory in 2 different shells and launch
2 different versions of Erlang, on in each shell.

It's possible to run multiple versions of Erlang at the same time, but they
must each be instantiated from a shell that has a different current directory.

With asdf  if you open 2 shells and execute ``use-erlang-23-a`` in the
first shell and then inside another shell execute ``use-erlang22-a`` in that
other shells, **from the same directory** both shells will now use the Erlang set up by
``use-erlang-22-a`` because they both use the same shim file identified by the
same ``.tool-version`` file.



asdf Directory Layout
^^^^^^^^^^^^^^^^^^^^^

The directory used by asdf-vm is ``~/.asdf``.  The top directory contains no
files, it holds only sub-directories.  This is teh layout of this directory
tree shown with a depth of 3:

.. code:: shell

          > tree -L 4 -d  -A .asdf
          .asdf
          ├── installs
          │   ├── elixir
          │   │   ├── 1.10.0
          │   │   │   ├── bin
          │   │   │   ├── lib
          │   │   │   └── man
          │   │   ├── 1.10.1
          │   │   │   ├── bin
          │   │   │   ├── lib
          │   │   │   └── man
          │   │   ├── 1.10.2
          │   │   │   ├── bin
          │   │   │   ├── lib
          │   │   │   └── man
          │   │   └── 1.10.3
          │   │       ├── bin
          │   │       ├── lib
          │   │       └── man
          │   └── erlang
          │       ├── 21.3
          │       │   ├── bin
          │       │   ├── erts-10.3
          │       │   ├── lib
          │       │   ├── misc
          │       │   ├── releases
          │       │   └── usr
          │       ├── 22.3.3
          │       │   ├── bin
          │       │   ├── doc
          │       │   ├── erts-10.7.1
          │       │   ├── lib
          │       │   ├── man
          │       │   ├── misc
          │       │   ├── releases
          │       │   └── usr
          │       ├── 22.3.4
          │       │   ├── bin
          │       │   ├── doc
          │       │   ├── erts-10.7.2
          │       │   ├── lib
          │       │   ├── man
          │       │   ├── misc
          │       │   ├── releases
          │       │   └── usr
          │       ├── 22.3.4.2
          │       │   ├── bin
          │       │   ├── doc
          │       │   ├── erts-10.7.2.1
          │       │   ├── lib
          │       │   ├── man
          │       │   ├── misc
          │       │   ├── releases
          │       │   └── usr
          │       ├── 23.0
          │       │   ├── bin
          │       │   ├── doc
          │       │   ├── erts-11.0
          │       │   ├── lib
          │       │   ├── misc
          │       │   ├── releases
          │       │   └── usr
          │       └── 23.0.2
          │           ├── bin
          │           ├── doc
          │           ├── erts-11.0.2
          │           ├── lib
          │           ├── misc
          │           ├── releases
          │           └── usr
          ├── plugins
          │   ├── elixir
          │   │   ├── bin
          │   │   └── shims
          │   └── erlang
          │       ├── bin
          │       └── kerl-home
          │           └── archives
          ├── repository
          │   └── plugins
          ├── shims
          └── tmp

          81 directories
          >


The ``~/.asdf/shims`` directory holds a set of script files that invoke the
real Erlang commands via an asdf command.

On my system I have installed some versions of Erlang and Elixir with asdf,
and the shims I see are shown here:

.. code:: shell


    > ls -F .asdf/shims
    cdv*                            elixirc*                        etop*                           snmpc*
    codeline_preprocessing.escript* emem*                           iex*                            start*
    cpu_sup*                        epmd*                           memsup*                         start_erl*
    ct_run*                         erl*                            mix*                            to_erl*
    dialyzer*                       erl_call*                       odbcserver*                     typer*
    diameterc*                      erlc*                           run_erl*                        xml_from_edoc.escript*
    elixir*                         escript*                        runcgi.sh*
    >

The content of ``~/.asdf/shims/erl`` which is used to invoke the Erlang shell
is:

.. code:: bash

    #!/usr/bin/env bash
    # asdf-plugin: erlang 21.3
    # asdf-plugin: erlang 23.0
    # asdf-plugin: erlang 22.3.3
    # asdf-plugin: erlang 22.3.4
    # asdf-plugin: erlang 23.0.2
    # asdf-plugin: erlang 22.3.4.2
    exec /usr/local/opt/asdf/bin/asdf exec "erl" "$@"

It uses asdf to execute the erl for the Erlang version identified by the
file .tool-versions stored in the current directory.

Creating whatis files for man pages
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

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

When learning Erlang, it might be useful to create an
environment where the only ``man`` topics available are the ones related to
Erlang.  It's easy: set ``MANPATH`` to the directory holding the Erlang man
pages files.  If you are also using Emacs, then Emacs man auto-completion will
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

I wrote the following Bash script to simplify the process:

.. code::  bash

    #!/usr/bin/env bash
    # Name: make-local-whatis
    # Abstract: Create a man whatis file for local man directory tree
    # Last Modified Time-stamp: <2020-07-17 13:48:17, updated by Pierre Rouleau>
    # -----------------------------------------------------------------------------
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
    # -----------------------------------------------------------------------------
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


Here's a session that demonstrates the above:

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
.. _makewhatis command line utility: https://man.openbsd.org/makewhatis.8

Erlang Man files to use with Emacs
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Emacs support for Erlang uses the Erlang man files.  Several packages uses the
Erlang man page files and they may install them in different location.
This section describes where various Emacs packages for Erlang support
install the man pages and how to consolidate them into one location.


Used by the standard Erlang mode (erlang.el)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The erlang.el stores only one version of the man files in
``~/.emacs.d/cache/erlang_mode_man_pages/`` directory.
The directory holds:

.. code:: ls

        -rw-r--r--  1 roup  staff    16239 17 Sep  2019 COPYRIGHT
        -rw-r--r--  1 roup  staff      842 17 Sep  2019 PR.template
        -rw-r--r--  1 roup  staff     4167 17 Sep  2019 README.md
        -rw-r--r--  1 roup  staff       51 22 Jul 10:32 erlang_man_download_url
        drwxr-xr-x  7 roup  staff      224 17 Sep  2019 man
        -rw-r--r--  1 roup  staff  1355169 22 Jul 07:44 man.tar.gz

Used by EDTS
^^^^^^^^^^^^

EDTS stores the man pages of several Erlang versions inside a sub-directory of
``~/.emacs.d/edts/doc/`` identifying the version.  For example, the files for
Erlang version 23.0 are stored inside ``~/.emacs.d/edts/doc/23.0``.
The directory holds:

.. code:: ls

        -rw-r--r--   1 roup  staff  16239 12 May 17:41 COPYRIGHT
        -rw-r--r--   1 roup  staff    842 12 May 17:41 PR.template
        -rw-r--r--   1 roup  staff   4167 12 May 17:41 README.md
        drwxr-xr-x   7 roup  staff    224 12 May 17:30 man


Consolidating all Erlang Man Files in one location
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

As described above, you may install Erlang in various ways, with the file
stored in various locations depending on the method used to install a specific
version of Erlang.

Ideally, there would be a way to work on several projects *concurrently* even
if those projects use different versions of Erlang. Also, ideally, when using
Emacs, you'd want to be able to use the various Emacs tools for Erlang and
ensure they find the man files in their expected locations.

At the same time you'd want to be able to access Erlang Man files from the
shell using the man command and maintain only one copy for each Erlang
version.

If you are using Emacs, you'll notice several Emacs packages that support Erlang.
The erlang.el package supports on version of Erlang.  The edts package
supports multiple versions of Erlang.  And each of them have the ability to
download the Erlang man files and store them in a directory they control.

- The erlang.el package stores the erlang man page files inside the directory
  ``~/.emacs.d/cache/erlang_mode_man_pages/V``  where ``V`` is the Erlang
  version.
- The edts package stores the Erlang man page files inside the directory
  ``~/.emacs.d/edts/doc/VV`` where ``VV`` is the Erlang version.  There can be
  several ``VV`` directories, one per Erlang version supported.

Like I did, you may also have downloaded the Erlang man pages somewhere else
because you downloaded the entire Erlang source package and built Erlang
yourself, or because you are using an pre-built version of Erlang or for
whatever else reason.

One way to consolidate all of that is to use symbolic links.  What I did is
to place symlinks inside the edts directory to the locations where I stored
the Erlang man files.  In my case I stored all Erlang documentation files
inside the ``~/docs/Erlang`` directory which contains the entire documentation
tree of a each specific Erlang versions I am interested in.

For example, the man man files for Erlang 17.5 are stored inside
the directory ``~/docs/Erlang/otp-17.5/man``.  Here's a partial tree view
of the directory tree (I removed several lines for clarity):

.. code:: shell

    > tree -L 3 otp-17.5
    otp-17.5
    ├── html
    ├── man
    │   ├── COPYRIGHT
    │   ├── PR.template
    │   ├── README
    │   ├── erlang_man_download_url
    │   └── man
    │       ├── man1
    │       ├── man3
    │       ├── man4
    │       ├── man6
    │       ├── man7
    │       └── whatis
    └── readme.txt

    77 directories, 17 files
    >

Notice the ``erlang_man_download_url`` file.  This is a file created and used
by edts. It contains the URL where the man files can be downloaded.  The
file contains the following single line of text::

  https://erlang.org/download/otp_doc_man_17.5.tar.gz

Also notice the ``whatis`` file in the ``man`` directory.  I created that file
using the method explained in `Creating whatis files for man pages`_ to allow
me to restrict the man pages to Erlang only and take advantage of Emacs
completion using the Emacs man command.

Then I created the symlinks in the ``~/.emacs.d/edts/doc`` directory:

.. code:: shell


    > cd ~/.emacs.d/edts/doc
    > ln -s  /Users/roup/docs/Erlang/otp-22.3/man  22.3
    > ln -s  /Users/roup/docs/Erlang/otp-22.2/man  22.2
    > ln -s  /Users/roup/docs/Erlang/otp-21.3/man  21.3
    > ln -s  /Users/roup/docs/Erlang/otp-20.3/man  20.3
    > ln -s  /Users/roup/docs/Erlang/otp-19.3/man  19.3
    > ln -s  /Users/roup/docs/Erlang/otp-18.3/man  18.3
    > ln -s  /Users/roup/docs/Erlang/otp-17.5/man  17.5
    > ll
    total 0
    lrwxr-xr-x  1 roup  staff  -  36 22 Jul 10:47 17.5@ -> /Users/roup/docs/Erlang/otp-17.5/man
    lrwxr-xr-x  1 roup  staff  -  36 22 Jul 10:47 18.3@ -> /Users/roup/docs/Erlang/otp-18.3/man
    lrwxr-xr-x  1 roup  staff  -  36 22 Jul 10:46 19.3@ -> /Users/roup/docs/Erlang/otp-19.3/man
    lrwxr-xr-x  1 roup  staff  -  36 22 Jul 10:46 20.3@ -> /Users/roup/docs/Erlang/otp-20.3/man
    lrwxr-xr-x  1 roup  staff  -  36 22 Jul 10:46 21.3@ -> /Users/roup/docs/Erlang/otp-21.3/man
    lrwxr-xr-x  1 roup  staff  -  36 22 Jul 10:45 22.2@ -> /Users/roup/docs/Erlang/otp-22.2/man
    lrwxr-xr-x  1 roup  staff  -  36 22 Jul 10:44 22.3@ -> /Users/roup/docs/Erlang/otp-22.3/man
    drwxr-xr-x  6 roup  staff  - 192 20 Jul 17:47 23.0/
    >

And then I create a symlink inside ``~/.emacs.d/cache`` called
``erlang_mode_man_pages`` to the location of the directory holding the man
pages of the default Erlang version for the shell.

Ideally that should be all controlled from the version of Erlang used in the
shell or in the project.   The edts package does some of this.  I'm planning
to wrap this all up with code controlled by my Emacs PEL system. But this is
still work in progress at the moment.




-----------------------------------------------------------------------------
