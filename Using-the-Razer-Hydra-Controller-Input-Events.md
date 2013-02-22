The new Torque 3D Razer Hydra input device provides a number of input events that may be used with Torque 3D's action map system. There are a number of different ways to use the Razer Hydra input device, which are set up using global TorqueScript variables.

## Action Map Device Type ##

When binding a TorqueScript function to a Razer Hydra input event using Torque 3D's action map system, the device name to use is `razerhydra`.  As only one Razer Hydra may be used on a computer at a time, there is no need to append a device instance number to the end of the device name.  The following is an example of setting up a proper action map binding:

```
moveMap.bind(razerhydra, rh_trigger1, gamepadFire);
```

## Standard Gamepad Input Events ##

The Razer Hydra provides a full compliment of gamepad buttons and sticks spread across two hand held controllers.  Torque 3D provides complete access to all of these input events which behave as you would expect from a Xbox 360 compatible gamepad.  The following action map input events are available:

**Left Controller**
* `rh_thumbx0` - thumb stick x-axis motion in the range of -1.0 to 1.0
* `rh_thumby0` - thumb stick y-axis motion in the range of -1.0 to 1.0
* `rh_trigger0` - trigger motion (sometimes referred to as z-axis motion) in the range of 0.0 to 1.0
* `rh_shoulder0` - shoulder (or bumper) button
* `rh_thumb0` - thumb stick used as a button
* `rh_start0` - start button
* `rh_1button0` - 1 button
* `rh_2button0` - 2 button
* `rh_3button0` - 3 button
* `rh_4button0` - 4 button

**Right Controller**
* `rh_thumbx1` - thumb stick x-axis motion in the range of -1.0 to 1.0
* `rh_thumby1` - thumb stick y-axis motion in the range of -1.0 to 1.0
* `rh_trigger1` - trigger motion (sometimes referred to as z-axis motion) in the range of 0.0 to 1.0
* `rh_shoulder1` - shoulder (or bumper) button
* `rh_thumb1` - thumb stick used as a button
* `rh_start1` - start button
* `rh_1button1` - 1 button
* `rh_2button1` - 2 button
* `rh_3button1` - 3 button
* `rh_4button1` - 4 button
