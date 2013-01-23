The [Leap Motion](https://www.leapmotion.com/) controller allows for hands and fingers to provide input to an application.  With commit [27a81f9c0d](https://github.com/GarageGames/Torque3D/commit/27a81f9c0da8c10fc406a451022f01fc41265fb7) the *development* branch now has preliminary support for this new input device.

### Making Use of the Leap Motion Controller in Your Project ###

Before you can make use of the Leap Motion controller in Torque 3D you will need to download the Leap Motion SDK from their web site and extract it to a convenient directory.  As of this writing you need to be invited into their developer program in order to gain access to their SDK.

With the SDK in place, you will need to modify your project's `buildFiles/config/project.conf` file in a text editor.  The first step is to let Torque 3D's Project Generator know where the Leap Motion SDK is located.  The easiest way to do this is to add the `$LEAPMOTION_SDK_PATH` global variable to the top of your `project.conf` file.  For example:

`$LEAPMOTION_SDK_PATH = "C:\Users\dwyand_2\Downloads\LeapMotion\Leap_Developer_Kit_0.7.1_Windows\Leap_SDK";`

You may also create a Windows environmental variable named `TORQUE_LEAPMOTION_PATH` that also provides an absolute path to the Leap Motion SDK.  Going this route doesn't store the path within the `project.conf` file, which may be required if multiple developers are working on the same project.

The second addition to your `project.conf` file is a reference to the Torque 3D's Project Generator module for the Leap Motion.  Add the following between the `Torque3D::beginConfig()` and `Torque3D::endConfig()` lines:

```
    // Include Leap Motion module
    includeModule( 'leapMotion' );
```

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
$TORQUE_EXTENDED_MOVE = true;

// Our path to the Leap Motion SDK:
$LEAPMOTION_SDK_PATH = "C:\Users\dwyand_2\Downloads\LeapMotion\Leap_Developer_Kit_0.7.1_Windows\Leap_SDK";

// Configure Torque 3D
Torque3D::beginConfig( "win32", "MarbleMotion" );

    // Include Leap Motion module
    includeModule( 'leapMotion' );
        
    // Enable for optional minidump debugging support
    // addProjectDefine( 'TORQUE_MINIDUMP' );
        
Torque3D::endConfig();

?>
```

With these changes in place you may run your project's `generateProjects.bat` file to rebuild the various Visual Studio files.