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
    <tr>
        <td>AI System - Navgraph, planner, fuzzy state machine</td>
        <td>Create a framework for a comprehensive AI system, provide Navgraph for terrain and interiors spaces. Design a component system where a planner, state machine or flocking system could be used to control the AI. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3266445-ai-system-navgraph-planner-fuzzy-state-machine">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Update the Terrain System</td>
        <td>Change the terrain system so that there are better and more modern tools like those in UDK. This included better blending between textures, and the ability to use diffuse, normal, spec, and other textures together. Also, add some tools to the terrain editor, like the ability to make ramps. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3269267-update-the-terrain-system">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>DX11 Support</td>
        <td>Update much of the rendering to support DX11 and some of it's features. Obviously this is a big task, but keeping up on DirectX versions I think is important to stay current. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3311334-dx11-support">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Inverse Kinematics for character animation</td>
        <td>Other engines have used this for a while to place characters' feet on the ground. I'd love to be able to use it to animate things like holding weapons as well. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3266894-inverse-kinematics-for-character-animation">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>GUI system Overhaul for Torque 3D</td>
        <td><a href="http://blogs.unity3d.com/2012/06/29/the-new-gui/">http://blogs.unity3d.com/2012/06/29/the-new-gui/</a> The Torque 3D GUI System needs some work. Maybe something similar to Scale form or Awesomium but built into T3D. Something that can call Adobe Flash files or the open source equivalent. Maybe something like Unity3D's New GUI? Either way the GUI system needs an update. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3266596-gui-system-overhaul-for-torque-3d">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Create an Open Source Alternative to Torsion</td>
        <td>Torsion is currently old and buggy, but there is no alternative to it if you need a script debugger. Either create a new TorqueScript IDE, or modify existing plugins/IDEs to include some of the more advanced functionality of Torsion. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3269278-create-an-open-source-alternative-to-torsion">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Global Illumination</td>
        <td>Built in GUI for Global Illumination will greatly increase the quality of the final game-product. Production time is saved by not having to swap between 3rd-Party programs to bake level environment maps. Intuitive (layers of control) for light, shadow, atlas maps. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3267036-global-illumination">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Export to mobile platforms</td>
        <td>Torque3D should be able to deploy to Android, WM8, iOS and other platforms the same way Unity3D or other engines. Even if this is done through an embedded VM layer. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3291079-export-to-mobile-platforms">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>3d skybox</td>
        <td>Can be use to fake big epic scenes. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3336772-3d-skybox">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Animation Blending</td>
        <td>Animation Blending for characters. There is already an opensource project that can help with this but i don't know if it's compatible with the MIT License. <a href="http://sourceforge.net/projects/tecnofreakanima/">http://sourceforge.net/projects/tecnofreakanima/</a>
 From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3268129-animation-blending">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Better support for MinGW compilers</td>
        <td>I've been thrilled by the release of Torque 3D under MIT license! Since then I was trying to get the engine to compile under MinGW (GCC) compilers under windows, and so far the adapting was a success. It compiles, however it crashes at some point during some floating point operations. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3268908-better-support-for-mingw-compilers">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>hitboxes aka locational damage</td>
        <td>A way to track or identify incoming damage to a location. It can be used with tanks, flight sims, big stompy robots, armored locations and tracking damage to limbs. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3270366-hitboxes-aka-locational-damage">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>64 bit build</td>
        <td>It seems like a 64 bit build target for Windows is something that's long overdue as most people have machines with 8Gb of RAM or more these days. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3280647-64-bit-build">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>CgFX Shader Language integration</td>
        <td>From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3266386-cgfx-shader-language-integration">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Multiple Viewports in World Editor</td>
        <td>Torque3D v.1.2 currently uses only one camera viewport that may be toggled in the editor. This one view navigation method uses more mouse clicks and time on development. Like any other standard 3D package software, multiple viewports allow total user navigation & view control over objects and the world. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3351219-multiple-viewports-in-world-editor">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Advanced snapping options</td>
        <td>A lot of games, especially modern ones use modular systems for building levels, so it is important to have proper snapping options in the game editor. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3929242-advanced-snapping-options">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Convert data serialization over to use TAML</td>
        <td>One of the biggest dependencies on TorqueScript currently is the data serialization (datablocks, materials, etc). Migrating the data serialization to an scripting independent format (like TAML) would go a long way towards making the engine more flexible for use with other languages or being embedded as a framework. It would also pave the way for smarter asset packaging and asynchronous asset loading. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3269229-convert-data-serialization-over-to-use-taml">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Play through web page, with streaming capabilities</td>
        <td>A web page streaming technology like Unity's that allows the game to be played through web page but not require the whole game package to be downloaded. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3266475-play-through-web-page-with-streaming-capabilities">feature request</a>.</td>
        <td></td>
    </tr>
</table>
