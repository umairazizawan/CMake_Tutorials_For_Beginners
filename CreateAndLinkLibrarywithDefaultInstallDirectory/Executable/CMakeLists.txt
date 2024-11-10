# Set minimum version of CMake
cmake_minimum_required(VERSION 3.13)  

#Create project
project(LinkLibraryToExecutableUsingCMake)

# Create Executable
add_executable(HelloWordExecutable main.cpp)


# In general if we are linking to an external library this would not be required.
# But for the purpose of this demo we include the path of the HelloWorld.h header file
# as the executable needs to know its contents at compile time.
# Incase of a third party external library the header would either be installed in 
# `usr/include` or `usr/local/include` so this would not be required, as headers are typically
# shipped with a package, but this is beyond the scope of the current topic 
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/../Library/include)

# Tell the executable to link to the HelloWorldLibrary
target_link_libraries(HelloWordExecutable HelloWorldLibrary)

# Install executable to default location "usr/local/bin"
install(TARGETS HelloWordExecutable)

