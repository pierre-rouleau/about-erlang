===============================
Installing Erlang with Homebrew
===============================

:Home page: https://github.com/pierre-rouleau/about-erlang
:Time-stamp: <2021-05-15 13:30:08, updated by Pierre Rouleau>
:Copyright:  Copyright © 2021, Pierre Rouleau
:License: `MIT <../LICENSE>`_

.. contents::  **Table of Contents**
.. sectnum::

.. ---------------------------------------------------------------------------

Homebrew_ is a popular package manager for macOS (and now also for Linux).
You can install Erlang with it.  But be aware of the following pros and cons:

**Pros**:  It is very easy to install Erlang with Homebrew. See the
instructions below.

**Cons**: Homebrew installs a version that it will eventually want to
upgrade. It is fine when just experimenting with Erlang but this will not help
you if you want to create a system that will be running for a long time.
It's possible to prevent homebrew from upgrading it by using the ``brew pin
erlang`` command though.  See `Homebrew FAQ`_ if you want to do that.

Installation Instructions
=========================

Install Homebrew
----------------

- If you don't already have it, install the Homebrew command line utility
  (``brew``) using the instructions right on the `Homebrew home page`_.
- You can then use the various commands:

  - ``brew search`` to search for a package.  For Erlang: ``brew search
    erlang`` will do.
  - ``brew info`` to get more info about a package. Something like ``brew info
    erlang``.  This will describe the version and its dependencies.
  - ``brew install`` to install a given package.  To install Erlang with
    Homebrew, the command is: ``brew install erlang``.


Check what Homebrew Installs
----------------------------

First check what version of Erlang will be installed by Homebrew:

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

Install Erlang with Homebrew
----------------------------

To install, you should update and upgrade Homebrew, then install Erlang with
the following 3 consecutive commands::

    brew update
    brew upgrade
    brew install erlang

On a macOS system, if all went well Homebrew should have installed Erlang
binaries somewhere under ``/usr/local/Cellar`` and placed symlinks inside
``/usr/local/bin``.

If you execute ``which erl`` you should get something like ``/usr/local/bin/erl``.

Make sure ``/usr/local/bin`` is in your PATH.

Once it's done You should be able to run the Erlang REPL and the compiler.
In your main shell.

A little more work is required to also be able to open the Erlang Man files.

Complete shell setup with access to Erlang Man files
----------------------------------------------------

On my systems I like to be able to have quick commands to setup and modify
shell environments.  To do that I use the following:

- A shell script that:

  - sets up environment variables such as ``PATH``, ``MANPATH``,
  - prints information about what is being set up,
  - set a title for the shell, so I can quickly identify the terminal window,
  - and whatever   is required to set up the programming environment.

  That script must be sourced.  I put the script  in``~/bin`` which is on my
  ``PATH``.  The execute bit of the script file is not set, preventing the
  script from being invoked directly.   The names for these scripts all start
  with the ``envfor-`` prefix.  For Erlang they're ``envfor-erlang-``.

  - For the Homebrew installation of Erlang, the script is
    ``~/bin/envfor-erlang-hb``.  There's only one since you will normally have
    only one Erlang version controlled by Homebrew.

- A shell command alias set up in ``~/.bashrc`` that refers to the script in
  ``~/bin``.  These aliases all have a name that starts with the ``use-``
  prefix.  For Erlang, they are named ``use-erlang-`` something.  For the
  Homebrew installation of Erlang the alias is ``use-erlang-hg``.






.. _Homebrew home page:
.. _Homebrew: https://brew.sh
.. _Homebrew/discussions on GitHub: https://github.com/Homebrew/discussions/discussions
.. _Homebrew FAQ:  https://docs.brew.sh/FAQ


.. ---------------------------------------------------------------------------
