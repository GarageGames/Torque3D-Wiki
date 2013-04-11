The Oculus Rift has a number of special requirements in order to render your application on its display.  The first is that it requires side-by-side stereo images (one for each eye) which effectively means you are rendering each frame twice.  The second requirement is that for each eye's view you need to render from a slightly different world position (the distance between the eyes).

The third requirement is that the perspective projection needs to take place off center.  With a normal render this perspective projection is set to the center of the view.  However, as a user's eyes do not line up with the center of the Rift's half-panel this offset needs to be taken into account.

Finally, the Oculus Rift's optics require that a barrel distortion be perform on the rendered frame prior to it being displayed.  This distortion needs to occur separately for each eye.
