#[[ To do Add context/purpose/use case
]]

# Set minimum version of CMake
cmake_minimum_required(VERSION 3.13)  

#Create project
project(CreateLibraryUsingCMake)


###################################################################################################
#                                                Create Library                                   #
###################################################################################################

#[[ Add the "include" folder, which contains HelloWorld.h, to the list of locations
 the compiler will search.
 In practical terms for the present case, the include_directories() command basically allows HelloWorld.cpp to find
 HelloWorld.h.
 Both relative and Absolute paths can be provided. 
 Relative paths start from the location of CMakeLists.txt  
 ]]
include_directories(include)

#[[ Use add_subdirectory command to tell CMake to look for a CMakeLists.txt
 in a subfolder. This is useful when compiling large Projects.
 Note: If something is specificed in a Parent folder CMakeLists.txt such as a variable name, it will
 also be available to any CMakeLists.txt that exist in the subfolders, if it is specified as a subdirectory()
 In the present case, the include_directories could be taken as an example.
 ]]
add_subdirectory(src)

###################################################################################################
#                                                Utilize Library                                  #
###################################################################################################

# To do Add more details
# If we just run the program without setting CMAKE_INSTALL_RPATH, the HelloWordProgram will not be able to locate the Library at RunTime
# and exit with the following error.
#./HelloWordProgram: error while loading shared libraries: libHelloWorldLibrary.so: cannot open shared object file: No such file or directory
# This is because by default CMake strips this variable when installing binaries....

SET(CMAKE_INSTALL_RPATH "${CMAKE_INSTALL_PREFIX}/bin/libraries")

# Create Executable
add_executable(HelloWordProgram main.cpp)

#To do
target_link_libraries(HelloWordProgram HelloWorldLibrary)

# Install executable
install(TARGETS HelloWordProgram)

