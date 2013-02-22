Before you can make use of the Razer Hydra controller in Torque 3D you will need to download the Sixense SDK from their [web site](http://sixense.com/developers) and extract it to a convenient directory.

### Configure Your project.conf ###

With the Sixense SDK in place, you will need to modify your project's `buildFiles/config/project.conf` file in a text editor.  The first step is to let Torque 3D's Project Generator know where the Sixense SDK is located.  The easiest way to do this is to add the `$RAZERHYDRA_SDK_PATH` global variable to the top of your `project.conf` file.  For example:

`$RAZERHYDRA_SDK_PATH = "C:\Users\dwyand_2\Downloads\RazerHydra\SixenseSDK_062612";`

You may also create a Windows environmental variable named `TORQUE_RAZERHYDRA_PATH` that also provides an absolute path to the Sixense SDK.  Going this route doesn't store the path within the `project.conf` file, which may be required if multiple developers are working on the same project.

The second addition to your `project.conf` file is a reference to the Torque 3D's Project Generator module for the Razer Hydra.  Add the following between the `Torque3D::beginConfig()` and `Torque3D::endConfig()` lines:

```
    // Include Razer Hydra module
    includeModule( 'razerHydra' );
```

With these changes in place you may run your project's `generateProjects.bat` file to rebuild the various Visual Studio files.
