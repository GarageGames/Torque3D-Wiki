The new Torque 3D Oculus Rift input device provides a number of head tracking sensor input events that may be used with Torque 3D's action map system. There are a few different ways to use the Oculus Rift input device, which are set up using global TorqueScript variables.

## Action Map Device Type ##

When binding a TorqueScript function to an Oculus Rift sensor input event using Torque 3D's action map system, the device name to use is `oculusvr`.  As all connected Oculus Rift sensors and any stand alone sensors are handled through the same input device there is no need to append a device instance number to the end of the device name.  The following is an example of setting up a proper action map binding:

```
moveMap.bind( oculusvr, ovr_sensorrotang0, OVRSensorRotEuler );
```
