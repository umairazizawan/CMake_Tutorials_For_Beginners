# Set minimum version of CMake
cmake_minimum_required(VERSION 3.13)  

#Create project
project(LinkLibraryToExecutableUsingCMake)

# Create Executable
add_executable(HelloWordExecutable main.cpp)


include_directories(${CMAKE_CURRENT_SOURCE_DIR}/../Library/include)

target_link_libraries(HelloWordExecutable HelloWorldLibrary)

# Install executable to default location "usr/local/bin"
install(TARGETS HelloWordExecutable)

