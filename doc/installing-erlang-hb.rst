===============================
Installing Erlang with Homebrew
===============================

:Home page:
:Time-stamp: <2021-05-14 18:27:38, updated by Pierre Rouleau>
:Copyright:  Copyright © 2021, Pierre Rouleau
:License:

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
  erlang`` command though.  See `Homebrew FAQ`_.


.. ---------------------------------------------------------------------------
