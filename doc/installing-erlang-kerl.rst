======================================
Building Erlang From Source Using Kerl
======================================

:Home page: https://github.com/pierre-rouleau/about-erlang
:Time-stamp: <2021-05-15 18:14:46, updated by Pierre Rouleau>
:Copyright:  Copyright © 2020, 2021, Pierre Rouleau
:License: `MIT <../LICENSE>`_

.. contents::  **Table of Contents**
.. sectnum::

.. ---------------------------------------------------------------------------

Using Kerl
==========

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
--------------------------------

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
-------------

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
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

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
---------------------

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

Launching a shell with a Kerl-built Erlang
------------------------------------------

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

.. ---------------------------------------------------------------------------

.. _Kerl: https://github.com/kerl/kerl
.. _XCode: https://developer.apple.com/xcode/
.. _OpenSSL: https://en.wikipedia.org/wiki/OpenSSL
.. _Homebrew: https://brew.sh


.. ---------------------------------------------------------------------------
