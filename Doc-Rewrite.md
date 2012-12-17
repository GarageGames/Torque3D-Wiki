Torque3D v2.0
=============

MIT Licensed Open Source version of [Torque 3D](http://www.garagegames.com/products/torque-3d) from [GarageGames](http://www.garagegames.com)

More Information
----------------

* Documentation is in the [Torque3D-Documentation](https://github.com/GarageGames/Torque3D-Documentation) GitHub repo.
* Project Manager is in the [Torque3D-ProjectManager](https://github.com/GarageGames/Torque3D-ProjectManager) GitHub repo.
* T3D [Beginner's Forum](http://www.garagegames.com/community/forums/73)
* T3D [Professional Forum](http://www.garagegames.com/community/forums/63)
* GarageGames [Store](http://www.garagegames.com/products)
* GarageGames [Professional Services](http://services.garagegames.com/)

Creating a New Project Based on a Template
------------------------------------------

The templates included with Torque 3D provide a starting point for your project.  Once we have created our own project based on a template we may then compile an executable and begin work on our game.  The following templates are included in this version of Torque 3D:

* Empty
* Empty PhysX
* Full
* Full PhysX

### Using PhysX ###

If you plan on creating a project based on a template that uses PhysX you will first need to have the PhysX SDK intalled on your computer.  Without the PhysX SDK in place the project generation step will fail when using either the *Project Manager* or manual project generation methods.

This version of Torque 3D makes use of the PhysX SDK version 2.8.4.6.  The following steps are used to install this SDK:

1. In a web browser, go to the [NVidia Support Center](http://supportcenteronline.com/ics/support/default.asp?deptID=1949)
2. If you do not have an account, you will need to register with them to have the support staff create an account for you.
3. If you have an account, login.
4. On the middle of the page, on the right, click on Downloads.
5. On the far right column, under Old downloads, click More.
6. Download the Windows 2.8.4.6 version.
7. Run the installer and follow the steps to install it in the default location.
8. Depending on your operating system version, you may need to reboot after the installation.

### Using the Project Manager to Create a Project ###

The *Project Manager* may be used to create a new game project based on one of the templates that are included with Torque 3D.  If you are using Torque 3D directly from the GitHub repository then you will need to get the *Project Manager* from the [Torque3D-ProjectManager](https://github.com/GarageGames/Torque3D-ProjectManager) repo.

The following steps use the *Project Manager* to create a new project:

1. Run the *Project Manager*.
2. Click the *New Project* button.
3. Choose a template from the drop down on the right.
4. Give the project a name.
5. Click the *Create* button to create the project.  This will open a new dialog window that shows the progress.
6. When it finishes, click the *Finished* button.
7. You may click on the *Open Folder* button to go to the project's directory.

### Manually Creating a Project ###

We may also manually create a project based on a template.  The following steps outline how to do this:

1. Open the *Templates* directory.
2. Right-click on the template you would like to use and choose *Copy*.
3. Go to the *My Projects* directory and paste the template there.
4. Rename the pasted template to the name of your project/game.
5. Go into your project's *game* directory and rename all executables, DLL files and the .torsion file (and maybe .torsion.opt) from the template name to that of your project (these files may not be present at this time).
6. Open the .torsion file in a text editor and replace all references to the template's name with that of your project (you only need to do this if you plan on using Torsion).
7. Open you project's *source/torqueConfig.h* file in a text editor and change the `TORQUE_APP_NAME` define to the name of your project.
8. In your project's *buildFiles/config* directory open each .conf file and find each reference to the template's name and replace it with the name of your project.
9. Open your project's *game/main.cs" file in a text editor and replace all template references to the name of your project.
10. Go to your project's directory and double click on the *generateProjects.bat* to create your project's solution files.





Compiling Torque 3D
-------------------

If you are going to be using a PhysX template, then you will need to complete this step. Otherwise, you can go to 2a.

1. Install the PhysX SDK version 2.8.4.6.  
  * In a web browser, go to the NVidia Support Center (http://supportcenteronline.com/ics/support/default.asp?deptID=1949)
  * If you do not have an account, you will need to register with them to have the support staff create an account for you.
  * If you have an account, login.
  * On the middle of the page, on the right, click on Downloads.
  * On the far right column, under Old downloads, click More.
  * Download the Windows 2.8.4.6 version.
  * Run the installer and follow the steps to install it in the default location.
  * Depending on your operating system version, you may need to reboot after the installation.

2a. Creating a New Game Project - With Toolbox
  * Run the Torque 3D Toolbox.
  * Click New Project.
  * Choose a base template.
  * Name the Project.
  * Click Create to create the project.
  * When it finishes, click the Finished button.

2b. Creating a New Game Project - Manually
  * Open the Templates directory.
  * Right-click and copy the template that you want to use.
  * Navigate to the directory where you want to develop your game.
  * Paste inside of that directory to copy the files.
  * Open the game directory.
  * Rename the executable and DLL files to the name of your game (for example, rename Full.exe to MyGame.exe if you used the Full template).
  * Rename the plugin's in the same way, replacing the template name with your game's name.
  * Inside your project directory, double-click the generateProjects.bat file.
  * It will create the solutions.
 
3. Compiling Torque 3D
  * Navigate to engine\build\Visual Studio 2010
  * Double-click the Torque 3D.sln file.
  * When Visual Studio 2010 is fully loaded, press F5 to perform a clean build.

License
-------

Copyright (c) 2012 GarageGames, LLC

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to
deal in the Software without restriction, including without limitation the
rights to use, copy, modify, merge, publish, distribute, sublicense, and/or
sell copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS
IN THE SOFTWARE.
