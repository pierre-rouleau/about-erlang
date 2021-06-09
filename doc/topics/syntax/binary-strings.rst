=====================
Erlang Binary Strings
=====================

:Home page: https://github.com/pierre-rouleau/about-erlang
:Home URL:
:Project:
:Created:  Tuesday, June  8 2021.
:Author:  Pierre Rouleau <prouleau001@gmail.com>
:Modified: 2021-06-08 22:47:11, updated by Pierre Rouleau.
:Copyright: © 2021, Pierre Rouleau
:License: `MIT <../../../LICENSE>`_


.. contents::  **Table of Contents**
.. sectnum::

.. ---------------------------------------------------------------------------

Bit Syntax
==========

.. code:: erlang

  3> Color = 16#F0E1D2.
  15786450
  4> Pixel = <<Color:24>>.
  <<"ðáÒ">>

This *feature* of printing the data as a string is annoying here.
Fortunately since Erlang/OTP R16B it is possible to prevent erlang from doing
it in all shells with the `shells:strings/1`_ command.

.. code:: erlang

  9> shell:strings(false).
  true
  10> Pixel.
  <<240,225,210>>
  11> X



References
==========


- `Bit Syntax @ LYSEFGG`_
- `Bit-level Binaries and Generalized Comprehensions in Erlang`_, the paper
  defining their specification.



.. References


.. _Bit Syntax @ LYSEFGG: https://learnyousomeerlang.com/starting-out-for-real#bit-syntax
.. _Bit-level Binaries and Generalized Comprehensions in Erlang: http://user.it.uu.se/~pergu/papers/erlang05.pdf
.. _shells\:strings/1: http://erlang.org/doc/man/shell.html#strings-1




.. ---------------------------------------------------------------------------

..
       Local Variables:
       time-stamp-line-limit: 10
       time-stamp-start: "^:Modified:[ \t]+\\\\?"
       time-stamp-end:   "\\.$"
       End:
