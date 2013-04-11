The new Torque 3D Oculus Rift input device provides a number of head tracking sensor input events that may be used with Torque 3D's action map system. There are a few different ways to use the Oculus Rift input device, which are set up using global TorqueScript variables.

## Action Map Device Type ##

When binding a TorqueScript function to an Oculus Rift sensor input event using Torque 3D's action map system, the device name to use is `oculusvr`.  As all connected Oculus Rift sensors and any stand alone sensors are handled through the same input device there is no need to append a device instance number to the end of the device name.  The following is an example of setting up a proper action map binding:

```
moveMap.bind( oculusvr, ovr_sensorrotang0, OVRSensorRotEuler );
```

## Sensor Absolute Rotation Events ##

The OculusVR sensor is able to detect an absolute rotation in space.  This means that the sensor that is included within the Oculus Rift head mounted display is able to report the head's absolute rotation.  While in theory the OculusVR SDK supports more than one sensor plugged into your computer, individual sensors are not currently available for testing.  Because of this Torque 3D currently only supports a single OculusVR sensor -- the one that is within the Oculus Rift.  This sensor is reported as index `0`.  It is straight forward to expand the number of supported sensors when and if Oculus starts offering individual ones for sale.

Sensor rotation events may be reported in two different way: using an angled axis or using Euler angles.  One or both of these forms may be chosen and it depends on your own application.  To activate the angled axis form of rotation reporting you may set the TorqueScript global variable `$OculusVR::GenerateAngleAxisRotationEvents` to `true`.  To activate the Euler angle form, set the TorqueScript global variable `$OculusVR::GenerateEulerRotationEvents` to `true`.

The following action map input events are available depending on how these two global variables are set:

* `ovr_sensorrot0` - Absolute rotation in angled axis form (vector plus angle)
* `ovr_sensorrotang0` - Absolute rotation in Euler angle form (about x, y, and z axis)
