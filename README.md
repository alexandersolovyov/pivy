Installation from native Debian's repo's
---------------------------

For Debian-like distros - Ubuntu for example - You maybe don't want to build
from source. In that case pivy can be installed from native repositories
as *python-pivy* (for Python3):

```bash
sudo apt-get install python-pivy
```

The package for Python2 may be called *python2.7-pivy* or *python2-pivy*.

General build instructions:
---------------------------
[![Build Status](https://travis-ci.org/Coin3D/pivy.svg?branch=master)](https://travis-ci.org/Coin3D/pivy)

### Needed libraries

Installation requires development libraries for *coin*, and also (optianally)
*soqt* and *simvoleon*. Simvoleon package name may be littlebit confusing. So,
in Mandriva-like Linux distros like Rosa Linux, install:

```bash
sudo urpmi libcoin-devel
sudo urpmi libsoqt-devel

```

Then check the name of *simvoleon*:

```bash
urpmq -y simvoleon
```

For example, it may return two names: *libsimvoleon40* and *libsimvoleon40-devel*.
So, if library name is same for You, install:

```bash
sudo urpmi libsimvoleon40-devel
```

To build pivy You will also need swig. Install it like that:

```bash
sudo urpmi swig
```

### General installation

Pivy uses [distutils][0]. To build Pivy in most Linux distributions, run

```bash
  $ python3 setup.py build
  $ python3 setup.py install
```

**WARNING:** This command works only if Your installation of libraries *coin*,
*soqt* and *simvoleon*, containing cmake config files. Rosa Linux and some
odher Mandriva-based distributions they *does NOT* contain that files, so needed
libraries will not be found at start of build!
For systems, on which cmake config files are absent, use *setup_old.py* instead:

```bash
  $ python3 setup_old.py build
  $ python3 setup_old.py install
```

You may build it for python 2 by calling *python* instead of *python3*.

Reporting bugs:
--------------

Please submit bug reports, feature requests, etc. to the [Pivy
issue tracker][1].

Contact:
--------

If you have any questions regarding Pivy or simply want to discuss
with other Pivy users, you can do so at the general [coin-discuss
mailinglist][2].


[0]: http://www.python.org/sigs/distutils-sig/
[1]: https://github.com/Coin3D/pivy/issues
[2]: http://groups.google.com/group/coin3d-discuss
