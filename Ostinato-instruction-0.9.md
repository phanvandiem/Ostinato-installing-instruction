Prerequisites
=============

Ostinato v0.9 has the following dependencies:

- QT 4.3+ (but not Qt5.x)
- Protocol Buffers 2.3+ (bug not 3.x)
- libpcap

Install Prerequisites
=====================


    sudo apt install qt4-default libpcap-dev
    
For Protocol Buffer 2.3+, clone and build from git repo.


    git clone https://github.com/protocolbuffers/protobuf.git
    cd protobuf
    git checkout tags/v2.6.1
    curl https://src.fedoraproject.org/repo/pkgs/gtest/gtest-1.5.0.tar.bz2/8b2c3c3f26cb53e64a3109d03a97200a/gtest-1.5.0.tar.bz2 | tar jx
    mv gtest-1.5.0 gtest
    ./autogen.sh
    if occur error: possibly undefined macro: AC_PROG_LIBTOOL then use command: sudo apt-get install libtool
    ./configure
    make
    sudo make install


Build Steps
===========

1. Check out the source code version 0.9


    git clone https://github.com/pstavirs/ostinato.git
    cd ostinato
    git checkout tags/v0.9

2. Build the source code


    qmake
    make
    if occur protoc: error while loading shared libraries: libprotobuf.so.9: cannot open shared object file: No such file or directory then use command
    export LD_LIBRARY_PATH=/usr/local/lib
    sudo make install

References
==========

#. https://devguide.ostinato.org/BuildingFromSource.html
#. https://github.com/protocolbuffers/protobuf/tree/v2.6.1
