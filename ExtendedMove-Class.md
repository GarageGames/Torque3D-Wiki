The `ExtendedMove` class expands on the standard `Move` class that is used by various `GameBase` classes, such as the `Player` class.  The `ExtendedMove` class adds support for absolute positions (in millimeters) and rotations to be passed from the client to the server.  This makes it easier to support new input devices such as the [Leap Motion](Leap-Motion) controller in multiplayer environments where the server must validate all moves.

### Configure Your project.conf ###

The files for the `ExtendedMove` class and its support classes may be found under the [T3D/gameBase/extended/](https://github.com/GarageGames/Torque3D/tree/development/Engine/source/T3D/gameBase/extended) directory.  In order to make use of the `ExtendedMove` class in your own project you will need to modify your project's `buildFiles/config/project.conf` file to pass along the `$TORQUE_EXTENDED_MOVE` variable to Torque 3D's Project Generator.  Specifically you'll want to add the following to the top of your `project.conf` file:

```
// Set this to true to enable the ExtendedMove class.  This
// allows the passing of absolute position and rotation input
// device information from the client to the server.
$TORQUE_EXTENDED_MOVE = true;
```

After making this change you will need to run your project's `generateProjects.bat' file to rebuild the Visual Studio files.

### Example project.conf ###

Here is a complete example of a `project.conf` file with the required change, along with Leap Motion controller support:

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

### Use With Other Move Classes ###

Using the `ExtendedMove` class is an all or nothing proposition.  You either have your application compiled with it, or you don't.  When you make use of it in your project, it is in place of the standard `Move` class and therefore its special properties may be accessed from any other `GameBase` class.

This operates in the same way that HiFi networking does, which also takes over how the `Move` class and its support classes operate.  This means that you cannot have both `ExtendedMove` support and HiFi networking active at the same time.

### Passing Data to the ExtendedMove Class ###

As the `ExtendedMove` class is an extension of the standard `Move` class all of the usual global input variables are still available.  So you would still use `$mvTriggerCount0` to activate the first trigger, for example.

Beyond these standard global input variables, the `ExtendedMove` class adds a number of global input variable to handle absolute position and rotation values.  By default, the `ExtendedMove` class supports three sets of positions and rotations.  This is enough for two hands when using the Leap Motion controller, or for head tracking from the Oculus Rift plus two hands using a Razer Hydra.  Additional sets may be added by modifying the ExtendedMove::MaxPositionsRotations constant and recompiling.

The following global input variables are available with the `ExtendedMove` class to pass along absolute position:

**First Set**
* `$mvPosX0` - X position in millimeters
* `$mvPosY0` - Y position in millimeters
* `$mvPosZ0` - Z position in millimeters

**Second Set**
* `$mvPosX1` - X position in millimeters
* `$mvPosY1` - Y position in millimeters
* `$mvPosZ1` - Z position in millimeters

**Third Set**
* `$mvPosX2` - X position in millimeters
* `$mvPosY2` - Y position in millimeters
* `$mvPosZ2` - Z position in millimeters

When it comes to rotation there are a couple of options available on a per set basis.  An absolute rotation may be passed in as either a Euler angle (heading, pitch, bank) or as an angled axis (a vector and a rotation about the vector).  The following global input variables are used to determine how the rotations are represented:

* `$mvRotIsEuler0` - If true then the first set uses Euler angles
* `$mvRotIsEuler1` - If true then the second set uses Euler angles
* `$mvRotIsEuler2` - If true then the third set uses Euler angles

When using Euler angle rotations (the set's `$mvRotIsEulerN` is `true`) the following global input variable are available:

**First Set**
* `$mvRotX0` - Pitch rotation in degrees
* `$mvRotY0` - Bank rotation in degrees
* `mvRotZ0` - Heading rotation in degrees

**Second Set**
* `$mvRotX1` - Pitch rotation in degrees
* `$mvRotY1` - Bank rotation in degrees
* `mvRotZ1` - Heading rotation in degrees

**Third Set**
* `$mvRotX2` - Pitch rotation in degrees
* `$mvRotY2` - Bank rotation in degrees
* `mvRotZ2` - Heading rotation in degrees

### GameBase Classes And ExtendedMove ###

Currently there are no `GameBase` classes that support the new properties of the `ExtendedMove` class.  You will need to implement support for the `ExtendedMove` class yourself as your project requries.  This could be in the form of a modified `Player` class, or something completely new.

