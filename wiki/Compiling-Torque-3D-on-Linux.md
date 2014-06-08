This version of Torque 3D supports being run as a dedicated server under Linux.  As with a Windows build you will need to run your project's *generateProjects.command* file to properly generate the required make file.

Prior to compiling Torque 3D under Linux, you will need to make sure you have the appropriate libraries and tools installed.  The exact packages will depend on which Linux distribution you are using.  For example, under Ubuntu you will need:

* build-essential
* nasm
* git
* php5-cli
* libsdl-dev
* libogg-dev

With everything in place you may now follow these steps to compile Torque 3D:

1. Change to you project's *buildFiles/Make_Ded* directory.
2. Enter the `make clean` command.
3. Enter the either the `make debug` or `make release` command depending on the type of build you wish to make.
4. Go to your project's *game* directory.
5. To start your game enter the following command (we'll use the name *MyGame* as the example project name):  
    `./MyGame -dedicated -mission "levels/Empty Terrain.mis"`  
    where the argument after the `-mission` switch is the path to the mission to load.
