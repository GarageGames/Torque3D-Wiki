# Compiling Torque 3D
How to Generate Visual Studio Projects and Compile Torque 3D

## 1a. Creating a New Game Project - With Toolbox
* Run the Torque 3D Toolbox.
* Click New Project.
* Choose a base template.
* Name the Project.
* Click Create to create the project.
* When it finishes, click the Finished button.

## 1b. Creating a New Game Project - Manually
* Open the Templates directory.
* Right-click and copy the template that you want to use.
* Navigate to the directory where you want to develop your game.
* Paste inside of that directory to copy the files.
* Open the game directory.
* Rename the executable and DLL files to the name of your game (for example, rename Full.exe to MyGame.exe if you used the Full template).
* Rename the plugin's in the same way, replacing the template name with your game's name.
* Inside your project directory, double-click the generateProjects.bat file.
* It will create the solutions.

## 3. Compiling Torque 3D
* Navigate to engine\build\Visual Studio 2010
* Double-click the Torque 3D.sln file.
* When Visual Studio 2010 is fully loaded, press F5 to perform a clean build.