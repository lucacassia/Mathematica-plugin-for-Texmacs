# Mathematica-plugin-for-Texmacs
Tutorial on how to set up your Mathematica environment inside a Texmacs session.

## Dependencies
This has been tested on a `linux-x86-64` machine with `Mathematica-11.3` and `GNU TeXmacs-1.99.5`.

## Install
Download the patch files contained in the repository:

    git clone https://github.com/megadoro/Mathematica-plugin-for-Texmacs.git
  
Apply the patches to TeXmacs files:

    sudo patch /usr/lib/texmacs/TeXmacs/bin/tm_mathematica Mathematica-plugin-for-Texmacs/tm_mathematica.patch
    sudo patch /usr/share/TeXmacs/plugins/mathematica/Makefile.lazy Mathematica-plugin-for-Texmacs/Makefile.lazy.patch
    sudo patch /usr/share/TeXmacs/plugins/mathematica/src.lazy/tm_mathematica.c Mathematica-plugin-for-Texmacs/tm_mathematica.c.patch

Create a link to `libML64i4.so` in the default library directory of your system:

    MATH=`realpath $(which math) | sed -e 's=/Executables/math$=/SystemFiles/Links/MathLink/DeveloperKit/Linux-x86-64/CompilerAdditions='`
    sudo ln -s $MATH/libML64i4.so /usr/lib/libML64i4.so

Enjoy!
