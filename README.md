## LAPACK

LAPACK is a library of Fortran subroutines for solving the most commonly
occurring problems in numerical linear algebra.

Documentation is found [here](https://netlib.org/blas)

LAPACK releases are [available on netlib](http://www.netlib.org/lapack/).

The distribution contains (1) the Fortran source for LAPACK, and (2) its
testing programs.  It also contains (3) the Fortran reference implementation of
the Basic Linear Algebra Subprograms (the Level 1, 2, and 3 BLAS) needed by
LAPACK.  However this code is intended for use only if there is no other
implementation of the BLAS already available on your machine; the efficiency of
LAPACK depends very much on the efficiency of the BLAS.  It also contains (4)
CBLAS, a C interface to the BLAS, and (5) LAPACKE, a C interface to LAPACK.

### Installation

 - LAPACK can be installed with `make`. The configuration must be set in the
   `make.inc` file. A `make.inc.example` for a Linux machine running GNU compilers
   is given in the main directory. Some specific `make.inc` are also available in
   the `INSTALL` directory.
 - LAPACK includes also the [CMake](https://cmake.org/) build.  You will need
   to have CMake installed on your machine.  CMake will allow an easy
   installation on a Windows Machine.  An example CMake build to install the
   LAPACK library under `$HOME/.local/lapack/` is:
   ```sh
   mkdir build
   cd build
   cmake -DCMAKE_INSTALL_PREFIX=$HOME/.local/lapack ..
   cmake --build . -j --target install
   ```
 - LAPACK can be built and installed using [vcpkg](https://github.com/Microsoft/vcpkg/) dependency manager:
   ```sh
   git clone https://github.com/Microsoft/vcpkg.git
   cd vcpkg
   ./bootstrap-vcpkg.sh  # ./bootstrap-vcpkg.bat for Windows
   ./vcpkg integrate install
   ./vcpkg install lapack
   ```
   The lapack port in vcpkg is kept up to date by Microsoft team members and community contributors. If the version is out of date, please [create an issue or pull request](https://github.com/Microsoft/vcpkg) on the vcpkg repository.

### User Support

LAPACK has been thoroughly tested, on many different types of computers. The
LAPACK project supports the package in the sense that reports of errors or poor
performance will gain immediate attention from the developers. Such reports,
descriptions of interesting applications, and other comments should be sent by
email to [the LAPACK team](mailto:lapack@icl.utk.edu).

A list of known problems, bugs, and compiler errors for LAPACK is
[maintained on netlib](http://www.netlib.org/lapack/release_notes.html).
Please see as well the [GitHub issue tracker](https://github.com/Reference-LAPACK/lapack/issues).

For further information on LAPACK please read our [FAQ](http://www.netlib.org/lapack/faq.html)
and [Users' Guide](http://www.netlib.org/lapack/lug/lapack_lug.html).
A [user forum](http://icl.cs.utk.edu/lapack-forum/) and specific information for
[running LAPACK under Windows](http://icl.cs.utk.edu/lapack-for-windows/lapack/).
is also available to help you with the LAPACK library.


### Testing

LAPACK includes a thorough test suite. We recommend that, after compilation,
you run the test suite.

For complete information on the LAPACK Testing please consult LAPACK Working
Note 41 "Installation Guide for LAPACK".


### LAPACKE

LAPACK now includes the [LAPACKE](http://www.netlib.org/lapack/lapacke.html)
package.  LAPACKE is a Standard C language API for LAPACK that was born from a
collaboration of the LAPACK and INTEL Math Kernel Library teams.
