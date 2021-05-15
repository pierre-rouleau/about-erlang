===============================
Set macOS Terminal window title
===============================

:Home page: https://github.com/pierre-rouleau/about-erlang
:Time-stamp: <2021-05-15 16:15:20, updated by Pierre Rouleau>
:Copyright:  Copyright © 2021, Pierre Rouleau
:License: `MIT <../LICENSE>`_


.. contents::  **Table of Contents**
.. sectnum::

.. ---------------------------------------------------------------------------

The following script can be used under macOS to change the title of a terminal
window.


.. code:: shell

    #!/bin/sh
    # Abstract: Set the title of the current Terminal window.
    # Usage: settitle {the new title withing double quotes if more than 1 word}
    echo "\033]0;${1}\007\c"


Credits:  `Alvin Alexander blog`_.


.. _Alvin Alexander blog: https://alvinalexander.com/blog/post/mac-os-x/change-title-bar-of-mac-os-x-terminal-window/





.. ---------------------------------------------------------------------------
