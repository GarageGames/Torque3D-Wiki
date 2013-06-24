Herein we maintain a list of what individual community members will be contributing toward the Torque 3D MIT codebase.

<table>
    <tr>
        <td><b>Item</b></td>
        <td><b>Description</b></td>
        <td><b>Community Member(s)</b></td>
    </tr>
    <tr>
        <td>Cppcheck static code analysis</td>
        <td>Use <a href="http://cppcheck.sourceforge.net/">Cppcheck</a> to perform a static analysis of Torque 3D's code base. This could be broken up into smaller items.</td>
        <td></td>
    </tr>
    <tr>
        <td>Compile warnings clean-up</td>
        <td>Turn on compiler warnings and resolve them.  This could be broken up into smaller items.</td>
        <td></td>
    </tr>
    <tr>
        <td>Update to the latest Bullet library version</td>
        <td>Update the included <a href="http://bulletphysics.org/wordpress/">Bullet library</a> to the latest version.  v2.81 would likely be the best one to start with.  Could look into 3.x integration.</td>
        <td></td>
    </tr>
    <tr>
        <td>Update PhysX support to the latest 3.x version</td>
        <td>Update Torque 3D's PhysX support for the latest <a href=https://developer.nvidia.com/physx-downloads">PhysX 3.x</a> version.</td>
        <td></td>
    </tr>
    <tr>
        <td>Master server updated to T3D</td>
        <td>The Master Server code was written for TGE and should be updated for T3D and included in the repository. This also requires the proper build files for at least Linux.</td>
        <td><a href="http://www.garagegames.com/account/profile/70027">smally</a></td>
    </tr>
    <tr>
        <td>OSX platform support</td>
        <td>’Codecandy’ OS X work ported to T3D MIT with complete basic lighting support. Also talked about in this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3266408-add-full-support-for-mac-os-x-to-torque-3d">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Linux platform support</td>
        <td>Linux client basic lighting support. Also talked about in this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3266405-add-full-support-for-linux-operating-systems-to-to">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>OBJ mesh file import support</td>
        <td>Expand T3D's graphics pipeline to include loading in <i>.obj</i> files and converting them to DTS.</td>
        <td></td>
    </tr>
    <tr>
        <td>FBX file import support</td>
        <td>Expand T3D's graphics pipeline to include loading in FBX files and converting them to DTS.</td>
        <td></td>
    </tr>
    <tr>
        <td>Image file support</td>
        <td>Expand T3D's graphics pipeline by including support for new image file formats (such as Photoshop). This could be broken up into one task per image format.</td>
        <td></td>
    </tr>
    <tr>
        <td>Multiple CPU Core Usage (for skinned meshes especially)</td>
        <td>T3D still utilizes only a single CPU core, and skinned meshes have to be written/animated/rendered/exist/whatever on it. Who doesn't have at least a dual core machine these days? From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3268362-multiple-cpu-core-usage-for-skinned-meshes-especi">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>A new scripting language</td>
        <td>This would be in addition to TorqueScript, but for a more mainstream language like Lua or Javascript. Bonus points if it's written in such a way that additional languages could be added later. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3266218-a-new-scripting-language">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Shader Composer / Material Editor</td>
        <td>Some kind of Node-based Material Editor, would be nice. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3266379-shader-composer-material-editor">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Open GL 4.x support for Torque3D</td>
        <td>This would enable to port Torque 3D to other operating systems that are not dependent on direct3d. Operating systems such as Linux and Mac OSX. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3266552-open-gl-4-x-support-for-torque3d">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>A system like kismet from unreal engine 3</td>
        <td>For a quick way to test new ideas very easy. <a href="http://www.unrealengine.com/en/features/kismet/">http://www.unrealengine.com/en/features/kismet/</a>
 From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3266165-a-system-like-kismet-from-unreal-engine-3">feature request</a>.</td>
        <td></td>
    </tr>
</table>
