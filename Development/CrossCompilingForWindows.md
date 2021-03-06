# Cross compiling Veyon for Windows on Linux

## Preparations

* Create an Ubuntu 16.04 installation, e.g. by using the netboot installer at

 `http://archive.ubuntu.com/ubuntu/dists/xenial/main/installer-amd64/current/images/netboot/mini.iso`

* Install the add-apt-repository tool and the mingw repisitory

  ```
  sudo apt-get install python-software-properties
  sudo add-apt-repository ppa:tobydox/mingw-w64
  ```
    
  and update your package list cache (e.g. `apt-get update` or similiar)

* Install the following packages:

  * cmake
  * nsis
  * tofrodos
  * g++-mingw-w64
  * qt5base-mingw-w64
  * qt5tools-mingw-w64
  * libz-mingw-w64-dev
  * libjpeg-turbo-mingw-w64
  * libpng-mingw-w64
  * openssl-mingw-w64
  * openldap-mingw-w64
  * default-jdk

## Compiling and building the installer

* Change into the Veyon source directory and type

  ```
  mkdir b
  cd b
  ../cmake/build_mingw32
  make win-nsi
  ```

* This will build a ready-to-use Win32 installer like the ones you can download
  from the Veyon website.

* If you want to build a Win64 installer, run the `build_mingw64` script instead.

