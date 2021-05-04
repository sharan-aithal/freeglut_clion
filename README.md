# OpenGL in CLion
This is a simple guide to set up OpenGL project on CLion
You need download GLUT library from here [freeglut](https://www.transmissionzero.co.uk/software/freeglut-devel/)

## Set up
Download and extract freeglut inside project's directory.
Directory structure:
```
├── CMakeLists.txt
├── README.md
├── freeglut
│   ├── Copying.txt
│   ├── Readme.txt
│   ├── bin
│   │   ├── freeglut.dll
│   │   └── x64
│   │       └── freeglut.dll
│   ├── include
│   │   └── GL
│   │       ├── freeglut.h
│   │       ├── freeglut_ext.h
│   │       ├── freeglut_std.h
│   │       └── glut.h
│   └── lib
│       ├── libfreeglut.a
│       ├── libfreeglut_static.a
│       └── x64
│           ├── libfreeglut.a
│           └── libfreeglut_static.a
└── main.cpp
```

## Requirements for this setup
* CLion IDE
* CMake (built in CLion)
* freeglut
* MinGW with GCC

## Note:
+ If you have 32bit GCC compiler then you need to use only 32bit library and DLL's
+ If your system has 64bit GCC compiler then you must use 64bit libraries
