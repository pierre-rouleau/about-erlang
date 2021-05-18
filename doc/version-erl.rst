========================================================
The version-erl script: print Erlang's version on stdout
========================================================

:Home page: https://github.com/pierre-rouleau/about-erlang
:Time-stamp: <2021-05-18 17:13:46, updated by Pierre Rouleau>
:Copyright:  Copyright © 2020, 2021, Pierre Rouleau
:License: `MIT <../LICENSE>`_

.. contents::  **Table of Contents**
.. sectnum::

.. ---------------------------------------------------------------------------

The version-erl executable script
=================================

The following shell script uses the Erlang shell command line to print
Erlang's version information on the command line.

.. code:: bash

    #!/bin/sh
    # SH FILE: version-erl
    #
    # Purpose   : Print version of currently available Erlang on stdout.
    # Created   : Monday, May 11 2020.
    # Author    : Pierre Rouleau <prouleau001@gmail.com>
    # Time-stamp: <2021-05-18 17:13:11, updated by Pierre Rouleau>
    # Copyright © 2020, 2021, Pierre Rouleau
    # License   : MIT
    # ----------------------------------------------------------------------------
    # Description
    # -----------
    #
    # Usage:  version-erl
    #
    #  This uses an inline Erlang statement passed to the Erlang interpreter.

    # ----------------------------------------------------------------------------
    # Script
    # ------
    #
    erl -eval '{ok, Version} = file:read_file(filename:join([code:root_dir(), "releases", erlang:system_info(otp_release), "OTP_VERSION"])), io:fwrite(Version), halt().' -noshell
    # -----------------------------------------------------------------------------


.. ---------------------------------------------------------------------------
