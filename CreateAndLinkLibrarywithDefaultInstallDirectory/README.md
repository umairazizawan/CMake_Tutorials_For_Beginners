# CreateAndLinkLibraryWithDefaultInstallDirectory

This project creates a simple "HelloWorld" Library and links it to an executable.
This is meant to cover a basic use case for new developersof just creating your own library, installing it in the default directory and then using it in an executable installed in the default executable directory.

Note incase of the following error 
```
./HelloWordExecutable: error while loading shared libraries: libHelloWorldLibrary.so: cannot open shared object file: No such file or directory
```

If not execute the following command  and do echo $PATH again and `/usr/local/bin` should now be in your path
```
    sudo ldconfig
```
NOTE: You are encouraged to search the purpose of ldconfig command yourself. To oversimply it this command configured paths such as `/usr/local/lib` and  `/usr/local/bin`  so that any terminal searches these directories for libraries and executables. You can check if `/usr/local/bin` is include in your path by using the following command. 
```
echo $PATH
```

## Build Steps

### Command Line

1. Create a folder named `build` and `install` in the directory containing this README.md file.

2. Inside the build folder open a terminal and run the command
    ```
    cmake ..
    ```

3. Next execute the `make` command. Followed by `make install` which will install the newly created library to its default directory ` /usr/local/lib/` and the executable to  `/usr/local/bin/`. Incase you get the following error message when executing `make install`:

"/usr/local/lib/libHelloWorldLibrary.so": Permission denied.

Just do: 

"sudo make install"

4. Now go the the exectuable directory using following command
    ```
    cd /usr/local/bin/
    ``` 
5. Run the executable with
    ```
    ./HelloWordExecutable
    ```

### GUI

Open CMake-Gui. 


1. Click "browse source" and navigate to the tutorial folder.
2. Create build folder in the directory containing this README.md file. Click "browse build" and provide path to the build folder created earlier.
3. Click "Configure" without making any other changes.
5. Click "Generate"
6. Close CMake-Gui.
7. Open the "build" folder in the terminal.
8. Run commands 
    ```
    make
    make install
    ```
    Incase you get the following error message when executing `make install`:

    "/usr/local/lib/libHelloWorldLibrary.so": Permission denied.

    Just do: 

    "sudo make install"

9. Browse to the default installation directory `/usr/local/bin/` . There should be an executable in bin directory. For Example "HelloWordExecutable".

10. Open a terminal in bin directory and run the program. For example for HelloWordExecutable run the following command
    ```
    ./HelloWordExecutable
    ``` 

