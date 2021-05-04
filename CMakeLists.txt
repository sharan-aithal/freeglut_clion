cmake_minimum_required(VERSION 3.19)
project(freeglut_clion) # Project name

set(CMAKE_CXX_STANDARD 14)

# Download freeglut library and extract inside the project directory
# It should look like:
# freeglut/
#   bin/
#   include/
#   lib/

# Then you need to include header files such sa GL/glut.h
# The below line includes these header files
include_directories(freeglut/include) # freeglut/include has to contain the required OpenGL's .h files

# The below line links freeglut library
link_directories(freeglut/lib) # freeglut/lib has to contain the required OpenGL's .a files

# It will set library names to variable named OpenGlLibs
set(OpenGlLibs glu32 opengl32 freeglut) # link libraises and NOTE: here we are linking freeglut instead glut

add_executable(freeglut_clion main.cpp) # Executable filename and source file

# Finally link required library to the source program
target_link_libraries(freeglut_clion ${OpenGlLibs})