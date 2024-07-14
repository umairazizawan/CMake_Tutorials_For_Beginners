# HelloWorldofCMake

This a very basic cmake project for beginners.

## Build Steps

### Command Line

First lets look at building the project without install.

1. Create a folder named `build` in the directory containing this README.md file.
2. Inside the build folder run the command
    ```
    cmake ..
    ```
    `..` is the directory containing the `CMakeLists.txt`. In Linux `.` is used to refer to the current directory and `..` means one directory above that.
3. Now run the command
    ```
    make
    ```
    This will start compiling your project. After this is complete you will be able to see the executable `HelloWorld`.
4. Now you can run the executable with
    ```
    ./HelloWorld
    ```

If you want to install your project as well as build it then you have to specify the install location. Installing basically copies the executable and other necessary files to another location just like installing an app on your computer. 

1. Create a folder named `build` and `install`
2. Inside the build folder run the command
    ```
    cmake -DCMAKE_INSTALL_PREFIX:PATH=<path-to-install-directory> ..
    ```
    
    In the above command replace `<path-to-install-directory>` with the path to the install directory. Here we are telling cmake the location of the install directory, by default it is `/usr/local`.

3. Now after the `make` command you need to do `make install` which will copy your program to the `install/bin` folder.

4. Now Open a terminal in `install/bin` folder and run the executable with
    ```
    ./HelloWorld
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
9. Browse to install folder. There should be an executable in bin directory. For Example "HelloWorld".

10. Open a terminal in bin directory and run the program. For example for HelloWorld run the following command
    ```
    ./HelloWorld
    ``` 

