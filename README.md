Testing Environment for Literary Creative Turing Tests 2018
===========================================================

This document describes the virtual machine used in the [Literary Creative Turing Tests 2018](http://bregman.dartmouth.edu/turingtests/Literary2018) (part of the [Turing Tests in Creative Arts](ttca)).

[ttca]: http://bregman.dartmouth.edu/turingtests/

The testing environment is based on Ubuntu 16.04.4 with many packages installed.

The testing environment will not have access to the Internet. Plan accordingly.

If you have any difficulty porting your software to run in this Linux
environment, please contact the organizers of the competition and we will find
a solution.

VirtualBox machine images matching this setup are available. If you do not use
VirtualBox but would like to test your submission on a cloud server, contact
the organizers.

Overview
--------

Contestants will submit a compressed archive of their software (.zip, .tar.gz,
.tar.xz). The archive will be expanded into a temporary directory. The archive
should include an executable named ``runMe`` at the root of the archive. This
executable will be run with arguments that depend on the competition.

### Arguments passed to ``runMe`` in PoetiX, LimeriX, LyriX, and DigiKidLit

``runMe`` will be called with two arguments:

1. a noun or noun-phrase (e.g., "solitude", "red wheelbarrow")
2. a random positive integer (for reproducibility, if you are using a random seed)

Both the first and second arguments may be ignored. The second (integer) argument is provided for 
contestants who have designed software that makes use of a random seed to achieve deterministic results.

Assuming the local directory is the temporary directory into which the
submission archive has been extracted, the following is an example of the shell
command used to solicit a sonnet from the software:

```bash
./runMe solitude 5
```

Installed Packages
------------------

A variety of software is available in the testing environment. Participants
are, however, encouraged to submit software with pre-compiled libraries and/or
binaries and not rely on the testing environment for compilation.

The base image is the [Ubuntu 16.04 LTS (Xenial Xerus) cloud
image](https://cloud-images.ubuntu.com/xenial/current/). A number of packages
are installed using the following commands:

```bash
apt-get update && \
apt-get -yq dist-upgrade && \
apt-get install -yq \
  wget \
  bzip2 \
  ca-certificates \
  locales \
  build-essential \
  gfortran \
  gcc \
  clang && \
apt-get install -yq \
  git \
  vim \
  jed \
  emacs \
  build-essential \
  python-dev \
  unzip \
  libsm6 \
  pandoc \
  texlive-latex-base \
  texlive-latex-extra \
  texlive-fonts-extra \
  texlive-fonts-recommended \
  texlive-generic-recommended \
  texlive-xetex \
  libxrender1 \
  inkscape && \
apt-get install -yq \
  python3-all \
  python3-dev \
  python-all \
  python-dev \
  libav-tools && \
apt-get install -yq \
  python3-pandas \
  python3-numexpr \
  python3-matplotlib \
  python3-scipy \
  python3-seaborn \
  python3-sklearn \
  python3-skimage \
  python3-sympy \
  python3-sympy \
  python3-hdf5storage \
  python3-h5py \
  python3-lxml \
  python3-xlrd && \
apt-get install -yq \
  python-pandas \
  python-numexpr \
  python-matplotlib \
  python-scipy \
  python-seaborn \
  python-sklearn \
  python-skimage \
  python-sympy \
  python-sympy \
  python-hdf5storage \
  python-h5py \
  python-lxml \
  python-xlrd && \
apt-get install -yq \
  r-base \
  r-base-dev \
  r-cran-caret \
  r-cran-crayon \
  r-cran-plyr \
  r-cran-randomforest \
  r-cran-rcurl \
  r-cran-reshape2 \
  r-cran-rsqlite \
  fonts-dejavu
```
