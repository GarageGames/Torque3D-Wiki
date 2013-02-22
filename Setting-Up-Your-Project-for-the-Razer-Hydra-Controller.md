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

### Example project.conf ###

Here is a complete example of a `project.conf` file with all of the required changes:

```
<?php

// Set this true to enable hifi networking instead of standard.
// In general ... hifi is designed to better deal with fast
// moving players in close proximity to each other, such as
// a racing game.
$TORQUE_HIFI_NET = false;

// Set this to true to enable the ExtendedMove class.  This
// allows the passing of absolute position and rotation input
// device information from the client to the server.
$TORQUE_EXTENDED_MOVE = false;

// Our path to the Razer Hydra SDK:
$RAZERHYDRA_SDK_PATH = "C:\Users\dwyand_2\Downloads\RazerHydra\SixenseSDK_062612";

// Configure Torque 3D
Torque3D::beginConfig( "win32", "HydraRyder" );

    // Include Razer Hydra module
    includeModule( 'razerHydra' );
        
    // Enable for optional minidump debugging support
    // addProjectDefine( 'TORQUE_MINIDUMP' );
        
Torque3D::endConfig();

?>
```

### Required DLLs ###

Before you may run your freshly compiled game you will need to include the appropriate Sixense DLLs with your game's executable.  These files are located in the `SixenseSDK_062612/bin/win32` directory.  Specifically you should copy the `sixense.dll` (the release library) and `sixensed.dll` (the debug library) into the same directory as your game's executable.  It appears that the debug version of the Sixense DLL also requires `DeviceDLL.dll` that is located in the `SixenseSDK_062612\samples\win32\sixense_simple3d` directory.  When it comes time to release your game you only need to include the 'sixense.dll' library.
