User Manual
===========

It's very helpful to drag the mouse (or pen) while pressing `space` to pan the
canvas.  Also, switching between the brush and the eraser with `b` and `e`.
You can change the brush size with `[` and `]` and control the transparency
with the number keys.

While on Windows there are binaries available, for Milton on Linux or OSX you will have to compile from source. There are some basic build instructions below. They will probably build, but please be prepared to do a bit of debugging on your end if you run into trouble, since these are not the primary development platforms.

How to Compile
==============

Windows
-------

Milton currently supports Visual Studio 2019.

Other versions of Visual Studio might not work.

To build:

Run a x64 developer command prompt (for VS 2019 this corresponds to the "x64 Native Tools Command Prompt") and type the following:

```
build.bat
```

Milton will be compiled to `build\Milton.exe`


This repo provides a binary SDL.lib that was compiled by running
`build_deps.bat` in the `third_party` directory.


Linux and macOS
---------------

On 2021-02-27 a successful build for Linux can be done with these steps:

While in the milton top directory
```
cd third_party/SDL2-2.0.8
mkdir build
cd build
cmake -DVIDEO_WAYLAND=OFF -DCMAKE_INSTALL_PREFIX=linux64 -DCMAKE_BUILD_TYPE=Debug ../
make
make install
```

and then in the milton top directory, so ```cd ../../../```,
```
mkdir build
cd build
cmake ../
make
```

And if successful, you should have an executable called "Milton" that runs.

Versioning scheme
=================

Milton uses a MAJOR.MINOR.PATCH versioning scheme, where MAJOR keeps track of very significant changes, such as a UI overhaul. MINOR keeps track of binary file format compatibility. PATCH is incremented for new releases that do not break file format compatibility. PATCH version gets reset to 0 when the MINOR version increases.

For example, Milton version 1.3.1 can read mlt files produced any previous version, but it can't read files produced by 1.4.0


License
=======

    Milton

    Copyright (C) 2015 - 2018 Sergio Gonzalez

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <http://www.gnu.org/licenses/>.

Thanks
======

Milton is made with love by Sergio Gonzalez with the help of [awesome
people](https://github.com/serge-rgb/milton/blob/master/CREDITS.md).


