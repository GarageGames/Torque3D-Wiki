Before you can make use of the Oculus Rift in Torque 3D you will need to download the SDK from their [web site](http://developer.oculusvr.com) and extract it to a convenient directory.  To date, version 0.1.5 of the OculusVR SDK has been tested with Torque 3D.

### Configure Your project.conf ###

With the OculusVR SDK in place, you will need to modify your project's `buildFiles/config/project.conf` file in a text editor.  The first step is to let Torque 3D's Project Generator know where the OculusVR SDK is located.  The easiest way to do this is to add the `$OCULUSVR_SDK_PATH` global variable to the top of your `project.conf` file.  For example:

`$OCULUSVR_SDK_PATH = "C:\Users\dwyand_2\Downloads\OculusRift\ovr_sdk_0.1.5_src\OculusSDK";`

You may also create a Windows environmental variable named `TORQUE_OCULUSVR_PATH` that also provides an absolute path to the OculusVR SDK.  Going this route doesn't store the path within the `project.conf` file, which may be required if multiple developers are working on the same project.

The second addition to your `project.conf` file is a reference to the Torque 3D's Project Generator module for the Oculus Rift.  Add the following between the `Torque3D::beginConfig()` and `Torque3D::endConfig()` lines:

```
    // Include Oculus Rift module
    includeModule( 'oculusVR' );
```

With these changes in place you may run your project's `generateProjects.bat` file to rebuild the various Visual Studio files.
