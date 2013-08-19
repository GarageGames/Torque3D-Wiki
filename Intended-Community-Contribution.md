Herein we maintain a list of what individual community members will be contributing toward the Torque 3D MIT codebase.
   
   
### Community Member Contributions Completed
These tasks have been completed by the community.
<table>
    <tr>
        <td><b>Item</b></td>
        <td><b>Description</b></td>
        <td><b>Pull Request</b></td>
        <td><b>Community Member(s)</b></td>
    </tr>
    <tr>
        <td>Basic recast/detour support in T3D</td>
        <td><a href="http://www.garagegames.com/community/forums/viewthread/134404">http://www.garagegames.com/community/forums/viewthread/134404</a></td>
        <td><a href="https://github.com/GarageGames/Torque3D/pull/431">PR 431</a>, <a href="https://github.com/GarageGames/Torque3D/pull/432">PR 432</a>, <a href="https://github.com/GarageGames/Torque3D/pull/433">PR 433</a></td>
        <td><a href="http://www.garagegames.com/account/profile/79478">Daniel Buckmaster</a></td>
    </tr>
    <tr>
        <td>Update to the latest Bullet library version</td>
        <td>Update the included <a href="http://bulletphysics.org/wordpress/">Bullet library</a> to the latest version.  v2.81 would likely be the best one to start with.  Could look into 3.x integration.</td>
        <td><a href="https://github.com/GarageGames/Torque3D/pull/434">PR 434</a></td>
        <td><a href="http://www.garagegames.com/account/profile/35699">Luis Anton Rebollo</a></td>
    </tr>
</table>

<center>![divider](images/IntendedCommunityContribution/separator.png)</center>

### Community Member Contributions In Progress
Please let the Steering Committee know about any contributions you would like to make.
<table>
    <tr>
        <td><b>Item</b></td>
        <td><b>Description</b></td>
        <td><b>Community Member(s)</b></td>
    </tr>
    <tr>
        <td>Master server updated to T3D</td>
        <td>The Master Server code was written for TGE and should be updated for T3D and included in the repository. This also requires the proper build files for at least Linux.</td>
        <td><a href="http://www.garagegames.com/account/profile/70027">smally</a></td>
    </tr>
    <tr>
        <td>Testing and improvement of the Improved Console Function branch</td>
        <td><a href="https://github.com/GarageGames/Torque3D/tree/consolefuncrefactor">https://github.com/GarageGames/Torque3D/tree/consolefuncrefactor</a></td>
        <td><a href="http://www.garagegames.com/account/profile/33917">Demolishun</a></td>
    </tr>
</table>

   
   
### Steering Committee Suggestions
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
        <td>Update PhysX support to the latest 3.x version</td>
        <td>Update Torque 3D's PhysX support for the latest <a href=https://developer.nvidia.com/physx-downloads">PhysX 3.x</a> version.</td>
        <td></td>
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
</table>
   
   
### Community Feature Requests
[Torque 3D Feature Request Page](https://garagegames.uservoice.com/forums/178972-torque-3d-mit) Many of these items do not show the entire description of the feature request.  Please click on the link to read the whole request.
<table>
    <tr>
        <td><b>Item</b></td>
        <td><b>Description</b></td>
        <td><b>Community Member(s)</b></td>
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
    <tr>
        <td>Use a Plug-in Architecture so all the Add-ons could work together</td>
        <td>Curenattly each add-on is patching manually or automatically the stock engine yet once you want more than one add-on at the same time you need to merge it from two add ons pattching two stock engines a task not suted for everyone. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3347683-use-a-plug-in-architecture-so-all-the-add-ons-coul">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Support for Intel Graphics Cards</td>
        <td>Most game engines support Intel cards for casual and indie games... and for games with graphics like cartoon, etc. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3321155-support-for-intel-graphics-cards">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Steps in the FPS Tutorial for how to compile Torque3D for the first time</td>
        <td>The FPS tutorial jumps straight from section 1 (setup) to section 2 (test torque 3d) without addressing the need to compile it. This may seem obvious to those well versed in C++ based projects, but the reality is that many people are not coming from that background, and want to just muddle through that part to get to the asset creation and scripting. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3573196-steps-in-the-fps-tutorial-for-how-to-compile-torqu">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Upgraded sketch tool</td>
        <td>Since the old way of level editing with tools like constructor and the old format of models, where you could have a tiling texturing is gone, an upgrade of the sketch tool to replace this lost function may be nice. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3929207-upgraded-sketch-tool">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>PhysX vehicle</td>
        <td>Implement a PhysX vehicle or make current vehicles be able to collide with PhysX actors. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3270970-physx-vehicle">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>More Full Featured templates/Starter kits</td>
        <td>I feel that it would do the community good if the game engine would come with more full featured templates/starter kits. the torque game engine is prolly one of the better game engines out there, when it comes to the most bang for your buck.(expecially now that it is free.) however, the FPS Tutorial, although it does give you a starting point. it lacks some of the key features that is needed to compete with todays market. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3289976-more-full-featured-templates-starter-kits">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Displacement map option</td>
        <td>I have difficulties creating a normal map for the parallax effect, but searching for tutorials, I have found that some engines use a separate displacement map texture channel to achieve this. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3269768-displacement-map-option-">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>XMLVM toolchain for cross compiling to .Net, iOS, Andoid and Java</td>
        <td>XMLVM <a href="http://xmlvm.org/toolchain/">http://xmlvm.org/toolchain/</a> From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3347669-xmlvm-toolchain-for-cross-compiling-to-net-ios-">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>C# implemented</td>
        <td>I know someone was working on this but I don't think it was ever established in full. It would be nice to be able to use code from other engines more effectively. Tutorials from other engines could then be used with tweaking where a tutorial is not available yet for Torque. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3270114-c-implemented">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Core Engine refactor with Core Plus modules</td>
        <td>I believe T3D would be well served to adapt a modular approach to distribution consisting of "Core" template and "Core Plus" templates that provide genre specific functionality for developers who would otherwise be unable to refit a general purpose engine into application for their specific genre. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3266297-core-engine-refactor-with-core-plus-modules">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Forest Editor to support multiple forest objects per mission</td>
        <td>Currently forest editor supports only one forest object per mission "TheForest". My request would be a modification so that multiple forest objects could exist in a mission, with each object linked to a specific brush. This would provide a method to create multiple forests in a mission and modify or remove each individually without disturbing the others. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3270533-forest-editor-to-support-multiple-forest-objects-p">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Light animation for the emissive material</td>
        <td>Give the emissive material some animation properties like those from the Light Animation on light entities. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3878053-light-animation-for-the-emissive-material">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Terrain Streaming or Paging</td>
        <td>From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3953097-terrain-streaming-or-paging">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Rim Lighting Shader</td>
        <td>Rim Lighting as a Post-processing effects. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3289287-rim-lighting-shader">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Wind animation and collision support for groundcover objects</td>
        <td>The groundcover tool is a fast and easy way to distribute a lot of items onto lots of terrain, saving work and performance, but at the moment it is mostly useless if you want to have authentic vegetation with wind effects, if you use the groundcover now, you will have forest items with wind animation and the groundcover objects will not have it, producing a non authentic environment also so missing collision support makes it useless for bigger or non-vegetation objects in general. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3998951-wind-animation-and-collision-support-for-groundcov">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>screenspace lightning</td>
        <td>Full screenspace lightning. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3269264-screenspace-lightning">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>In game cinametics</td>
        <td>Add in game cinematics and its editor. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3933815-in-game-cinametics">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Seperate Sever from Client</td>
        <td>Set up the Server code to build on it's own, or set a flag so that it's not compiled with the client. Best practice would be be to split the the client and server and have a toggle able network build process when compiling. Not every one wants to make a networked game. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3310458-seperate-sever-from-client">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>wetness PostFX and wetness custom material</td>
        <td>It would be nice to finally get the wetness and precipitation added as an out-the-box feature. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3269297-wetness-postfx-and-wetness-custom-material">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Add TorqueScript Prefab methods</td>
        <td>As displayed here - would be a great addition to stock torque <a href="http://www.garagegames.com/community/resources/view/19259/1">http://www.garagegames.com/community/resources/view/19259/1</a>
 From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3262747-add-torquescript-prefab-methods">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Phong Tessellation</td>
        <td>I have found this and looks like it works without the need of DX 11 <a href="http://perso.telecom-paristech.fr/~boubek/papers/PhongTessellation/">http://perso.telecom-paristech.fr/~boubek/papers/PhongTessellation/</a>
 From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3266128-phong-tessellation">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Database: Simple and Complex</td>
        <td>We need a simple database with basic save option for the base characters supplied. This will save ammo count, health, etc. Then this can feed into a complex version that will set the ground for a network based database that is in congruence with a system that most will agree on such as maybe SQL light with a tutorial on basic functions to get one started. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3270518-database-simple-and-complex">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>MVC Design Pattern (Component System?)</td>
        <td>I am trying to determine if T3D already has this pattern or not. My conclusion is that the game objects are so tightly coupled with the input and output that I decided it does not follow the MVC pattern. Why use this pattern? Because if you want to write a game for Windows, Linux, iOS, XBox, PS3, Android, Flash, etc it would be really cool to only have to modify the View part. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3277249-mvc-design-pattern-component-system-">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>An unreal mesh paint like editor hooked into shadergen</td>
        <td>Basically an editor like mesh paint that lets you paint the vertex color in a mesh and shadergen hooked up to allow use of this. So for instance you could set diffuse0, diffuse1, diffuse2, diffuse3 in material and it would use diffuse0 like it does now but you could blend diffuse1,2,3 using red, green, and blue channels in the mesh paint tool. OF course if you only wanted to work with 2 textures you would just set diffuse0 and diffuse1 and use the red channel in the tool. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3266502-an-unreal-mesh-paint-like-editor-hooked-into-shade">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Rig Design for Torque 3D</td>
        <td>In the past, there was an image of the Torque Player "Blue Guy" and the Orc with rigs. These rigs had names that you would give them so that Torque and read. What i am requesting is not an in-game feature, but a feature on the website that will expose the different kinds of rigs that Torque3D can translate. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3268094-rig-design-for-torque-3d">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>More efficient / intuitive handling of the editor</td>
        <td>There are many little not very well optimized workflows in the Torque3D editor, like if you add an object to the scene the default alignment options should be snap to terrain and move on the horizontal axes and the object should snap to the mouse and if you press the mouse button the object gets placed. And if you click an object in the movement mode it gets automatically picket up and you are again in the snap to terrain horizontal movement. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3929874-more-efficient-intuitive-handling-of-the-editor">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Support for exporting game to the Flash platform</td>
        <td>This is a request that came up in the topic on GarageGames. Flash was not mentioned specifically, but with Alchemy 2 it seems to be a more viable web option than WebGL at this time. Feel free to disagree! From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3268645-support-for-exporting-game-to-the-flash-platform">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Ai poses and ContactTimer Pack/Unpack update fix (already in resources)</td>
        <td>Ai Poses exposed to console (still has a consoleMethod which should probably be updated to an EngineDefine) From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3266659-ai-poses-and-contacttimer-pack-unpack-update-fix-">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Realistic Skin Shader</td>
        <td>To replace or add the ability to apply a realistic skin shader to model. Similar to what is done in cryengine From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3269246-realistic-skin-shader">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Elevation mask for terrain-painting and new filling function</td>
        <td>In other engines, for example cry-engine, there was a function, where you could have a elevation mask for terrain painting, for example to make sure your underwater terrain only gets painted under the sea level. Also there was a function where you could fill the whole terrain with this mask at one click, this is extremely effective, because it lets you paint the whole terrain in a few clicks, no matter how big it is.
 From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3929274-elevation-mask-for-terrain-painting-and-new-fillin">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>More Simgroups/better managing (forest items, terrain materials...)</td>
        <td>I noticed at the moment there is no simgroup function for forest items and terrain materials, since there are useful simgroups for other objects like mission objects and forest brushes, I would like to see them for the forest items and terrain materials also, because handling of hundreds of files in one unsorted list can get pretty complicated. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3998928-more-simgroups-better-managing-forest-items-terr">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Add placement of physicsForce objects to the World Editor</td>
        <td>This object type is missing from the objects available to place via the editor, so we have to add them manually in the mission script file. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/4025560-add-placement-of-physicsforce-objects-to-the-world">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Bigger brushes</td>
        <td>At the moment the limit of the brush size of the terrain paint brush is only 40, that is really small and with that it is almost impossible to paint huge terrains, so lift this restriction. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3929304-bigger-brushes">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Improved Color Picker</td>
        <td>I rewrote the color picker recently to be quite a bit better. I submitted it as a resource here: <a href="http://www.garagegames.com/community/resources/view/21931">http://www.garagegames.com/community/resources/view/21931</a> And was going to fork the torque build and make a pull request but github for windows keeps crashing on me. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3262752-improved-color-picker">feature request</a>.</td>
        <td></td>
    </tr>
    <tr>
        <td>Add new GuiBitmapStringCtrl that strings a number of images</td>
        <td>Adds a new Gui Control to the engine that strings a number of images 
together. From this <a href="https://garagegames.uservoice.com/forums/178972-torque-3d-mit/suggestions/3262659-add-new-guibitmapstringctrl-that-strings-a-number-">feature request</a>.</td>
        <td></td>
    </tr>
</table>