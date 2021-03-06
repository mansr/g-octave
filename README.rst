.. _`GNU Octave`: http://octave.org/
.. _`Octave-Forge`: http://octave.sf.net/
.. _`g-octave`: http://www.g-octave.org/
.. _Python: http://python.org/
.. _Portage: http://www.gentoo.org/proj/en/portage/ 
.. _Paludis: http://paludis.pioto.org/
.. _pkgcore: http://www.pkgcore.org/
.. _`Gentoo Linux`: http://www.gentoo.org/
.. _`issue tracker`: https://github.com/rafaelmartins/g-octave/issues
.. _Git: http://git-scm.com/
.. _PySVN: http://pysvn.tigris.org/

g-octave
========

Introduction
------------

What is GNU Octave?
~~~~~~~~~~~~~~~~~~~

`GNU Octave`_ is a high-level language, primarily intended for numerical
computations. It provides a convenient command line interface for solving
linear and nonlinear problems numerically, and for performing other numerical
experiments using a language that is mostly compatible with Matlab.
It may also be used as a batch-oriented language.


What is Octave Forge?
~~~~~~~~~~~~~~~~~~~~~

`Octave-Forge`_ is a central location for the collaborative development of
packages for `GNU Octave`_.

The `Octave-Forge`_ packages contains the source for all the functions and
are designed to work with the `GNU Octave`_ package system. 


What is g-octave
~~~~~~~~~~~~~~~~

`g-octave`_ is a tool that generates and installs ebuilds for `Octave-Forge`_
packages "on-the-fly" to `Gentoo Linux`_, using Portage_, Paludis_ or pkgcore_.
It's capable to generate ebuilds and Manifest files (if needed)
for the packages, and to install them using an autogenerated overlay (named
g-octave). `g-octave`_ can also handle patches to the packages automatically.
The command line interface tries to be very similar to the interface of the
**emerge** tool.


Dependencies
------------

`g-octave`_ have some basic dependencies:

* Python_ >= 2.6
* Portage_
* Paludis_ (optional)
* pkgcore_ (optional)

Settings
--------

All the settings are centralized on the file */etc/g-octave.cfg*. Please
read the comments and change what you need. The recommendation is to keep
everything as it is. :)

You can also use environment variables to configure `g-octave`.

http://docs.g-octave.org/en/latest/userguide/#configuring-g-octave


Configuring your package manager
--------------------------------

http://docs.g-octave.org/en/latest/userguide/#configuring-g-octave


CLI options
-----------

*--version*
    show program's version number and exit

*-h, --help*
    show this help message and exit

*-l, --list*
    show a list of packages available to install and exit

*-i, --info*
    show a description of the required package and exit

*-p, --pretend*
    don't (un)merge packages, only create ebuilds and solve the dependencies

*-a, --ask*
    ask to confirmation before perform (un)merges

*-v, --verbose*
    Portage makes a lot of noise.

*-1, --oneshot*
    do not add the packages to the world file for later updating.

*-u, --update*
    try to update a package or all the installed packages

*-s, --search*
    search for packages with some term on the name (regular expressions allowed)

*-C, --unmerge*
    try to unmerge a package instead of merge

*--scm*
    enable the installation of the current live version of a package, if disabled
    on the configuration file

*--no-scm*
    disable the installation of the current live version of a package, if
    enabled on the configuration file

*-f, --force*
    forces the recreation of the ebuilds

*--force-all*
    forces the recreation of the overlay and of the ebuilds

*--no-colors*
    don't use colors on the CLI

*--sync*
    search for updates of the package database, patches and auxiliary files

*--config*
    return a value from the configuration file (/etc/g-octave.cfg)

*--list-raw*
    show a list of packages available to install (a package per line,
    without colors) and exit


Usage Examples
--------------

Install the latest version of *control*: ::
    
    # g-octave control

Install the version 0.3.1 of *control*: ::

    # g-octave control-0.3.1

Upgrade to latest version available of *control*: ::
    
    # g-octave -u control

Remove the package *control*: ::

    # g-octave -C control

Get informations about the package *control*: ::

    # g-octave -i control

To install the package *control* from the octave-forge SVN repository: ::
    
    # g-octave control-9999
    
The options *verbose*, *ask* and *pretend* are passed to **emerge**.


How can I help?
---------------

The users can help testing and reporting bugs in our `issue tracker`_.
If you can help programming in Python_ you're always welcome. :)

`g-octave`_ ebuilds are available on the Git repository, or the
Gentoo science overlay.


Warning
-------

If you experienced some random errors when installing packages, please
retry, using the option *--force-all*, and report the issue to us.
If you don't want to lose all your ebuilds, you can try to use the option
*--force*, that will re-create only the affected ebuild.


Download Page
-------------

You can get the sources here:
https://github.com/rafaelmartins/g-octave/downloads

or clone the Git_ repository using: ::
    
    $ git clone git://github.com/rafaelmartins/g-octave.git


Authors
-------

Rafael Goncalves Martins *<rafael at rafaelmartins dot eng dot br>*
