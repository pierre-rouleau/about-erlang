=======================================
Using the Erlang Man files within Emacs
=======================================

:Home page: https://github.com/pierre-rouleau/about-erlang
:Navigation: Prev_, Top_, Next_
:Time-stamp: <2021-06-04 09:58:04, updated by Pierre Rouleau>
:Copyright:  Copyright © 2020, 2021, Pierre Rouleau
:License: `MIT <../LICENSE>`_

.. _Prev:  whatis-files.rst
.. _Top:   installing-erlang.rst
.. _Next:  specialized-shells.rst

.. contents::  **Table of Contents**
.. sectnum::

.. ---------------------------------------------------------------------------

Erlang Man files to use with Emacs
==================================

Emacs support for Erlang uses the Erlang man files.  Several packages uses the
Erlang man page files and they may install them in different location.
This section describes where various Emacs packages for Erlang support
install the man pages and how to consolidate them into one location.

Consolidating all Erlang Man Files in one location
==================================================

As described in the page titled `Installing Erlang`_ sections, you may install Erlang in
various ways, with the file stored in various locations depending on the
method used to install a specific version of Erlang.

Ideally, there would be a way to work on several projects *concurrently* even
if those projects use different versions of Erlang. Also, ideally, when using
Emacs, you'd want to be able to use the various Emacs tools for Erlang and
ensure they find the man files in their expected locations.

At the same time you'd want to be able to access Erlang Man files from the
shell using the man command and maintain only one copy for each Erlang
version.

If you are using Emacs, you'll notice several Emacs packages that support Erlang.

Man files Used by the standard Erlang mode (erlang.el)
------------------------------------------------------

The `erlang.el`_ package which is part of the `Erlang source code repo`_,
supports one version of Erlang.

By default, it stores the erlang man page files inside the directory
``~/.emacs.d/cache/erlang_mode_man_pages/V`` where ``V`` is the Erlang
version.

For example, this directory holds the following files:

.. code:: ls

        -rw-r--r--  1 roup  staff    16239 17 Sep  2019 COPYRIGHT
        -rw-r--r--  1 roup  staff      842 17 Sep  2019 PR.template
        -rw-r--r--  1 roup  staff     4167 17 Sep  2019 README.md
        -rw-r--r--  1 roup  staff       51 22 Jul 10:32 erlang_man_download_url
        drwxr-xr-x  7 roup  staff      224 17 Sep  2019 man
        -rw-r--r--  1 roup  staff  1355169 22 Jul 07:44 man.tar.gz


Man Files Used by EDTS
----------------------

The EDTS_ external package supports multiple versions of Erlang.
And it has the ability to download the Erlang man files for each of them
and store them in a directory specific to that version of Erlang.

The EDTS_ package stores the Erlang man page files inside the directory
``~/.emacs.d/edts/doc/VV`` where ``VV`` is the Erlang version.  There can be
several ``VV`` directories, one per Erlang version supported.

For example, EDTS_ would store the files for Erlang version 23.0 inside
``~/.emacs.d/edts/doc/23.0``.  The directory it creates would hold:

.. code:: ls

        -rw-r--r--   1 roup  staff  16239 12 May 17:41 COPYRIGHT
        -rw-r--r--   1 roup  staff    842 12 May 17:41 PR.template
        -rw-r--r--   1 roup  staff   4167 12 May 17:41 README.md
        drwxr-xr-x   7 roup  staff    224 12 May 17:30 man


A Consolidation Strategy
------------------------

You may also have downloaded the Erlang man pages somewhere else
because you downloaded the entire Erlang source package and built Erlang
yourself, or because you are using an pre-built version of Erlang or for
whatever reason.

One way to consolidate all of that is to use symbolic links.  What I did is
to place symlinks inside the ``~/.emacs.d/edts/doc`` directory to the
locations of the Erlang man files.
As described `here <installing-erlang-man-files.rst>`_,
I stored all Erlang documentation files
inside the ``~/docs/Erlang`` directory along with the entire documentation
tree of a each specific Erlang versions I am interested in.

For example, the man files for Erlang 17.5 are stored inside
the directory ``~/docs/Erlang/otp-17.5/man``.  Here's a partial tree view
of the directory tree (with several lines removed for clarity):

.. code:: shell
    > tree -L 2 ~/docs/Erlang/otp-17.5
    /Users/roup/docs/Erlang/otp-17.5
    otp-17.5
    ├── COPYRIGHT
    ├── PR.template
    ├── README
    ├── doc
    │   ├── applications.html
    │   ├── design_principles
    │   ├── docbuild
    ...
    │   ├── programming_examples
    │   ├── reference_manual
    │   ├── system_architecture_intro
    │   ├── system_principles
    │   └── tutorial
    ├── erlang_man_download_url
    ├── erts-6.4
    │   ├── doc
    │   └── info
    ├── lib
    │   ├── asn1-3.0.4
    │   ├── common_test-1.10
    │   ├── compiler-5.0.4
    ...
    │   └── xmerl-1.3.7
    ├── man
    │   ├── man1
    │   ├── man3
    │   ├── man4
    │   ├── man6
    │   ├── man7
    │   └── whatis
    └── readme.txt

    75 directories, 13 files
    >


Notice the ``erlang_man_download_url`` file.  This is a file created and used
by EDTS_. It contains the URL where the man files can be downloaded.  The
file contains the following single line of text::

  https://erlang.org/download/otp_doc_man_17.5.tar.gz

Also notice the ``whatis`` file in the ``man`` directory.  I created that file
using the method explained in `Creating whatis files for Erlang man pages`_ to allow
me to restrict the man pages to Erlang only and take advantage of Emacs
completion using the Emacs man command.

Then I created the symlinks in the ``~/.emacs.d/edts/doc`` directory:

.. code:: shell


    > cd ~/.emacs.d/edts/doc
    > ln -s  ~/docs/Erlang/otp-23.3/man  23.3
    > ln -s  ~/docs/Erlang/otp-23.0/man  23.0
    > ln -s  ~/docs/Erlang/otp-22.3/man  22.3
    > ln -s  ~/docs/Erlang/otp-22.2/man  22.2
    > ln -s  ~/docs/Erlang/otp-21.3/man  21.3
    > ln -s  ~/docs/Erlang/otp-20.3/man  20.3
    > ln -s  ~/docs/Erlang/otp-19.3/man  19.3
    > ln -s  ~/docs/Erlang/otp-18.3/man  18.3
    > ln -s  ~/docs/Erlang/otp-17.5/man  17.5
    >
    > ls -l
    total 0
    lrwxr-xr-x  1 roup  staff  36 22 Jul  2020 17.5 -> /Users/roup/docs/Erlang/otp-17.5/man
    lrwxr-xr-x  1 roup  staff  36 22 Jul  2020 18.3 -> /Users/roup/docs/Erlang/otp-18.3/man
    lrwxr-xr-x  1 roup  staff  36 22 Jul  2020 19.3 -> /Users/roup/docs/Erlang/otp-19.3/man
    lrwxr-xr-x  1 roup  staff  36 22 Jul  2020 20.3 -> /Users/roup/docs/Erlang/otp-20.3/man
    lrwxr-xr-x  1 roup  staff  36 22 Jul  2020 21.3 -> /Users/roup/docs/Erlang/otp-21.3/man
    lrwxr-xr-x  1 roup  staff  36 22 Jul  2020 22.2 -> /Users/roup/docs/Erlang/otp-22.2/man
    lrwxr-xr-x  1 roup  staff  36 22 Jul  2020 22.3 -> /Users/roup/docs/Erlang/otp-22.3/man
    lrwxr-xr-x  1 roup  staff  36  3 Jun 14:52 23.0 -> /Users/roup/docs/Erlang/otp-23.0/man
    lrwxr-xr-x  1 roup  staff  36  3 Jun 15:02 23.3 -> /Users/roup/docs/Erlang/otp-23.3/man
    >

..


   And then I create a symlink inside ``~/.emacs.d/cache`` called
   ``erlang_mode_man_pages`` to the location of the directory holding the man
   pages of the default Erlang version for the shell.

   Ideally that should be all controlled from the version of Erlang used in the
   shell or in the project.   The EDTS_ package does some of this.  I'm planning
   to wrap this all up with code controlled by my Emacs PEL system. But this is
   still work in progress at the moment.


.. _Installing Erlang: installing-erlang.rst
.. _erlang.el:  https://github.com/erlang/otp/blob/maint/lib/tools/emacs/erlang.el
.. _edts:  https://github.com/sebastiw/edts#readme
.. _Creating whatis files for Erlang man pages:  whatis-files.rst
.. _Erlang source code repo: https://github.com/erlang/otp
.. _erlang.el:  https://github.com/erlang/otp/blob/maint/lib/tools/emacs/erlang.el

.. ---------------------------------------------------------------------------
