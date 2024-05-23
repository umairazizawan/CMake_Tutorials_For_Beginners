# CMake_Tutorials_For_Beginners
The Goal of this repository is to provide the basis for Complete beginners to start working with CMake. In particular it is written from the perspective of New Developers who are more comfortable with Windows and have only recently shifted to Linux. 
Basic CMake Projects will be added to this Repository over time. The CMakeLists.txt files contain comments explaining the purpose of each line of code.

1. HelloWordofCMake


# Platform
```
    Linux, Ubuntu 20.04 LTS
```

# build

1. Clone repository
2. Create separate folders names build and install
3. Open CMake-Gui. 

***Note***: The use of CMake-Gui is just for simplicity as this is a tutorial for complete beginners. CMake can be easily used from Terminal as well.

4. Click "browse source" and navigate to the tutorial folder you wish to build. 
5. Similarly Click "browse build" and provide path to the build folder created earlier
6. Click "Configure".
7. Once configured, set the Install directory("install" folder location) as the value of "CMAKE_INSTALL_PREFIX".
8. Click "Generate"
9. Close CMake-Gui.
10. Open the "build" folder in using FILES (file explorer) and open terminal in this directory or just open a terminal and cd to the "build" Directory
11. Run commands 
```
    make
    make install
```
12. Browse to install folder. There should be an executable in bin directory. For Example "HelloWorld".

13. Open a terminal in bin directory and run the program. For example for HelloWorld run the following command
```
    ./HelloWorld
``` 