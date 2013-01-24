The new Torque 3D Leap Motion input device provides a number of input events that may be used with Torque 3D's action map system.  There are a number of different ways to use the Leap Motion input device, which are set up using global TorqueScript variables.

## Hand and Finger Input Events ##

Torque 3D may provide absolute position and rotation information on any hands within the Leap Motion controller's view, along with any fingers (or tools) on the hands (known as pointables in the Leap Motion SDK).  In order to receive these events the `$LeapMotion::GenerateIndividualEvents` global TorqueScript variable should be set to `true` (the default).  The current configuration is to support up to two and and five pointables per hand.  These totals may be changed in the source code file  [platform/input/leapMotion/leapMotionConstants.h](https://github.com/GarageGames/Torque3D/blob/development/Engine/source/platform/input/leapMotion/leapMotionConstants.h).

The following action map input events are available (all positions are in millimeters and all rotations are in angled axis format):

**Hand 1**
* `lm_hand1` - absolute position
* `lm_hand1rot` - absolute rotation

**Hand 1 Pointables**
* `lm_hand1point1` - absolute finger 1 position
* `lm_hand1point1rot` - absolute finger 1 rotation
* `lm_hand1point2` - absolute finger 2 position
* `lm_hand1point2rot` - absolute finger 2 rotation
* `lm_hand1point3` - absolute finger 3 position
* `lm_hand1point3rot` - absolute finger 3 rotation
* `lm_hand1point4` - absolute finger 4 position
* `lm_hand1point4rot` - absolute finger 4 rotation
* `lm_hand1point5` - absolute finger 5 position
* `lm_hand1point5rot` - absolute finger 5 rotation

**Hand 2**
* `lm_hand2` - absolute position
* `lm_hand2rot` - absolute rotation

**Hand 2 Pointables**
* `lm_hand2point1` - absolute finger 1 position
* `lm_hand2point1rot` - absolute finger 1 rotation
* `lm_hand2point2` - absolute finger 2 position
* `lm_hand2point2rot` - absolute finger 2 rotation
* `lm_hand2point3` - absolute finger 3 position
* `lm_hand2point3rot` - absolute finger 3 rotation
* `lm_hand2point4` - absolute finger 4 position
* `lm_hand2point4rot` - absolute finger 4 rotation
* `lm_hand2point5` - absolute finger 5 position
* `lm_hand2point5rot` - absolute finger 5 rotation

Two additional TorqueScript global variables control how the hands and fingers the Leap Motion controller sees are mapped to these events.  The current Leap Motion SDK doesn't map physical hands and fingers to any particular index so you will need to decide which of the follow methods work for your application.  You may dynamically switch between these methods at any time.

With both the `$LeapMotion::KeepHandIndexPersistent` and `$LeapMotion::KeepPointableIndexPersistent` global variables set to `false` (the default) the input event index for each visible hand and finger is determined by the Leap Motion SDK.

For example, if the user places their right hand in view of the Leap Motion controller then its events will occur on the `lm_hand1` and `lm_hand1rot` events.  If the user then places their left hand beside their right hand, then the left hand may be mapped to the second event index, or it could take over the first event index and the right now will now shift to the second event index (`lm_hand2` and `lm_hand2rot`).  This mapping is up to the Leap Motion SDK, and also occurs for the fingers in view.

When the `$LeapMotion::KeepHandIndexPersistent` global variable is set to `true` then Torque 3D makes use of the Leap Motion SDK's persistent ID system.  When a hand or finger enters the Leap Motion controller's field of view it is internally assigned an ID.  The Leap Motion then attempts to maintain that ID although it is possible for this ID tracking to be lost and reacquired under another ID (the hand or figure could be obscured by another object, they could leave the controller's field of view, etc.).

So long as the Leap Motion SDK can maintain a hand's persistent ID then Torque 3D will ensure that its input event index remains the same (again, only when `$LeapMotion::KeepHandIndexPersistent` is `true`).  For example, if the right hands first enters the controller's field of view then it will be assigned the first index (the `lm_hand1` and `lm_hand1rot` events).  And if the left hand is detected then it will be assigned to the second event index.  Now if the right hand leaves the controller's field of view rather than the left hand now taking on the first index, it will remain at the second event index (the `lm_hand2` and `lm_hand2rot` events).

When the `$LeapMotion::KeepPointableIndexPersistent` global variable is set to `true` then Torque 3D also makes use of the persistent ID system with the hand's fingers.  In order for this finger tracking to work the hands must also be tracked with `$LeapMotion::KeepHandIndexPersistent` set to `true`.

### Using Hand and Finger Input Events ###

You bind the Leap Motion input events to an action map just like any other input event.  Specifically, you tie the events to the `leapmotion` device with the action map `bind()` method.  Here is an example of making use of the position and rotation events generated when a hand is being tracked by the Leap Motion controller (place it in `scripts/client/default.bind.cs`):

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

## Hand as Thumb Stick Input Events ##

Torque 3D allows a hand detected by the Leap Motion controller to be used like a gamepad thumb stick.  Imagine that a thumb stick is coming out of the top of your hand and you move it by tilting your hand.

To activate these thumb stick input events we set the `$LeapMotion::GenerateSingleHandRotationAsAxisEvents` global TorqueScript variable to `true`.  With that variable set the following action map input events are available:

`lm_handaxisx`  
`lm_handaxisy`  

Both of these events mimic the output from a gamepad thumb stick axis and are in the range of -1.0 to 1.0.  Internally, these x and y axis values are normalized to ensure the length of their vector is never more than 1, just like a real thumb stick.

In order to calculate the -1.0 to 1.0 range, the tilt of the hand with respect to a vector pointing straight up (technically this vector is normal to the plane of the Leap Motion controller's top surface) is used.  When this hand to up vector angle reaches the `$LeapMotion::MaximumHandAxisAngle` global script variable value (the default is 25 degrees) then the virtual thumb stick is considered all the way over.  Adjusting `$LeapMotion::MaximumHandAxisAngle` for your application determines how far over the user must tilt their hand for a 100% value.

Only one hand is supported at this time and the `$LeapMotion::KeepHandIndexPersistent` global variable determines how multiple hands are dealt with (see the discussion above about this variable).

### Using Hand as Thumb Stick Input Events ###

You bind the Leap Motion input events to an action map just like any other input event.  Specifically, you tie the events to the `leapmotion` device with the action map `bind()` method.  As these events operate like a gamepad thumb stick you may use any of the action map features with them, such as defining dead zones.  Dead zones are especially useful as they allow for some hand jitter in the rest position without generating input events.

For example, here is how you could use the Leap Motion controller to move the player around in one of the Torque 3D templates (place the script in `sciprts/client/default.bind.cs`):

```
$LeapMotion::GenerateSingleHandRotationAsAxisEvents= true;
moveMap.bind( leapmotion, lm_handaxisx, "D", "-0.23 0.23", gamePadMoveX );
moveMap.bind( leapmotion, lm_handaxisy, "D", "-0.23 0.23", gamePadMoveY );
```

These two bindings make use of the `gamePadMoveX` and `gamePadMoveY` functions already defined in `scripts/client/default.bind/cs`, which are also called when the player uses a Xbox 360 compatible gamepad.  These bindings also define a dead zone within the range of -0.23 to 0.23 where no input events will be generated.

## Whole Frame Input Events ##

There may be a time when the provided Leap Motion input events don't quite fit your needs.  In these cases you may make use of the Leap Motion whole frame input event that is available in Torque 3D.  To activate this input event you set the `$LeapMotion::GenerateWholeFrameEvents` global TorqueScript variable to `true`.  When active, you may then receive the `lm_frame` input event.

The `lm_frame` event is unique in that it provides a single value that is a SimObject ID to a `LeapMotionFrame` class instance.  You may then use this ID to call the instance's methods and retrieve the frame's data.

Each 'LeapMotionFrame' class instance is automatically stored within the `LeapMotionFrameGroup` SimGroup.  A maximum number of `LeapMotionFrame` objects are kept at any time as determined by the `$LeapMotion::MaximumFramesStored` global TorqueScript variable (the default is 30).  When a new `LeapMotionFrame` object is required, the oldest is removed from the `LeapMotionFrameGroup` and recycled.

The `LeapMotionFrame` instances are stored newest to oldest, with the newest at index 0 within the group.  When you receive a `lm_frame` event you may safely assume that the frame ID given in the frame's parameter is the first frame in the `LeapMotionFrameGroup`.  To manually retrieve the newest frame and the frame that came just before it (perhaps to perform a delta calculation between the two) you may use the following:

```
%newestFrame = LeapMotionFrameGroup.getObject(0);
%previousFrame = LeapMotionFrameGroup.getObject(1);
```

This may be done at any time that your application is running so long as you are collecting whole frames as set with the `$LeapMotion::GenerateWholeFrameEvents` global variable.

### Using Whole Frame Input Events ###

You bind the Leap Motion input events to an action map just like any other input event.  Specifically, you tie the events to the `leapmotion` device with the action map `bind()` method.  For example, the following TorqueScript code (placed in `scripts/client/default.bind.cs`) performs an action against each frame received by the input event:

```
function LMFrame(%id)
{
   // Output some information about this frame to the console
   echo( "Frame " @ %id @ " time: " @ %id.getFrameRealTime() @ " hands: " @ %id.getHandCount() );
}

$LeapMotion::GenerateWholeFrameEvents = true;
moveMap.bind( leapmotion, lm_frame, LMFrame);
```

The 'LeapMotionFrame' class has a large number of methods available for working with a frame's hands and pointables.  Please see the source code file [platform/input/leapMotion/leapMotionFrame.cpp](https://github.com/GarageGames/Torque3D/blob/development/Engine/source/platform/input/leapMotion/leapMotionFrame.cpp) for a complete list of the available methods.

## Miscellaneous Input Events ##

The `lm_framevaliddata` input event is generated the Leap Motion controller gains or loses all hand and pointable tracking information.  This transition may occur when the user places their hand over the controller and then removes it.  This event can be useful for changing the application's state, such as pausing when nothing is being tracked by the Leap Motion controller.

The `lm_framevaliddata` input event provides a single parameter that has a value of 1 when hand or pointable tracking data is available, and 0 when there is no longer any tracking data.  Here is an example of using this event:

```
function LMFrameValidData(%val)
{
   echo("Frame valid data: " @ %val);
}

moveMap.bind( leapmotion, lm_framevaliddata, LMFrameValidData);
```

This event is always available from the Leap Motion controller input device.

## Order of Input Events ##

The following is the order in which input events may be received by the application:

1. The `lm_framevaliddata` event.
2. If `$LeapMotion::GenerateIndividualEvents` is `true` then all individual hand and pointable events.
3. If `$LeapMotion::GenerateSingleHandRotationAsAxisEvents` is `true` then the `lm_handaxisx` and `lm_handaxisy` events, but only if these values have changed this frame compared to the previous frame.  This is the same behavior as with gamepad thumb sticks.
4. If `$LeapMotion::GenerateWholeFrameEvents` is `true` then the `lm_frame` event.

