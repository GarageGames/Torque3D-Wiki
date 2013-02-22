The new Torque 3D Razer Hydra input device provides a number of input events that may be used with Torque 3D's action map system. There are a number of different ways to use the Razer Hydra input device, which are set up using global TorqueScript variables.

## Action Map Device Type ##

When binding a TorqueScript function to a Razer Hydra input event using Torque 3D's action map system, the device name to use is `razerhydra`.  As only one Razer Hydra may be used on a computer at a time, there is no need to append a device instance number to the end of the device name.  The following is an example of setting up a proper action map binding:

```
moveMap.bind(razerhydra, rh_trigger1, gamepadFire);
```

## Standard Gamepad Input Events ##

The Razer Hydra provides a full compliment of gamepad buttons and sticks spread across two hand held controllers.  Torque 3D provides complete access to all of these input events which behave as you would expect from a Xbox 360 compatible gamepad.  The following action map input events are available:
