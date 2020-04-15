=====================================================
About the Erlang Programming Language and Environment
=====================================================

:Time-stamp: <2020-04-15 08:16:11, updated by Pierre Rouleau>
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
More information, is available in the documents listed below:

- `Installing Erlang on macOS`_, part of my `macOS Development Environment`_ document.



.. _Installing Erlang on macOS: https://github.com/pierre-rouleau/about-macOS/blob/master/doc/macos-env.rst#environment-for-erlang
.. _Erlang OTP Download page:   https://www.erlang.org/downloads
.. _macOS Development Environment: https://github.com/pierre-rouleau/about-macOS/blob/master/doc/macos-env.rst



-----------------------------------------------------------------------------
