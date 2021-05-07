# OpenGL in CLion (MinGW Windows only)
If you have CLion IDE, and you want to run OpenGL programs on it, This simple guide helps you to set up OpenGL project on CLion.
Only you need have required tools and download GLUT library from here [freeglut](https://www.transmissionzero.co.uk/software/freeglut-devel/)

## Requirements for this setup
* CLion IDE
* CMake (built in CLion)
* freeglut
* MinGW with GCC

## Set up
* Create a new project from start up window of IDE. Select C++ Executable, and add project name and Create
* Download and extract `freeglut` inside project's directory. After that your directory structure will look:
```
├── CMakeLists.txt
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


* Then configure your includes by adding line in your [CMakeLists.txt](./CMakeLists.txt#L15)
  `include_directories(freeglut/include)`
  #### For 32 bit GCC compiler
    Add library for linking in [CMakeLists.txt](./CMakeLists.txt#L18)
    -  `link_directories(freeglut/lib)`
  #### For 64 bit compiler
    Add library for linking in [CMakeLists.txt](./CMakeLists.txt#L18)
    -  `link_directories(freeglut/lib/x64)`
* Link GL libraries 
  - `target_link_libraries(${PROJECT_NAME} glu32 opengl32 freeglut)`


* Before start build / running program you need to place `freeglut.dll` file in to one of directory of your %PATH% environmental variable.
  #### For 32 bit compiler
  Place **_freeglut.dll_** from `freeglut/freeglut.dll` to your %PATH%
  #### For 64 bit compiler
  Place **_freeglut.dll_** from `freeglut/x64/freeglut.dll` to your %PATH%

## Note:
+ Ensure that you have completed MinGW installation, because this completely depends on MinGW.
* * If you have 32bit GCC compiler then you need to use only 32bit library and DLL's
  * If your system has 64bit GCC compiler then you must use 64bit libraries otherwise you will encounter runtime error

## Global configuration
  * Place files in freeglut/include to your include/ directory
  * Place files in freeglut/lib to your lib/ directory
  * Place freeglut.dll from bin/ to your %PATH% path