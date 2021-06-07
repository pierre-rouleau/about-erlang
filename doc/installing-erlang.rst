=================
Installing Erlang
=================

:Home page: https://github.com/pierre-rouleau/about-erlang
:Navigation: Prev_, Top_, Next_
:Time-stamp: <2021-06-07 14:08:33, updated by Pierre Rouleau>
:Copyright:  Copyright © 2020, 2021, Pierre Rouleau
:License: `MIT <../LICENSE>`_

.. _Prev:  learning-erlang.rst
.. _Top:   https://github.com/pierre-rouleau/about-erlang
.. _Next:  editing-erlang.rst

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
#. `Using asdf-vm`_ to build from source.  asdf-vm extends Kerl and provides
   the ability to build lots of other tools, Elixir for instance.
   At the moment (and from what I currently know) this seems to be a very good
   choice because you can install Erlang but also Elixir and several other
   tools with it.
#. Building from source using the Erlang/OTP instructions found in
   the `Erlang/OTP Build and Install instructions`_. I have not yet gone
   through the entire process yet. Once I do I will provide more information.

You will probably want to use Erlang man pages when developing code.
See the following sections:

- `Manual installation of Erlang OTP Documentation and Man Files`_
  to get a local copy of Erlang HTML documentation and Erlang Man pages,
- `Creating whatis files for Erlang man pages`_ to understand the purpose
  of the whatis utility and its impact on the Erlang man pages, and
- `Using Erlang Man files within Emacs`_ to get the best of Erlang when using Emacs.
- `Using Specialized OS Shells for Erlang`_, to use several versions of Erlang
  simultaneously.
- `Using PEL with Specialized Shells for Erlang to Edit Erlang`_.

The next step is to setup files that are important when using Erlang.
These files are described in the following sections.

- The ~/.erlang startup file


Some extra information specific to macOS is available of my `macOS Development Environment`_ document.

If you are not familiar with Emacs and would like to learn about it, you may
be interested by my Emacs customization and document project, PEL_ and the
Erlang specific document `Developing Erlang with PEL`_.

.. _Erlang/OTP Build and Install instructions: https://github.com/erlang/otp/blob/master/HOWTO/INSTALL.md
.. _Installing Erlang on macOS: https://github.com/pierre-rouleau/about-macOS/blob/master/doc/macos-env.rst#environment-for-erlang
.. _Erlang OTP Download page:   https://www.erlang.org/downloads
.. _macOS Development Environment: https://github.com/pierre-rouleau/about-macOS/blob/master/doc/macos-env.rst

.. _Using Homebrew:                                installing-erlang-hb.rst
.. _Using Erlang Installer from Erlang Solutions:  installing-erlang-ei.rst
.. _Using Kerl:                                    installing-erlang-kerl.rst
.. _Using asdf-vm:                                 installing-erlang-asdf.rst
.. _Using Specialized OS Shells for Erlang:        specialized-shells.rst
.. _Using PEL with Specialized Shells for Erlang to Edit Erlang: editing-erlang-with-pel.rst

.. _Manual installation of Erlang OTP Documentation and Man Files: installing-erlang-man-files.rst
.. _Creating whatis files for Erlang man pages:  whatis-files.rst
.. _Using Erlang Man files within Emacs:         erlang-man-with-emacs.rst
.. _PEL:                                         https://github.com/pierre-rouleau/pel#readme
.. _Developing Erlang with PEL: https://github.com/pierre-rouleau/pel/blob/master/doc/developing-erlang.rst



---------------------------------------------------------------------------
