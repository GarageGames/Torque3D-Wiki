The `ExtendedMove` class expands on the standard `Move` class that is used by various `GameBase` classes, such as the `Player` class.  The `ExtendedMove` class adds support for absolute positions (in millimeters) and rotations to be passed from the client to the server.  This makes it easier to support new input devices such as the [Leap Motion](Leap-Motion) controller in multiplayer environments where the server must validate all moves.

The files for the `ExtendedMove` class and its support classes may be found under the [T3D/gameBase/extended/](https://github.com/GarageGames/Torque3D/tree/development/Engine/source/T3D/gameBase/extended) directory.  In order to make use of the `ExtendedMove` class in your own project you will need to modify your project's `buildFiles/config/project.conf` file to pass along the `$TORQUE_EXTENDED_MOVE` variable to Torque 3D's Project Generator.  Specifically you'll want to add the following to the top of your `project.conf` file:

```
// Set this to true to enable the ExtendedMove class.  This
// allows the passing of absolute position and rotation input
// device information from the client to the server.
$TORQUE_EXTENDED_MOVE = true;
```

After making this change you will need to run your project's `generateProjects.bat' file to rebuild the Visual Studio files.  Here is a complete example of a `project.conf` file with the required change, along with Leap Motion controller support:

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


