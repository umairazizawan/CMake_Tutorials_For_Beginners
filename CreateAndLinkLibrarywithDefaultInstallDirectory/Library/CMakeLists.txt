include_directories(include)

#[[Create an Library by providing the add_library command with three arguments: 
   1. Library name. This will be the name of created Library.
   2. Type of Library. Here we are creating a Dynamic Library (.so) for which we specify "SHARED"
      Other types are STATIC and MODULE.
      Note: In general SHARED and STATIC are the commonly used types 
      The detailed differences and uses of each these in beyond the present scope.
      But there are alot of excellent explanations available on the subject on Github and Stackoverflow.
   3. Files to compile (source files)
 ]]
add_library(HelloWorldLibrary SHARED HelloWorld.cpp)

#Install the created Library in the defeault location "usr/local/lib" by not proivding a destination 
install(TARGETS HelloWorldLibrary)
