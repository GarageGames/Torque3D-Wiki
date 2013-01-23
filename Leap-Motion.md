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

Before you may run your freshly compiled game you will need to include the appropriate Leap Motion DLLs with your game's executable.  As of the Leap Motion SDK v0.7.1 these files are located in the `Leap_SDK/lib/x86` directory.  Specifically you should copy the `Leap.dll` (the release library) and `Leapd.dll` (the debug library) into the same directory as your game's executable.  When it comes time to release your game you only need to include the 'Leap.dll' library.

### Using the Leap Motion Controller ###

The new Torque 3D Leap Motion input device provides a number of input events that may be used with Torque 3D's action map system.  There are a number of different ways to use the Leap Motion input device, which are set up using global TorqueScript variables.

##### Hand and Finger Input Events #####

Torque 3D may provide absolute position and rotation information on any hands within the Leap Motion controller's view, along with any fingers on the hands (known as pointables in the Leap Motion SDK).  In order to receive these events the `$LeapMotion::GenerateIndividualEvents` global TorqueScript variable should be set to `true` (the default).  The default configuration is to support up to two and and five pointables per hand.  These totals may be changed in `source/platform/input/leapMotion/leapMotionConstants.h`.

The following action map input events are available (all rotations are in angled axis format):

*Hand 1*  
`lm_hand1` - absolute position  
`lm_hand1rot` - absolute rotation  
`lm_hand1point1` - absolute finger 1 position  
`lm_hand1point1rot` - absolute finger 1 rotation  
`lm_hand1point2` - absolute finger 2 position  
`lm_hand1point2rot` - absolute finger 2 rotation  
`lm_hand1point3` - absolute finger 3 position  
`lm_hand1point3rot` - absolute finger 3 rotation  
`lm_hand1point4` - absolute finger 4 position  
`lm_hand1point4rot` - absolute finger 4 rotation  
`lm_hand1point5` - absolute finger 5 position  
`lm_hand1point5rot` - absolute finger 5 rotation  

*Hand 2*  
`lm_hand2` - absolute position  
`lm_hand2rot` - absolute rotation  
`lm_hand2point1` - absolute finger 1 position  
`lm_hand2point1rot` - absolute finger 1 rotation  
`lm_hand2point2` - absolute finger 2 position  
`lm_hand2point2rot` - absolute finger 2 rotation  
`lm_hand2point3` - absolute finger 3 position  
`lm_hand2point3rot` - absolute finger 3 rotation  
`lm_hand2point4` - absolute finger 4 position  
`lm_hand2point4rot` - absolute finger 4 rotation  
`lm_hand2point5` - absolute finger 5 position  
`lm_hand2point5rot` - absolute finger 5 rotation  

Two additional TorqueScript global variables control how the hands and fingers the Leap Motion controller sees are mapped to these events.  The current Leap Motion SDK doesn't map physical hands and fingers to any particular index so you will need to decide which of the follow methods work for your application.

With both the `$LeapMotion::KeepHandIndexPersistent` and `$LeapMotion::KeepPointableIndexPersistent` global variables set to `false` (the default) the input event index for each visible hand and finger is determined by the Leap Motion SDK.

For example, if the user places their right hand in view of the Leap Motion controller then its events will occur on the `lm_hand1` and `lm_hand1rot` events.  If the user then places their left hand beside their right hand, then the left hand may be mapped to the second event index, or it could take over the first event index and the right now will now shift to the second event index (`lm_hand2` and `lm_hand2rot`).  This mapping is up to the Leap Motion SDK, and also occurs for the fingers in view.

When the `$LeapMotion::KeepHandIndexPersistent` global variable is set to `true` then Torque 3D makes use of the Leap Motion SDK's persistent ID system.  When a hand or finger enters the Leap Motion controller's field of view it is internally assigned an ID.  The Leap Motion then attempts to maintain that ID although it is possible for this ID tracking to be lost and reaquired under another ID (the hand or figure could be obscured by another object, they could leave the controller's field of view, etc.).

So long as the Leap Motion SDK can maintain a hand's persistent ID then Torque 3D will ensure that its input event index remains the same (again, only when `$LeapMotion::KeepHandIndexPersistent` is `true`).  For example, if the right hands first enters the controller's field of view then it will be assigned the first index (the `lm_hand1` and `lm_hand1rot` events).  And if the left hand is detected then it will be assigned to the second event index.  Now if the right hand leaves the controller's field of view rather than the left hand now taking on the first index, it will remain at the second event index (the `lm_hand2` and `lm_hand2rot` events).

When the `$LeapMotion::KeepPointableIndexPersistent` global variable is set to `true` then Torque 3D also makes use of the persistent ID system with the hand's fingers.  In order for this finger tracking to work the hands must also be tracked with `$LeapMotion::KeepHandIndexPersistent` set to `true`.

##### Using Hand and Finger Input Events #####

You bind the Leap Motion input events to an action map just like any other input event.  Specifically, you tie the events to the `leapmotion` device when with the action map `bind()` method.  Here is an example of making use of the position and rotation events generated when a hand is being tracked by the Leap Motion controller (place it in `scripts/client/default.bind.cs`):

```
function LMHandPos1(%x, %y, %z)
{
   // Output the absolute position of the first hand to the console:
   echo("Hand 1 position in millimeters:" SPC %x SPC %y SPC %z);
}

function LMHandRot1(%x, %y, %z, %a)
{
   // Output the absolute rotation of the first hand to the console:
   echo("Hand 1 rotation as angled axis:" SPC %x SPC %y SPC %z SPC %a);

   // Convert into a world space forward vector
   %pos = "0 0 0";
   %rot = %x SPC %y SPC %z SPC %a;
   %transform = MatrixCreate( %pos, %rot );
   %forward = MatrixMulVector( %transform, "0 1 0" );
   echo("Hand 1 world forward vector:" SPC %forward.x SPC %forward.y SPC %forward.z);
}

$LeapMotion::GenerateIndividualEvents = true;
moveMap.bind( leapmotion, lm_hand1, LMHandPos1);
moveMap.bind( leapmotion, lm_hand1rot, LMHandRot1);
```

##### Hand as Thumb Stick Events #####

Torque 3D allows a hand detected by the Leap Motion controller to be used like a gamepad thumb stick.  To activate these input events we set the `$LeapMotion::GenerateSingleHandRotationAsAxisEvents` global TorqueScript variable to `true`.  With that variable set the following action map input events are available:

`lm_handaxisx`
`lm_handaxisy



