==========================
The ~/.erlang startup file
==========================

:Home page: https://github.com/pierre-rouleau/about-erlang
:Navigation: Prev_, Top_
:Created:  Monday, June  7 2021.
:Author:  Pierre Rouleau <prouleau001@gmail.com>
:Modified: 2021-06-07 15:57:00, updated by Pierre Rouleau.
:Copyright: © 2021, Pierre Rouleau

.. _Prev:  editing-erlang-with-pel.rst
.. _Top:   installing-erlang.rst


.. contents::  **Table of Contents**
.. sectnum::

.. ---------------------------------------------------------------------------

The ~/.erlang file
==================

As described in the `erl configuration man page`_, when Erlang/OTP is started
it searches for the file ``.erlang`` in the user's home directory and
evaluates its content as Erlang expressions if it finds one.

You can start several configuration settings inside that file or put logic to
detect the current project and apply a configuration that is required for the
current project.

You can also compile and load the content of other files.  A file often used
by Erlang users is a **user-default** file that is generic and applies to all
projects.

Here's an example for the content of a ``.erlang file``:

.. code:: erlang

    %%% File      : .erlang
    %%% Purpose   : Erlang Shell Configuration.
    %%% Created   : Monday, June  7 2021.
    %%% Author    : Pierre Rouleau <prouleau001@gmail.com>
    %%% Time-stamp: <2021-06-07 14:24:09, updated by Pierre Rouleau>
    %%% Copyright © 2021, Pierre Rouleau
    %%% License   : MIT
    %%% ------------------------------------------------------------------------------------------------
    %%% Header Description: Erlang Shell Configuration.
    %%%
    %%%
    %%% References:
    %%% - http://erlang.org/doc/man/erl.html#configuration
    %%%
    %%% ================================================================================================
    io:format("Executing user profile in ~~/.erlang\n", []).
    UD = filename:absname_join(os:getenv("HOME"), "dev/erlang/base/user_default.erl").
    shell_default:c(UD).
    io:format("Completed ~~/.erlang\n", []).
    %%% ------------------------------------------------------------------------------------------------

A User Default File
===================

As described by `this Pluralsight article`_, you can create extra commands to use
inside the Erlang shell.  Like ``cmd`` to execute a shell utility command,
shown below:

.. code:: erlang

    -module(user_default).
    -export([cmd/1]).


    cmd(Cmd) ->
       io:format("~s~n", [os:cmd(Cmd)]).

Centralizing all Erlang Configuration Files in a DVCS repo
==========================================================

Ideally your ``.erlang`` file should be stored in a VCS.  You could create a
Erlang setup specific project under the control of a DVCS like GIT, Mercurial or
any other and store the file in that directory.  Then you create a symlink
inside your home directory to that file.

.. _erl configuration man page: https://erlang.org/doc/man/erl.html#configuration
.. _this Pluralsight article:   https://www.pluralsight.com/guides/10-essential-erlang-tools-for-erlang-developers

.. ---------------------------------------------------------------------------

..
       Local Variables:
       time-stamp-line-limit: 10
       time-stamp-start: "^:Modified:[ \t]+\\\\?"
       time-stamp-end:   "\\.$"
       End:
