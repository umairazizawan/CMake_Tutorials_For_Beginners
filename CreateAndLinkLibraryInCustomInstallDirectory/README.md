# CreateAndLinkLibraryWithCustomInstallDirectory

This project creates a simple "HelloWorld" Library and links it to an executable.
This is meant to cover a standard workflow of just creating your own library and then using it in another library or executable.
Building this type of project is fairly staright forward but most Devs struggle with the errors such as: 
```
./HelloWordExecutable: error while loading shared libraries: libHelloWorldLibrary.so: cannot open shared object file: No such file or directory
```
There are many ways to successfully link to a library at runtime, which creates alot of confusion for beginners as they are not familiar with the  workings of $Path, RPath, LD_LIBRARY_PATH and runPath, and the role they play in executables finding libraries at runtime. 

This project uses RPath to link the library to an executable in a custom install directory. Please view CMakeLists.txt comments for details

The reader is encouraged to use this tutorial as starting point and go through the discussions on various forums to develope a better understanding of how $Path, RPath, LD_LIBRARY_PATH and runPath work.

## Build Steps

### Command Line

First lets look at building the project without install.


1. Create a folder named `build` and `install` in the directory containing this README.md file.

2. Inside the build folder run the command
    ```
    cmake -DCMAKE_INSTALL_PREFIX:PATH=<path-to-install-directory> ..
    ```
    
    In the above command replace `<path-to-install-directory>` with the path to the install directory. Here we are telling cmake the location of the install directory, by default it is `/usr/local`.

3. Now after the `make` command you need to do `make install` which will copy your program to the `install/bin` folder.

4. Now Open a terminal in `install/bin` folder and run the executable with
    ```
    ./HelloWordExecutable
    ```

### GUI

Open CMake-Gui. 


1. Click "browse source" and navigate to the tutorial folder.
2. Create build folder in the directory containing this README.md file. Click "browse build" and provide path to the build folder created earlier
3. Click "Configure".
4. Once configured, set the Install directory("install" folder location) as the value of "CMAKE_INSTALL_PREFIX".
5. Click "Generate"
6. Close CMake-Gui.
7. Open the "build" folder in the terminal.
8. Run commands 
    ```
    make
    make install
    ```
9. Browse to install folder. There should be an executable in bin directory. For Example "HelloWordExecutable".

10. Open a terminal in bin directory and run the program. For example for HelloWordExecutable run the following command
    ```
    ./HelloWordExecutable
    ``` 

