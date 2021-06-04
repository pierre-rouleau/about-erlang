======================================
Using Specialized OS Shells for Erlang
======================================

:Home page: https://github.com/pierre-rouleau/about-erlang
:Navigation: Prev_, Top_
:Created:  Thursday, June  3 2021.
:Author:  Pierre Rouleau <prouleau001@gmail.com>
:Modified: 2021-06-03 17:50:26, by Pierre Rouleau.
:Copyright: © 2021, Pierre Rouleau

.. _Prev:  erlang-man-with-emacs.rst
.. _Top:   installing-erlang.rst


.. contents::  **Table of Contents**
.. sectnum::

.. ---------------------------------------------------------------------------

As described in the sections of `Installing Erlang`_ I create a set of commands
to set up OS shells to use various versions of Erlang.  These commands have
names that identify the Erlang version and the way it was installed or built.
They are shell alias that source the actual script, allowing the setting of
environment variables such as ``MANPATH`` or ``PATH`` to specialize the shell.

Here's a list of some of the commands I use and the relation ship to their
script.

================== =============================== ========= =================
Command Alias      Script                          Erlang
Name                                               Version   Installation Type
================== =============================== ========= =================
use-erlang-hb      ``~/bin/envfor-erlang-hb``      Variable  Homebrew
use-erlang-21-ei   ``~/bin/envfor-erlang-21-ei``   21        Erlang Installer
use-erlang-22-ei   ``~/bin/envfor-erlang-22-ei``   22        Erlang Installer
use-erlang-23-kn   ``~/bin/envfor-erlang-23-kn``   23        Kerl native build
use-erlang-22-kn   ``~/bin/envfor-erlang-22-kn``   22        Kerl native build
use-erlang-23.0-kl ``~/bin/envfor-erlang-23.0-kl`` 23.0      Kerl LLVM build
use-erlang-21-a    ``~/bin/envfor-erlang-21-a``    21        ASDF-vm
use-erlang-22-a    ``~/bin/envfor-erlang-22-a``    22        ASDF-vm
use-erlang-23-a    ``~/bin/envfor-erlang-23-a``    23        ASDF-vm
================== =============================== ========= =================

Normally, there is only one version of Erlang installed by Homebrew so only
one command is defined.  The other commands identify the major version of
Erlang, such as 21, 22 or 23.  The scripts are updated to run the latest minor
version available for that major version.  If the minor version number is
identified in the script name, that exact version is used.  The suffix
identifies the way the Erlang was installed or built.


The command alias are set in the ``~/.bashrc`` file that source the
appropriate script, like this:

.. code:: shell

          alias use-erlang-hb='source envfor-erlang-hb'

Here's a copy of the envfor-erlang-hb script:

.. code:: shell

    # Sourced script.  -*- mode: sh; -*-
    #  Name      : envfor-erlang-hb
    #  Purpose   : Complete Homebrew system Erlang 23.3.4
    #  Created   :
    #  Author    : Pierre Rouleau <prouleau001@gmail.com>
    #  Time-stamp: <2021-05-15 21:43:16, updated by Pierre Rouleau>
    # -----------------------------------------------------------------------------
    # This file *must* be sourced.
    #
    # Run with:  use-erlang
    #
    #
    # It sets up:
    # - the executable path for Erlang 23.3.4 (in fact nothing done; it's already there)
    # - the MANPATH for Erlang 23.3.4 man pages (while keeping access for others)
    # - DIR_ERLANG_DEV environment variable: flag and root of Erlang developed code
    #
    # This protects against multiple execution (via the DIR_ERLANG_DEV envvar).
    #
    # Assumes Erlang 23.3.4 installed with Homebrew:
    # - Erlang 23.3.4 executable files are accessible via symlinks in /usr/local/bin/
    # - Erlang 23.3.4 man files are located in /usr/local/Cellar/erlang/23.3.4/lib/erlang/man

    # -----------------------------------------------------------------------------
    if [ "$DIR_ERLANG_DEV" == "" ]; then
        export DIR_ERLANG_DEV="$HOME/dev/erlang"
        if [ "$MAN_ONLY_ERLANG" == "" ]; then
            MANPATH=/usr/local/Cellar/erlang/23.3.4/lib/erlang/man:`manpath`
        else
            MANPATH=/usr/local/Cellar/erlang/23.3.4/lib/erlang/man
        fi
        if [ -f "/usr/local/Cellar/erlang/23.3.4/lib/erlang/man/whatis" ]; then
            export PEL_ERLANG_VERSION=23.3.4
            export MANPATH
            echo "+ Homebrew-based Erlang 23.3.4 environment set."
            echo "+ Using Cellar/Erlang/23.3.4 Man pages."
            settitle "Erlang 23.3.4 HB"
        else
            echo "Error: missing: /usr/local/Cellar/erlang/23.3.4/lib/erlang/man"
            echo "Execute: make-local-whatis /usr/local/Cellar/erlang/23.3.4/lib/erlang/man"
            echo " then try again."
            echo "Reason: The whatis file is needed to use whatis on Erlang man files."
            echo "        Also Emacs uses it for man auto-completion."
            return 1
        fi
    else
        echo "! Erlang environment was already set for this shell: nothing done this time."
    fi

    # -----------------------------------------------------------------------------


The others are similar.  Here's the copy of envfor-erlang-23-a:

.. code:: shell

    # Sourced script: envfor-erlang-23-a  -*- mode: sh; -*-
    #
    # Purpose   : Install Erlang 23.0.2 (built with asdf/native Clang)
    # Created   : Tuesday, May 18 2021.
    # Author    : Pierre Rouleau <prouleau001@gmail.com>
    # Time-stamp: <2021-06-03 14:36:16, updated by Pierre Rouleau>
    # Copyright © 2021, Pierre Rouleau
    # License   : MIT
    # ----------------------------------------------------------------------------
    # Description
    # -----------
    #
    # Run with: use-erlang-23-a
    #
    # This script uses:
    # - `use-asdf` alias to source the `envfor-asdf` script, to setup asdf-vm
    # - `asdf` command (asdf-vm) to activate Erlang 23.0.2 locally.
    # - settitle script to set the terminal title.
    #
    # This script:
    # - Ensure that the Erlang man pages are available via the man command
    # - Set PEL_ERLANG_VERSION envvar, used by PEL to inform PEL Emacs Lisp code
    # - Set terminal title to indicate which Erlang is used.`
    # - Set DIR_ERLANG_DEV to directory root of Erlang projects.
    #   This also acts as a flag protecting against multiple executions of
    #   scripts that set the Erlang environment.

    # ----------------------------------------------------------------------------
    # Script
    # ------
    #
    if [ "$DIR_ERLANG_DEV" == "" ]; then
        export DIR_ERLANG_DEV="$HOME/dev/erlang"
        if [ "$MAN_ONLY_ERLANG" == "" ]; then
            MANPATH=$HOME/docs/Erlang/otp-23.0/man:`manpath`
        else
            MANPATH=$HOME/docs/Erlang/otp-23.0/man
        fi
        if [ -f "$HOME/docs/Erlang/otp-23.0/man/whatis" ]; then
            export PEL_ERLANG_VERSION=23.0.2
            export MANPATH
            echo "+ Erlang 23.0.2 (built with asdf-vm/native Clang) environment set."
            echo "+ Using OTP-23 Man pages."
            echo "Note: asdf is leaving a .tool-version in the current directory!"
            use-asdf
            asdf local erlang 23.0.2
            settitle "Erlang 23.0.2 asdf/Native"
        else
            echo "Error: missing: $HOME/docs/Erlang/otp-23.0/man"
            echo "Execute make-local-whatis $HOME/docs/Erlang/otp-23.0/man"
            echo " then try again."
            echo "The whatis file is needed to use whatis on Erlang man files."
            echo "Also Emacs uses it for man auto-completion."
            return 1
        fi

    else
        echo "! Erlang environment was already set for this shell."
    fi

    # -----------------------------------------------------------------------------


.. _Installing Erlang: installing-erlang.rst



.. ---------------------------------------------------------------------------

..
       Local Variables:
       time-stamp-line-limit: 10
       time-stamp-start: "^:Modified:[ \t]+\\\\?"
       time-stamp-end:   "\\.$"
       End:
