# Set minimum version of CMake
cmake_minimum_required(VERSION 3.13)  

#Create project
project(CreateLibraryUsingCMake)


###################################################################################################
#                                                Create Library                                   #
###################################################################################################

#[[ Add the "include" folder, which contains HelloWorld.h, to the list of locations
 the compiler will search.
 In practical terms, for the present case, the include_directories() command basically allows HelloWorld.cpp
 to find HelloWorld.h.
 Both relative and Absolute paths can be provided. 
 Relative paths start from the location of CMakeLists.txt  
 ]]
include_directories(include)

#[[ Use add_subdirectory command to tell CMake to look for a CMakeLists.txt
 in a subfolder. This is useful when compiling large Projects.
 Note: If something is specificed in a Parent folder CMakeLists.txt such as a variable name, it will
 also be available to any CMakeLists.txt that exist in the subfolders, if it is specified as a subdirectory()
 The above include_directories command could be taken as an example of this.
 ]]
add_subdirectory(src)

###################################################################################################
#                                                Utilize Library                                  #
###################################################################################################

# If we just run the program without setting CMAKE_INSTALL_RPATH, the HelloWordExecutable will not be able to locate the Library at RunTime
# and exit with the following error.
#./HelloWordExecutable: error while loading shared libraries: libHelloWorldLibrary.so: cannot open shared object file: No such file or directory
# This is because by default CMake strips this variable when installing binaries. This is because libraries are usually installed in `lib` or `usr/lib`.
# These directories are included in the environment of every terminal session.

SET(CMAKE_INSTALL_RPATH "${CMAKE_INSTALL_PREFIX}/bin/libraries")

# Create Executable
add_executable(HelloWordExecutable main.cpp)

# Link Executable to Library
target_link_libraries(HelloWordExecutable HelloWorldLibrary)

# Install executable
install(TARGETS HelloWordExecutable)

