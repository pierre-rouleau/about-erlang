========================================================
The version-erl script: print Erlang's version on stdout
========================================================

:Home page: https://github.com/pierre-rouleau/about-erlang
:Time-stamp: <2021-05-15 16:36:07, updated by Pierre Rouleau>
:Copyright:  Copyright © 2021, Pierre Rouleau
:License: `MIT <../LICENSE>`_

.. contents::  **Table of Contents**
.. sectnum::

.. ---------------------------------------------------------------------------

The version-erl executable script
=================================

The following shell script uses the Erlang shell command line to print
Erlang's version information on the command line.

.. code:: bash

    #!/usr/bin/env sh
    # Name:     version-erl
    # Abstract: Print version of currently available Erlang on stdout.
    # Requires: Accessible Erlang binaries: uses erl.
    # Used by : PEL Emacs support for Erlang to auto-detect available Erlang version.
    # Last Modified Time-stamp: <2020-07-22 17:08:27, updated by Pierre Rouleau>
    # -----------------------------------------------------------------------------
    erl -eval '{ok, Version} = file:read_file(filename:join([code:root_dir(), "releases", erlang:system_info(otp_release), "OTP_VERSION"])), io:fwrite(Version), halt().' -noshell
    # -----------------------------------------------------------------------------



.. ---------------------------------------------------------------------------
