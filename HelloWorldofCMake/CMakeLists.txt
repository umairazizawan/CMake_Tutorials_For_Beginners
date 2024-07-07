#[[First thing any beginners needs to understand is that writing a CMakeLists.txt counts as writing Code.
   Therefore it should be given the same amount of thought and effort.
   Also, Like any code it has certain rules and syntax.
 ]]


#[[Set supported minimum version of CMake which must be installed on machine to compile this project.
   Every CMakeLists.txt requires this.
 ]]
cmake_minimum_required(VERSION 3.13)  

#[[Create project "HelloWordProject". 
   Every CMakeLists.txt requires a project name. 
   The name can be anything, The rules are similar to defining a variable.
 ]]
project(HelloWordProject)

#[[Create an executable by providing the add executable command with two arguments: 
   1. Executable name. This will be the name of created executable 
      which the user can run in terminal. Again the name can be anything, similar to a variable. 
   2. Files to compile (source files)
 ]]
add_executable(HelloWorld main.cpp)

#[[Install the created executable when make install command is called in terminal
   Here the TARGETS attribute tells cmake that an executable is to be installed 
 ]]
install(TARGETS HelloWorld)
