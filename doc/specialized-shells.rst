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

Command Aliases in shell startup file
=====================================

The command alias are set in the ``~/.bashrc`` file that source the
appropriate script, like this:

.. code:: shell

          alias use-erlang-hb='source envfor-erlang-hb'


Examples of source scripts
==========================

Each of these script is similar in content. Each of them:

- Ensure that the Erlang man pages are available via the man command:

  - Set **MANPATH** to provide access the Erlang man pages

    - If ``MAN_ONLY_ERLANG`` environment variable is set, MANPATH
      is set to that directory only, otherwise the Erlang man directory
      is added in front of the current value of MANPATH.

- Set following environment variables:

  - ``DIR_ERLANG_DEV``:

     Identifies where Erlang projects are stored.
     Also acts as a flag protecting against
     multiple execution of scripts that
     set Erlang environment.

  - ``PEL_ERLANG_VERSION``:

    The version of the active Erlang.

  - ``PEL_ERLANG_MAN_PARENT_DIR``:

    The absolute path of directory that holds Erlang man/man1 directory.


Notice that by default the scripts will update **MANPATH** to hold the
directory where Erlang man files are located as well as all other man
directories as returned by the manpath_ utility.  To set **MANPATH** to only
list the Erlang man files set the ``MAN_ONLY_ERLANG`` environment variable to
any value before executing the ``use-erlang`` command.

Each of these scripts use:

- the `make-local-whatis script`_ to create `whatis files for Erlang`_ when
  they are missing.
- the `settitle script`_ to set the title of the macOS terminal window; it
  helps quickly identify the terminal window when you have several terminal
  windows opened.


For Homebrew
------------

There's only one script for Homebrew-based installations, since you normally
have only one instance of Erlang that have been installed by Homebrew. This is
also why the command name does not include the Erlang version.

Here's a copy of the envfor-erlang-hb script:

.. code:: bash

    # Sourced script.  -*- mode: sh; -*-
    # Name      : envfor-erlang-hb
    # Purpose   : Complete Homebrew system Erlang 23.3.4
    # Created   :
    # Author    : Pierre Rouleau <prouleau001@gmail.com>
    # Time-stamp: <2021-06-04 15:44:32, updated by Pierre Rouleau>
    # Copyright © 2021, Pierre Rouleau
    # License   : MIT
    # -----------------------------------------------------------------------------
    # This file *must* be sourced.
    #
    # Run with:  use-erlang
    #
    #
    # It sets up:
    # - the executable path for Erlang 23.3.4 (in fact nothing done; it's already there)
    # - the MANPATH for Erlang 23.3.4 man pages (while keeping access for others)
    #
    # This assumes that Erlang 23.3.4 was installed with Homebrew:
    # - Erlang 23.3.4 executable files are accessible via symlinks in /usr/local/bin/
    # - Erlang 23.3.4 man files are located in /usr/local/Cellar/erlang/23.3.4/lib/erlang/man
    #
    # This script:
    # - Ensure that the Erlang man pages are available via the man command:
    #   - Set MANPATH to provide access the Erlang man pages
    #     - If MAN_ONLY_ERLANG environment variable is set, MANPATH
    #       is set to that directory only, otherwise the Erlang man directory
    #       is added in front of the current value of MANPATH.
    # - Set following environment variables:
    #   - DIR_ERLANG_DEV            : where Erlang projects are stored.
    #                                 Also acts as a flag protecting against
    #                                 multiple execution of scripts that
    #                                 set Erlang environment.
    #   - PEL_ERLANG_VERSION        : version of the active Erlang
    #   - PEL_ERLANG_MAN_PARENT_DIR : Absolute path of directory that holds
    #                                 Erlang man/man1 directory.
    #
    #  The PEL environment variables are used by Emacs PEL

    # -----------------------------------------------------------------------------
    if [ "$DIR_ERLANG_DEV" == "" ]; then
        export DIR_ERLANG_DEV="$HOME/dev/erlang"
        export PEL_ERLANG_MAN_PARENT_DIR=/usr/local/Cellar/erlang/23.3.4/lib/erlang
        if [ "$MAN_ONLY_ERLANG" == "" ]; then
            MANPATH=$PEL_ERLANG_MAN_PARENT_DIR/man:`manpath`
        else
            MANPATH=$PEL_ERLANG_MAN_PARENT_DIR/man
        fi
        if [ -f "/usr/local/Cellar/erlang/23.3.4/lib/erlang/man/whatis" ]; then
            export PEL_ERLANG_VERSION=23.3.4
            export MANPATH
            echo "+ Homebrew-based Erlang 23.3.4 environment set."
            echo "+ Using Cellar/Erlang/23.3.4 Man pages."
            settitle "Erlang 23.3.4 HB"
        else
            echo "Error: missing: /usr/local/Cellar/erlang/23.3.4/lib/erlang/man/whatis"
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

For Erlang Installer based installations
----------------------------------------

The script is similar for Erlang Installer based installations.

Here's a copy of the envfor-erlang-21-ei:

.. code:: bash


    # Sourced script: envfor-erlang-21-ei  -*- mode: sh; -*-
    #
    # Purpose   : Activate Erlang 21.3.8.7 installed by Erlang Solution Installer
    # Created   : Tuesday, May 18 2021.
    # Author    : Pierre Rouleau <prouleau001@gmail.com>
    # Time-stamp: <2021-06-04 15:45:17, updated by Pierre Rouleau>
    # Copyright © 2021, Pierre Rouleau
    # License   : MIT
    # ----------------------------------------------------------------------------
    # Description
    # -----------
    #
    # Run with: use-erlang-21-ei
    #
    # This script:
    # - Set PATH to get the specified Erlang version
    # - Ensure that the Erlang man pages are available via the man command:
    #   - Set MANPATH to provide access the Erlang man pages
    #     - If MAN_ONLY_ERLANG environment variable is set, MANPATH
    #       is set to that directory only, otherwise the Erlang man directory
    #       is added in front of the current value of MANPATH.
    # - Set following environment variables:
    #   - DIR_ERLANG_DEV            : where Erlang projects are stored.
    #                                 Also acts as a flag protecting against
    #                                 multiple execution of scripts that
    #                                 set Erlang environment.
    #   - PEL_ERLANG_VERSION        : version of the active Erlang
    #   - PEL_ERLANG_MAN_PARENT_DIR : Absolute path of directory that holds
    #                                 Erlang man/man1 directory.
    #
    #  The PEL environment variables are used by Emacs PEL

    # -----------------------------------------------------------------------------
    # Script
    # ------
    #
    if [ "$DIR_ERLANG_DEV" == "" ]; then
        export DIR_ERLANG_DEV="$HOME/dev/erlang"
        export PEL_ERLANG_MAN_PARENT_DIR="$HOME/docs/Erlang/otp-21.3"
        PATH=$HOME/.erlangInstaller/21.3.8.7/lib/erl_interface-3.11.3/bin:$HOME/.erlangInstaller/21.3.8.7/bin:${PATH}
        export PATH
        if [ "$MAN_ONLY_ERLANG" == "" ]; then
            MANPATH=$PEL_ERLANG_MAN_PARENT_DIR/man:`manpath`
        else
            MANPATH=$PEL_ERLANG_MAN_PARENT_DIR/man
        fi
        if [ -f "$HOME/docs/Erlang/otp-21.3/man/whatis" ]; then
            export PEL_ERLANG_VERSION=21.3.8.7
            export MANPATH
            echo "+ Erlang 21.3.8.7 (from Erlang Solutions' Erlang Installer) environment set."
            echo "+ Using OTP-21.3 Man pages."
            settitle "Erlang 21.3.8.7 EI"
        else
            echo "Error: missing: $HOME/docs/Erlang/otp-21.3/man/whatis"
            echo "Execute make-local-whatis $HOME/docs/Erlang/otp-21.3/man"
            echo " then try again."
            echo "Reason: The whatis file is needed to use whatis on Erlang man files."
            echo "        Also Emacs uses it for man auto-completion."
            return 1
        fi
    else
        echo "! Erlang environment was already set for this shell: nothing done this time."
    fi

    # -----------------------------------------------------------------------------



For Kerl-based installation
---------------------------

The script is similar for Kerl-based installation, except that the PATH is
controlled by Kerl itself.

Here's a copy of the envfor-erlang-23-kn:

.. code:: bash

    # Sourced script: envfor-erlang-23-kn  -*- mode: sh; -*-
    #
    # Purpose   : Install Erlang 23.0.2 (built with Kerl/Native clang)
    # Created   : Tuesday, May 18 2021.
    # Author    : Pierre Rouleau <prouleau001@gmail.com>
    # Time-stamp: <2021-06-04 15:44:17, updated by Pierre Rouleau>
    # Copyright © 2021, Pierre Rouleau
    # License   : MIT
    # ----------------------------------------------------------------------------
    # Description
    # -----------
    #
    #   Run with: use-erlang-23-kn
    #
    #
    #   It uses 'Kerl activate' to install Erlang 23.0.2
    #
    # This script:
    # - Set PATH to get the specified Erlang version (via kerl)
    # - Ensure that the Erlang man pages are available via the man command:
    #   - Set MANPATH to provide access the Erlang man pages
    #     - If MAN_ONLY_ERLANG environment variable is set, MANPATH
    #       is set to that directory only, otherwise the Erlang man directory
    #       is added in front of the current value of MANPATH.
    # - Set following environment variables:
    #   - DIR_ERLANG_DEV            : where Erlang projects are stored.
    #                                 Also acts as a flag protecting against
    #                                 multiple execution of scripts that
    #                                 set Erlang environment.
    #   - PEL_ERLANG_VERSION        : version of the active Erlang
    #   - PEL_ERLANG_MAN_PARENT_DIR : Absolute path of directory that holds
    #                                 Erlang man/man1 directory.
    #
    #  The PEL environment variables are used by Emacs PEL

    # ----------------------------------------------------------------------------
    # Script
    # ------
    #
    if [ "$DIR_ERLANG_DEV" == "" ]; then
        export DIR_ERLANG_DEV="$HOME/dev/erlang"
        export PEL_ERLANG_MAN_PARENT_DIR="$HOME/docs/Erlang/otp-23.0"
        if [ "$MAN_ONLY_ERLANG" == "" ]; then
            MANPATH=$PEL_ERLANG_MAN_PARENT_DIR/man:`manpath`
        else
            MANPATH=$PEL_ERLANG_MAN_PARENT_DIR/man
        fi
        if [ -f "$HOME/docs/Erlang/otp-23.0/man/whatis" ]; then
            export PEL_ERLANG_VERSION=23.0.2
            export MANPATH
            echo "+ Erlang 23.0.2 (built with Kerl/native Clang) environment set."
            echo "+ Using OTP-23 Man pages."
            echo "Use kerl_deactivate to deactivate it."
            settitle "Erlang 23.0.2 Kerl/Native"
            source ~/bin/erls/23.0.2/activate
        else
            echo "Error: missing: $HOME/docs/Erlang/otp-23.0/man/whatis"
            echo "Execute make-local-whatis $HOME/docs/Erlang/otp-23.0/man"
            echo " then try again."
            echo "Reason: The whatis file is needed to use whatis on Erlang man files."
            echo "        Also Emacs uses it for man auto-completion."
            return 1
        fi
    else
        echo "! Erlang environment was already set for this shell."
    fi

    # -----------------------------------------------------------------------------



For asdf-vm based installation
------------------------------

The asdf-vm tools controls the environment.  Once it has been setup with this
script, it's possible to use other asdf-vm commands to modify the environment
further.

Here's the copy of envfor-erlang-23-a:

.. code:: bash

    # Sourced script: envfor-erlang-23-a  -*- mode: sh; -*-
    #
    # Purpose   : Install Erlang 23.0.2 (built with asdf/native Clang)
    # Created   : Tuesday, May 18 2021.
    # Author    : Pierre Rouleau <prouleau001@gmail.com>
    # Time-stamp: <2021-06-04 16:00:01, updated by Pierre Rouleau>
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
    # - Set PATH to get the specified Erlang version (via asdf-vm)
    # - Ensure that the Erlang man pages are available via the man command:
    #   - Set MANPATH to provide access the Erlang man pages
    #     - If MAN_ONLY_ERLANG environment variable is set, MANPATH
    #       is set to that directory only, otherwise the Erlang man directory
    #       is added in front of the current value of MANPATH.
    # - Set following environment variables:
    #   - DIR_ERLANG_DEV            : where Erlang projects are stored.
    #                                 Also acts as a flag protecting against
    #                                 multiple execution of scripts that
    #                                 set Erlang environment.
    #   - PEL_ERLANG_VERSION        : version of the active Erlang
    #   - PEL_ERLANG_MAN_PARENT_DIR : Absolute path of directory that holds
    #                                 Erlang man/man1 directory.
    #
    #  The PEL environment variables are used by Emacs PEL

    # ----------------------------------------------------------------------------
    # Script
    # ------
    #
    if [ "$DIR_ERLANG_DEV" == "" ]; then
        export DIR_ERLANG_DEV="$HOME/dev/erlang"
        export PEL_ERLANG_MAN_PARENT_DIR="$HOME/docs/Erlang/otp-23.0"
        if [ "$MAN_ONLY_ERLANG" == "" ]; then
            MANPATH=$PEL_ERLANG_MAN_PARENT_DIR/man:`manpath`
        else
            MANPATH=$PEL_ERLANG_MAN_PARENT_DIR/man
        fi
        if [ -f "$PEL_ERLANG_MAN_PARENT_DIR/man/whatis" ]; then
            export PEL_ERLANG_VERSION=23.0.2
            export MANPATH
            echo "+ Erlang 23.0.2 (built with asdf-vm/native Clang) environment set."
            echo "+ Using OTP-23.0 Man pages."
            echo "Note: asdf is leaving a .tool-version in the current directory!"
            use-asdf
            asdf local erlang 23.0.2
            settitle "Erlang 23.0.2 asdf/Native"
        else
            echo "Error: missing: $HOME/docs/Erlang/otp-23.0/man/whatis"
            echo "Execute make-local-whatis $HOME/docs/Erlang/otp-23.0/man"
            echo " then try again."
            echo "Reason: The whatis file is needed to use whatis on Erlang man files."
            echo "        Also Emacs uses it for man auto-completion."
            return 1
        fi
    else
        echo "! Erlang environment was already set for this shell."
    fi

    # -----------------------------------------------------------------------------


.. _manpath: https://man7.org/linux/man-pages/man5/manpath.5.html
.. _Installing Erlang: installing-erlang.rst
.. _make-local-whatis script: whatis-files.rst#the-make-local-whatis-script
.. _whatis files for Erlang:  whatis-files.rst#the-whatis-utility
.. _settitle script:          settitle.rst



.. ---------------------------------------------------------------------------

..
       Local Variables:
       time-stamp-line-limit: 10
       time-stamp-start: "^:Modified:[ \t]+\\\\?"
       time-stamp-end:   "\\.$"
       End:
