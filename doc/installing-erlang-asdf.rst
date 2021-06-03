======================================================
Build, Install and Manage Erlang Versions with asdf-vm
======================================================

:Home page: https://github.com/pierre-rouleau/about-erlang
:Navigation: Prev_, Top_
:Time-stamp: <2021-06-03 13:15:03, updated by Pierre Rouleau>
:Copyright:  Copyright © 2020, 2021, Pierre Rouleau
:License: `MIT <../LICENSE>`_

.. _Prev:  installing-erlang-ei.rst
.. _Top:   installing-erlang.rst

This page describes the installation of Erlang on macOS using the `asdf-vm`_
tool.  You may also be interested by this post by AJ Foster:
`Installing Elixir and Erlang With ASDF`_.

.. _Installing Elixir and Erlang With ASDF: https://www.pluralsight.com/guides/installing-elixir-erlang-with-asdf


.. contents::  **Table of Contents**
.. sectnum::

.. ---------------------------------------------------------------------------


Installing asdf-vm
==================

Follow on of the `asdf installation methods described in the asdf-vm installation instructions`_.

On macOS, I have used the method using Homebrew.


.. _asdf installation methods described in the asdf-vm installation instructions: https://asdf-vm.com/#/core-manage-asdf?id=install


Using asdf-vm
=============

With the asdf-vm_ tool, you can "*manage multiple runtime versions with a
single CLI tool*" (as written on the asdf-vm_ site).
You can build, install and activate multiple versions of
Erlang as well as a lot of other things like Elixir and other un-related
programming languages and tools.

To asdf-vm, Erlang, like Elixir and Python is a *plugin*. The concept of
*plugin* here applies to a programming language, or a specific tool. They are
considered at the same level.

The asdf tool does everything.  With it you can list the various languages
that you want to use, their versions, and install them on the system very
easily.  When *installing* a version of a tool, it downloads the source code
and perform the complete build.

On my system I did not have to setup the version of OpenSSL to use with
asdf-vm as I had to do with Kerl.  asdf was able to detect the latest version
of OpenSSL I have on my system (as of this writing, version 1.1.1g released
April 21, 2020).

.. _asdf-vm: https://asdf-vm.com/#/
.. _Get and manage asdf itself: https://asdf-vm.com/#/core-manage-asdf
.. _List available plugins, get the ones you need, manage them.: https://asdf-vm.com/#/core-manage-plugins
.. _Get, compile and install a specific version of the plugin.:  https://asdf-vm.com/#/core-manage-versions
.. _identify a current version: https://asdf-vm.com/#/core-manage-versions?id=set-current-version

Setting the Environment for asdf
--------------------------------

For asdf-vm_ I use the same strategy as for the other mechanisms used to install Erlang, I use:

- `The envfor-asdf source script`_ to setup the environment.
- `The use-asdf alias`_ inside by .bashrc file.

With those I can `proceed with the installation`_.


.. _proceed with the installation: `Installation Steps`_



The envfor-asdf source script
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The ``envfor-asdf`` script holds the logic used to set up a shell
for asdf.

The ``envfor-asdf`` script is shown here:

.. code:: bash

    # Sourced script: envfor-asdf  -*- mode: sh; -*-
    #
    # Purpose   : Install asdf, tool to build/manage Erlang, Elixir, etc...
    # Created   : Saturday, May 15 2021.
    # Author    : Pierre Rouleau <prouleau001@gmail.com>
    # Time-stamp: <2021-05-18 11:00:12, updated by Pierre Rouleau>
    # Copyright © 2021, Pierre Rouleau
    # License   : MIT
    # ----------------------------------------------------------------------------
    # Description
    # -----------
    #
    # Run with: use-asdf
    #
    # Note:
    #      This is asdf-vm, not the Common Lisp ASDF tool!
    #
    # References:
    # - Manage asdf-vm          : https://asdf-vm.com/#/core-manage-asdf
    # - Adopting Erlanf - Setup : https://adoptingerlang.org/docs/development/setup/
    #

    # ----------------------------------------------------------------------------
    # Script
    # ------
    if [ "$ROUP_ENVFOR_ASDF" == "" ]; then
        export ROUP_ENVFOR_ASDF=1
        export KERL_BUILD_DOCS=yes
        export KERL_INSTALL_MANPAGES=yes
        export KERL_INSTALL_HTMLDOCS=yes
        . $(brew --prefix asdf)/asdf.sh
        . $(brew --prefix asdf)/etc/bash_completion.d/asdf.bash
        printf "ASDF (asdf-vm) support now installed in this shell.\n"
        printf "ASDF uses "
        $(brew --prefix openssl)/bin/openssl version
        settitle "Using ASDF (asdf-vm)"
    else
        printf "Shell is already setup for ASDF!\n"
        return 1
    fi
    # -----------------------------------------------------------------------------


The use-asdf alias
~~~~~~~~~~~~~~~~~~

The alias in my ``.bashrc`` file is:

.. code:: shell

  alias use-asdf='source envfor-asdf'

Installation Steps
~~~~~~~~~~~~~~~~~~

To install a new version of Erlang using asdf-vm_,  the important steps are:

#. Set the shell for asdf-vm_ by executing the ``use-asdf``.
   This is an alias to the  ``envfor-asdf`` script it sources.
#. `Get and manage asdf itself`_.  These are the instructions to install
   and manage asdf-vm.  You have to do this the very first time and then only
   when you want tu upgrade asdf-vm_ itself.
#. `List available plugins, get the ones you need, manage them.`_  You can
   list all available plugins (such as Erlang) and all versions available for
   this *plugin*.  So you can list all Erlang versions you can build with it.
#. `Get, compile and install a specific version of the plugin.`_  These are
   the commands you use to build and install something like a version of Erlang.


Once this is all done and you have compiled and installed one or several
versions of a given *plugin* (such as Erlang)  it's possible to `identify a current version`_ of a given
plugin to be used globally (it persists).  You can also use a command to
activate that version just for the current shell.

On my system I use the mechanism that activates a specific version of Erlang
for the shell using the same mechanism as I do for the other 3 ways of dealing
with Erlang: a ``use-erlang-xx-a`` alias defined in the ``.bashrc`` file to a
shell script it sources.  The shell script has a name like
``envfor-erlang-xx-a``.  The ``xx`` is Erlang version number and the ``-a``
suffix identifies thet asdf-vm toolchain.


asdf commands
-------------

The asdf commands must be installed in the shell.  For that I execute my
``use-asdf`` (the alias to source my ``envfor-asdf`` script).
Once that is done, I can use all asdf commands to:

- `update asdf-vm`_
- `manage asdf plugins`_
- `manage asdf plugins versions`_ (eg. build and install new versions of Erlang).

More information is available on the asdf-vm_ site.


.. _update asdf-vm: https://asdf-vm.com/#/core-manage-asdf?id=update
.. _manage asdf plugins: https://asdf-vm.com/#/core-manage-plugins
.. _manage asdf plugins versions: https://asdf-vm.com/#/core-manage-versions




Example: Building Erlang 22.3.4.2
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

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

The asdf-vm_ can identify a version of each *plugin* as being the global
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
------------------------------

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

          # Sourced script: envfor-erlang-23-a  -*- mode: sh; -*-
          #
          # Purpose   : Install Erlang 23.0.2 (built with asdf/native Clang)
          # Created   : Tuesday, May 18 2021.
          # Author    : Pierre Rouleau <prouleau001@gmail.com>
          # Time-stamp: <2021-05-18 11:17:05, updated by Pierre Rouleau>
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
                  MANPATH=$HOME/docs/Erlang/otp-23.0/man/man:`manpath`
              else
                  MANPATH=$HOME/docs/Erlang/otp-23.0/man/man
              fi
              if [ -f "$HOME/docs/Erlang/otp-23.0/man/man/whatis" ]; then
                  export PEL_ERLANG_VERSION=23.0.2
                  export MANPATH
                  echo "+ Erlang 23.0.2 (built with asdf-vm/native Clang) environment set."
                  echo "+ Using OTP-23 Man pages."
                  echo "Note: asdf is leaving a .tool-version in the current directory!"
                  use-asdf
                  asdf local erlang 23.0.2
                  settitle "Erlang 23.0.2 asdf/Native"
              else
                  echo "Error: missing: $HOME/docs/Erlang/otp-23.0/man/man"
                  echo "Execute make-local-whatis $HOME/docs/Erlang/otp-23.0/man/man"
                  echo " then try again."
                  echo "The whatis file is needed to use whatis on Erlang man files."
                  echo "Also Emacs uses it for man auto-completion."
                  return 1
              fi

          else
              echo "! Erlang environment was already set for this shell."
          fi

          # -----------------------------------------------------------------------------



And here's a session using it to install Erlang 23.0.2:

.. code:: shell

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
stored in the current directory.

  ⚠️   **asdf is sensitive to the current directory where the erl command is issued**.

Unlike the other tools (Erlang Solutions' Erlang Installer, Kerl-built
versions), **you cannot use the same directory in 2 different shells and launch
2 different versions of Erlang, one in each shell**.

- It's possible to run multiple versions of Erlang at the same time, but they
  must each be instantiated from a shell that has a different current directory.
- With asdf  if you open 2 shells and execute ``use-erlang-23-a`` in the
  first shell and then inside another shell execute ``use-erlang22-a`` in that
  other shells, **from the same directory** both shells will now use the Erlang set up by
  ``use-erlang-22-a`` because they both use the same shim file identified by the
  same ``.tool-version`` file.



asdf Directory Layout
---------------------

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


.. ---------------------------------------------------------------------------
