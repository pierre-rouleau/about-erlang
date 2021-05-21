================
Tools for Erlang
================

:Home page: https://github.com/pierre-rouleau/about-erlang
:Time-stamp: <2021-05-21 16:32:57, updated by Pierre Rouleau>
:Copyright:  Copyright © 2021, Pierre Rouleau
:License: `MIT <../LICENSE>`_

          There are an increasing number of tools available for Erlang development.
Some of them are listed in this page.
These include the `built-in Erlang tools`_ that are part of the Erlang system
itself, and other tools provided by the community.

🚧 This page is under_ construction.  I will add  info about several other
tools soon. 🚧


.. _built-in Erlang tools:  https://erlang.org/doc/apps/tools/index.html


.. contents::  **Table of Contents**
.. sectnum::


---------------------------------------------------------------------------

Erlang Build Tools
==================


rebar3
------

For Erlang projects you must use this tool.  It's used in Erlang but also
other BEAM-based languages.  It is used for several tasks and controls the
build of Erlang projects.

See:

- `rebar3 @ GitHub`_
- `rebar home page`_   (you can download a copy of rebar from this page),
- `rebar3 documentation`_
- `rebar3 tutorials`_

To start from the beginning, read `rebar3 Getting Started`_


.. _rebar3 tutorials:         https://rebar3.org/docs/tutorials/
.. _rebar3 documentation:     https://rebar3.org/docs/
.. _rebar3 @ GitHub:          https://github.com/erlang/rebar3
.. _rebar3 Getting Started:   https://rebar3.org/docs/getting-started/
.. _rebar home page:          https://rebar3.org



.. ---------------------------------------------------------------------------


Erlang Code Style Checkers & Formatters
=======================================

elvis - the Erlang Style Reviewer
---------------------------------

See:

- `elvis @ Github`_
- `elvis video presentation by Inaka and Erlang Solutions on Youtube`_

To use elvis, start by creating a git clone the `elvis Github repo`_ on your
computer. Then follow the instructions listed in the repo Readme file which
essentially consist of running the following commands inside your elvis
clone directory:

- ``rebar3 compile``
- ``rebar3 escriptize``

The second command creates an ``elvis`` executable in the ``_build/default/bin``
sub-directory. You can then create a symlink to that file in a directory that
is in your PATH to be able to invoke the elvis command from anywhere.

On my system I use the ``~/bin`` directory for that purpose.

With the above done, you will be able to execute elvis from the command line
like this:

::

    > elvis
    Usage: elvis [-h] [-c <config>] [--commands]
                 [--output-format <output_format>] [-P <parallel>] [-q] [-V]
                 [-v] [-p <code_path>] [-k]

      -h, --help          Show this help information.
      -c, --config        Provide the path to the configuration file. When
                          none is provided elvis checks if there's an
                          elvis.config file.
      --commands          Show available commands.
      --output-format     It allows you to display the results in plain text.
                          When none is provided elvis displays the results in
                          colors. The options allowed are (plain | colors |
                          parsable).
      -P, --parallel      Allows to analyze files concurrently. Provide max
                          number of concurrent workers, or specify "auto" to
                          peek default value based on the number of schedulers.
      -q, --quiet         Suppress all output.
      -V, --verbose       Enable verbose output.
      -v, --version       Output the current elvis version.
      -p, --code-path     Add the directory in the code path.
      -k, --keep-rocking  Won't stop rocking on first error when given a list
                          of files


    > elvis --commands
    Elvis will do the following things for you when asked nicely:

    rock [file...]   Rock your socks off by running all rules to your source files.

    git-hook         Pre-commit Git Hook: Gets all staged files and runs the rules
                                          specified in the configuration to those
                                          files.

    git-branch [branch|commit]
                     Rock your socks off by running all rules on source files that
                     have changed since branch or commit.

    install git-hook
                    Installs Elvis as a pre-commit hook in your current working
                    directory, which should be a git repository.
    >

Next you will have to configure elvis.  See Elvis repo documentation for that.

.. _elvis Github repo:
.. _elvis @ Github: https://github.com/inaka/elvis
.. _elvis video presentation by Inaka and Erlang Solutions on Youtube: https://www.youtube.com/watch?v=Q88hGUJUwHs


rebar3 format
-------------



.. ---------------------------------------------------------------------------

Erlang Code Analysis Tools
==========================


xref
----

The xref tool analyzes dependencies between functions, modules, applications
and releases.

If you use rebar3 to control your project, you can use the ``rebar3 xref``
command to run the xref on the project's code.

You will have to configure xref in the ``rebar.config`` file of the project,
specifying the various `xref settings`_.


See:

- `xref reference @ Erlang.org`_
- `Xref - The Cross Reference Tool @ Erlang.org`_
- `rebar3- configurations for xref`_
- `Removing Erlang dead code with Xref`_.  It describes how to remove unused
  *exported* code from your project.



.. _xref reference @ Erlang.org: https://erlang.org/doc/man/xref.html
.. _Xref - The Cross Reference Tool @ Erlang.org:  https://erlang.org/doc/apps/tools/xref_chapter.html
.. _Removing Erlang dead code with Xref: https://tech.nextroll.com/blog/dev/2018/10/09/remove-erlang-dead-code-xref.html
.. _xref settings:
.. _rebar3 configurations for xref:      https://www.rebar3.org/docs/configuration/configuration/#xref




Use the ignore_xref attribute to mark functions called dynamically
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

You should use the ``ignore_xref`` attribute to identify functions that are
called dynamically and will otherwise be reported as not being called by xref.

For example, if the function some_function/1 is called dynamically and is
exported, then the following code snippet could be used:

.. code:: erlang

      -module(example).
      -exports([some_function/1, some_other_function/1]).

      %% This function should be dynamically invoked through example:some_function/1
      -ignore_xref([{?MODULE, some_other_function, 1}]).

      ...


.. ---------------------------------------------------------------------------
