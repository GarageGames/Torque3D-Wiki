The Oculus Rift has a number of special requirements in order to render your application on its display.  The first is that it requires side-by-side stereo images (one for each eye) which effectively means you are rendering each frame twice.  The second requirement is that for each eye's view you need to render from a slightly different world position (the distance between the eyes) in order to have a true stereo view.

The third requirement is that the perspective projection needs to take place off center.  With a normal render this perspective projection is set to the center of the view.  However, as a user's eyes do not line up with the center of the Rift's half-panel this offset needs to be taken into account.

Finally, the Oculus Rift's optics require that a barrel distortion be perform on the rendered frame prior to it being displayed.  This distortion needs to occur separately for each eye.

Fortunately, all of this is taken care of by Torque 3D with a little set up.

## Setting Up Your Application ##

There are a number of support functions in (core/scripts/client/oculusVR.cs)[https://github.com/GarageGames/Torque3D/blob/development/Templates/Full/game/core/scripts/client/oculusVR.cs] that help you get your application ready for displaying on the Oculus Rift.  We will be referencing these functions throughout this section.

### Step 1: Preparing the Canvas ###
