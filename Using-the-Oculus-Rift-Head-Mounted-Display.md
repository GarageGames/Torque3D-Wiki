The Oculus Rift has a number of special requirements in order to render your application on its display.  The first is that it requires side-by-side stereo images (one for each eye) which effectively means you are rendering each frame twice.  The second requirement is that for each eye's view you need to render from a slightly different world position (the distance between the eyes) in order to have a true stereo view.

The third requirement is that the perspective projection needs to take place off center.  With a normal render this perspective projection is set to the center of the view.  However, as a user's eyes do not line up with the center of the Rift's half-panel this offset needs to be taken into account.

Finally, the Oculus Rift's optics require that a barrel distortion be perform on the rendered frame prior to it being displayed.  This distortion needs to occur separately for each eye.

Fortunately, all of this is taken care of by Torque 3D with a little set up.

## Setting Up Your Application ##

There are a number of support functions in (core/scripts/client/oculusVR.cs)[https://github.com/GarageGames/Torque3D/blob/development/Templates/Full/game/core/scripts/client/oculusVR.cs] that help you get your application ready for displaying on the Oculus Rift.  We will be referencing these functions throughout this section.

### Step 1: Preparing the Canvas ###

The Oculus Rift is treated as a separate monitor by your computer.  Often users will have this set up as an extension to their desktop, but it may also be set to mirror their desktop.  In either case, when you have your application go full screen you will want it appear on the Rift's display.  The way we do this is by informing Torque 3D that we would like to favour the graphics adapter that is attached to the Rift.

Fortunately, we can just use the `pointCanvasToOculusVRDisplay()` function and it will take care of this set up.  We need to call this function just before the *Canvas* (the main application window) is created.  We do this by adding the function to the `createCanvas()` function in `main.cs`:

```
function createCanvas(%windowTitle)
{
   if ($isDedicated)
   {
      GFXInit::createNullDevice();
      return true;
   }

   // For Rift
   pointCanvasToOculusVRDisplay();
   
   // Create the Canvas
   %foo = new GuiCanvas(Canvas);
   
   // Set the window title
   if (isObject(Canvas))
      Canvas.setWindowTitle(getEngineName() @ " - " @ $appName);
   
   return true;
}
```

### Step 2: Prepare for Rendering to the Rift ###

Before we can render to the Rift we need to tell Torque 3D about the correct field of view to use, what the eye offsets are, etc.  We also need to enable side-by-side stereo rendering as well as the barrel distortion shader to account for the Rift's lenses.

Fortunately we can just call the `enableOculusVRDisplay()` helper function and it performs this work for us.  A good place to do this is in `GameConnection::initialControlSet()` in `scripts/client/serverConnection.cs` just before you switch to the *PlayGui* GUI control.

```
function GameConnection::initialControlSet(%this)
{
   echo ("*** Initial Control Object");

   // The first control object has been set by the server
   // and we are now ready to go.
   
   // first check if the editor is active
   if (!isToolBuild() || !Editor::checkActiveLoadDone())
   {
      if (Canvas.getContent() != PlayGui.getId())
      {
         // For Rift
         enableOculusVRDisplay(%this, true);
         
         Canvas.setContent(PlayGui);
      }
   }
}
```

### Step 3: Setup a Control Scheme ###

A control scheme is something new for Torque 3D and is something you set on the *GameConnection* at either the client or server.  This tells any game objects that the *GameConnection* controls what to expect for input events and how to make use of them.  For the Rift we need to turn on an absolute rotation control scheme (which also required using the `ExtendedMove` class).

Often we want to also add the mouse or gamepad relative rotation to that obtained from the Rift's head tracker.  This allows for a user to rotate all the way around in-game without having to turn all the way around in the chair or while standing.

To modify the control scheme for a *GameConnection* we need to call its `setControlSchemeParameters()` method.  Fortunately, we can also use the `setStandardOculusVRControlScheme()` helper function which sets up for Rift head tracking and heading input from the mouse or gamepad.  You can call this at any time but a convienent place is during `GameConnection::initialControlSet()` right after `enableOculusVRDisplay()`:

```
function GameConnection::initialControlSet(%this)
{
   echo ("*** Initial Control Object");

   // The first control object has been set by the server
   // and we are now ready to go.
   
   // first check if the editor is active
   if (!isToolBuild() || !Editor::checkActiveLoadDone())
   {
      if (Canvas.getContent() != PlayGui.getId())
      {
         // For Rift
         enableOculusVRDisplay(%this, true);
         setStandardOculusVRControlScheme(%this);
         
         Canvas.setContent(PlayGui);
      }
   }
}
```

### Step 4: Setup Up The Action Map ###

In order to pass along the Rift's head tracking to Torque 3D's input system we need to set up an action map.  When using the control scheme talked about above, we need to reference the `ExtendedMove` class' global input variables to pass along the data.  We also want to set the Rift's input events to generate Euler angles rather than an angled axis.  All of this may be done in `default.bind.cs`:

```
// ----------------------------------------------------------------------------
// Oculus Rift
// ----------------------------------------------------------------------------

function OVRSensorRotEuler(%pitch, %roll, %yaw)
{
   //echo("Sensor euler: " @ %pitch SPC %roll SPC %yaw);
   $mvRotZ0 = %yaw;
   $mvRotX0 = %pitch;
   $mvRotY0 = %roll;
}

$mvRotIsEuler0 = true;
$OculusVR::GenerateAngleAxisRotationEvents = false;
$OculusVR::GenerateEulerRotationEvents = true;
moveMap.bind( oculusvr, ovr_sensorrotang0, OVRSensorRotEuler );
```

