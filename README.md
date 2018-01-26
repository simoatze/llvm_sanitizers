<div id="table-of-contents">
<h2>Table of Contents</h2>
<div id="text-table-of-contents">
<ul>
<li><a href="#org3a0e2c8">1. Introduction</a></li>
<li><a href="#org439bac7">2. Prerequisites</a></li>
<li><a href="#org00d4c9f">3. Installation</a>
<ul>
<li><a href="#org09f20c6">3.1. Options</a></li>
</ul>
</li>
<li><a href="#org1841460">4. Contacts and Support</a></li>
</ul>
</div>
</div>


<a id="org3a0e2c8"></a>

# Introduction

This script download, build and install Clang/LLVM with Google Sanitizers support.


<a id="org439bac7"></a>

# Prerequisites

To compile Clang/LLVM you need a recent version of GCC >= 4.8.5 and, a
CMake version >= 3.4.3.

Ninja build system is preferred. For more information how to obtain
Ninja visit <https://martine.github.io/ninja>.


<a id="org00d4c9f"></a>

# Installation

This script facilitate the build of Clang/LLVM with with Google Sanitizers support.

You can start the build process by running `build.sh`:

    export LLVM_INSTALL=/your/install/path
    ./build.sh --prefix=${LLVM_INSTALL}

The installation script will create a folder called *LLVM* at the same
level of the *llvm\_sanitizers* directory and install LLVM into
*LLVM\_INSTALL*. If you do not specify the *&#x2013;prefix* option, by
default the script will try to install the software under "/usr".

You can specify the *&#x2013;no-install* option to skip the install
(e.g. make install) and keep the executable under the build directory.

Once the installation completes, you need to setup your environement
to allow Clang/LLVM to work correctly.

Please set the following path variables:

    export PATH=${LLVM_INSTALL}/bin:${PATH}"
    export LD_LIBRARY_PATH=${LLVM_INSTALL}/lib:${LD_LIBRARY_PATH}"

If you used the option *&#x2013;no-install* you can setup your environment
with the following commands (change *\\/current\\/path* with the path to
the *build.sh* script folder):

    export PATH=/current/path/../LLVM/llvm_build/build/bin:${PATH}"
    export LD_LIBRARY_PATH=/current/path/../LLVM/llvm_build/build//lib:${LD_LIBRARY_PATH}"

To make the environment permanent add the previous lines or
equivalents to your shell start-up script such as "~/.bashrc".


<a id="org09f20c6"></a>

## Options

Running the command:

    ./install --help

shows the options available for building and installing Clang/LLVM.

    Usage

      ./build.sh [options]

    Options
      --prefix=<value>             = Specify an installation path.
      --build-system=<value>       = Specify a build system generator. Please run
                                     'man cmake-generators' for a list of generators
                                     available for this platform. Default is Ninja.
      --release=<value>            = Specify the release version of Clang/LLVM that
                                     will be installed (>= 39). Default is 3.9.
      --http                       = Enables GitHub web url in case SSH key and
                                     passphrase are not set in the GitHub account.
      --update                     = Update previous building. Default is SSH.
      --build-type=<value>         = Specify the type of build. Accepted values
                                     are Release (default), Debug or RelWithDebInfo.
      --gcc-toolchain-path=<value> = Specify the GCC toolchain path.
      --no-install                 = Do not install.


<a id="org1841460"></a>

# Contacts and Support

-   E-Mail Contacts:

    <ul style="list-style-type:circle"> <li> <a href="mailto:satzeni@nvidia.com?Subject=[llvm_sanitizer]%20" target="_top">Simone Atzeni</a> </li></ul>
