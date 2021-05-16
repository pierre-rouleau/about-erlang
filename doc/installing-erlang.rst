=================
Installing Erlang
=================

:Home page: https://github.com/pierre-rouleau/about-erlang
:Time-stamp: <2021-05-15 18:11:49, updated by Pierre Rouleau>
:Copyright:  Copyright © 2020, 2021, Pierre Rouleau
:License: `MIT <../LICENSE>`_

.. contents::  **Table of Contents**
.. sectnum::

.. ---------------------------------------------------------------------------

Erlang can be installed from source or from pre-built packages.

Instruction on how to install Erlang depends on the Operating System and are
available on the `Erlang OTP Download page`_.  Another good source of
information is available in the `setup section of the Adopting Erlang`_ web site.

The following section describes the various ways to install Erlang on macOS.


.. _setup section of the Adopting Erlang: https://adoptingerlang.org/docs/development/setup/

Installing Erlang on macOS
==========================

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


Also, see the section titled
`Manual installation of Erlang OTP Documentation and Man Files`_
to get a local copy of Erlang HTML documentation and Erlang Man pages.

Some extra information specific to macOS is available of my `macOS Development Environment`_ document.

.. _Erlang/OTP Build and Install instructions: https://github.com/erlang/otp/blob/master/HOWTO/INSTALL.md
.. _Installing Erlang on macOS: https://github.com/pierre-rouleau/about-macOS/blob/master/doc/macos-env.rst#environment-for-erlang
.. _Erlang OTP Download page:   https://www.erlang.org/downloads
.. _macOS Development Environment: https://github.com/pierre-rouleau/about-macOS/blob/master/doc/macos-env.rst

Using Homebrew
--------------

See `Installing Erlang with Homebrew`_



.. _Installing Erlang with Homebrew: installing-erlang-hb.rst
.. _Install Erlang Using Erlang Installer from Erlang Solutions: installing-erlang-ei.rst
.. _Install Erlang OTP Documentation and Man Files: installing-erlang-man-files.rst
.. _Building Erlang From Source Using Kerl: installing-erlang-kerl.rst



Using Erlang Installer from Erlang Solutions
--------------------------------------------

See `Install Erlang Using Erlang Installer from Erlang Solutions`_.


Manual installation of Erlang OTP Documentation and Man Files
-------------------------------------------------------------

See `Install Erlang OTP Documentation and Man Files`_.


Using Kerl
----------

See `Building Erlang From Source Using Kerl`_


..
   -----------------------------------------------------------------------------


Using asdf-vm
-------------

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
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

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
~~~~~~~~~~~~~

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
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

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
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

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
~~~~~~~~~~~~~~~~~~~~~

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
-----------------------------------




Erlang Man files to use with Emacs
----------------------------------

Emacs support for Erlang uses the Erlang man files.  Several packages uses the
Erlang man page files and they may install them in different location.
This section describes where various Emacs packages for Erlang support
install the man pages and how to consolidate them into one location.


Used by the standard Erlang mode (erlang.el)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

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
~~~~~~~~~~~~

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
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

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


---------------------------------------------------------------------------
