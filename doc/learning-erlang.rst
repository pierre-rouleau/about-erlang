===============
Learning Erlang
===============

:Home page: https://github.com/pierre-rouleau/about-erlang
:Time-stamp: <2020-08-22 22:51:26, updated by Pierre Rouleau>
:Copyright:  Copyright © 2020, Pierre Rouleau
:License: `MIT <../LICENSE>`_


.. contents::  **Table of Contents**
.. sectnum::


Authority Information
=====================


============================ ===========================================================================================================================
Topic                        Content
============================ ===========================================================================================================================
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
============================ ===========================================================================================================================


Code Guidelines & Quick Sheets
==============================

============================ ===========================================================================================================================
Topic                        Content
============================ ===========================================================================================================================
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
============================ ===========================================================================================================================




Learning Resources
==================


============================ ===========================================================================================================================
Topic                        Content
============================ ===========================================================================================================================
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
============================ ===========================================================================================================================


Language References
===================


============================ ===========================================================================================================================
Topic                        Content
============================ ===========================================================================================================================
**References**               **Erlang - Sequential**

                             - **Type Specifications**

                               - `Types and Function Specifications`_  (at `erlang.org`_).

                                 - `Types (or lack thereof)`_ (at `LYSEFGG`_).
                                 - `Type Specifications and Erlang`_ (at `LYSEFGG`_).

                               - `TypEr: A Type Annotator of Erlang Code`_   (at `erlang.org`_).

                                 - `TypEr: A Type Annotator of Erlang Code`_ (Lindahl, Sogonas paper, Uppsala University, Sweden).

                             - **Data Types**

                               ====================================================== ==================================================================
                               From `erlang.org reference data types`_                Complementary Information
                               ====================================================== ==================================================================
                               - Terms_
                               - `Numbers,`_                                          - Numbers_ [1]_, supports `Bignums`_ but `not in math functions`_.
                               - `atoms,`_                                            - atoms_ and Variables_ [1]_.
                               - boolean_: ``true`` and ``false``                     - `boolean and comparison operators`_ [1]_.
                               - pid_ (`Erlang process`_ identifier)
                               - `port identifier`_ (`Erlang port`_ IDs)
                               - reference_
                               - "strings_" and `escape sequences`_
                               - `bit strings and binaries,`_                         - bit strings
                               - {`tuples,`_}  and records_                           - {tuples_} [1]_
                               - [`lists,`_]                                          - [lists_], `list comprehensions`_ [1]_
                               - map_ and `map expressions`_
                               - `type conversions`_
                               - `Fun`_ and `Fun expressions`_
                               ====================================================== ==================================================================

                             - **Erlang Functions**

                               ====================================================== ==================================================================
                               From `erlang.org - User's Guide`_                      Other
                               ====================================================== ==================================================================
                               - Built-in-Functions: `BIFs concept`_, `list of BIFs`_
                               ====================================================== ==================================================================

                             **Erlang Tools**

                             - **Erlang Shell**

                               - `The Shell <https://learnyousomeerlang.com/starting-out#the-shell>`_ ,
                                 `Shell Commands <https://learnyousomeerlang.com/starting-out#shell-commands>`_
                                 (at `LYSEFGG`_).
                               - Man pages: `Shell <https://erlang.org/doc/man/shell.html>`_.
                               - Related modules:
                                 `shell_default <https://erlang.org/doc/man/shell_default.html>`_,
                                 `shell_docs <https://erlang.org/doc/man/shell_docs.html>`_.
============================ ===========================================================================================================================




Development Resources
=====================


============================ ===========================================================================================================================
Topic                        Content
============================ ===========================================================================================================================
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
============================ ===========================================================================================================================


.. _erlang.org:
.. _Erlang Project Homepage:                      https://www.erlang.org
.. _Erlang On-Line Documentation, Books & Papers: https://www.erlang.org/docs
.. _Joe Armstrong:                                https://en.wikipedia.org/wiki/Joe_Armstrong_(programmer)
.. _Erlang/OTP Documentation:                     https://erlang.org/doc/
.. _Erlang/OTP Documentation with Search:         https://erlang.org/doc/search/
.. _erldocs.com:                                  https://erldocs.com/
.. _erlang.org reference data types:              https://erlang.org/doc/reference_manual/data_types.html
.. _erlang.org - User's Guide:                    https://erlang.org/doc/reference_manual/users_guide.html
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
.. _Erlang process:                               https://erlang.org/doc/reference_manual/processes.html
.. _Erlang port:                                  https://erlang.org/doc/reference_manual/ports.html
.. _Fun:                                          https://erlang.org/doc/reference_manual/data_types.html#fun
.. _Fun expressions:                              https://erlang.org/doc/reference_manual/expressions.html#funs
.. _BIFs concept:                                 https://erlang.org/doc/reference_manual/functions.html#built-in-functions--bifs-
.. _list of BIFs:                                 https://erlang.org/doc/man/erlang.html
.. _Bignums:                                      https://en.wikipedia.org/wiki/Arbitrary-precision_arithmetic
.. _not in math functions:                        https://stackoverflow.com/questions/19893708/will-erlang-have-bignums-for-math-functions



.. [1] From `Learn You Some Erlang for Great Good!`_


-----------------------------------------------------------------------------

..
   Emacs settings: line length is 151 because GitHub fails to render tables
   embedded in tables properly when a row takes more than 1 line and also
   fails when the line is longer than that.
   Local Variables:
   fill-column: 151
   End:


.. ---------------------------------------------------------------------------
