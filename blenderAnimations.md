## shape key 
How can I animate oval shaped eyes (Blender to Unity)?
[forum.unity](https://forum.unity.com/threads/how-can-i-animate-oval-shaped-eyes-blender-to-unity.455147/)

I made a cartoon character in Blender with oval shaped eyes and I want to use it in a game. But I have some problems with the animation of the eyes. I couldn't just rotate the eye-mesh because of its shape, its coming out of its sockets, so I animated the pupil using bones and the UVWarp modifier. It's working nicely in Blender but whenever I import it to Unity, the animation plays but nothing happens, the pupil doesn't move. I tried to export it as .blend and as .fbx., the result is the same. I assume Unity doesn't understand the modifier or something else is going wrong. 
So how can I animate eye movement on oval shaped eyes in Unity? How can I export it from Blender to Unity or do I have to animate it directly in Unity?
I'm fairly new to the program so thank you for any help!


DimitriX89

UVWarp is a Blender-specific modifier, so it wont export anywhere. 
What you could use is shape key animation. The common solution for cartoon eyes is Lattice modifier

<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/b2.png"   height="200" />[youtube](https://www.youtube.com/watch?v=g6ozlmgvesc)

,use it to produce shape keys representing all look directions (4 for each eye). 

<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/b1.png"   height="200" />[youtube](https://www.youtube.com/watch?v=gDZcmAWL2jA)
Then, you have to export the mesh as *.FBX and animate these shape keys using Unity internal animation tool, because Unity can only import shape key mesh data, not the shape key actions.

Thank you so far, I tried this and it works in Blender - 
but when I import it to Unity the shape keys / blend shapes are missing. 
It's the lattice modifier. I tried it with the lattice applied, then the shape keys are there. 
But my eyes are round again, not deformed as they should be.

So how do I import this with the lattice deformation and shape keys?

Make clones of your object (with their lattices), for each shape key you need. 
On each clone, set the corresponding shape key to max influence. 
On the main object, remove the lattice modifier and old shape keys. 
Select one of the clones, then (Shift+right mouse) the main object, and in Shape key menu (triangle pulldown) choose Join as Shapes. 
This will bake the results of lattice modifier + old shape key into new shape key. Repeat for others.


## Blendshapes
Shapekeys are actually supported in Unity now without any fancy wizardry.

In Unity they are known as Blendshapes.

A skinned mesh renderer is automatically added to any object imported with an armature. This need only be 1 single root bone. It doesn't really have to do anything. You can use it to move the object around if you wish.

The BlendShape slider appears on the SMR component.

http://docs.unity3d.com/Manual/BlendShapes.html
https://www.youtube.com/watch?v=JIc6131M2v8

## Animation



<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/bAnim.png" height="200" >

Blender Character Animation for Unity [video](
https://www.youtube.com/watch?time_continue=55&v=8181FF9zQlo)

<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/btu.png"     height="200" >

Blender Shape Keys for Unity Blendshapes [video](https://www.youtube.com/watch?v=unFd5a9-Ga8)


The correct workflow is from object mode first select the armature, go into pose mode, while in pose mode hold shift and select the mesh object you wish to weight paint, when both the armature and mesh are selected, the mesh being the active object, go into weight paint mode and you will be able to select the bones you wish to adjust weights for, in addition to adjusting the bone transforms as if in pose mode.

Note: that if you are using left mouse to select option in the input user preferences you will be unable to select bones while in weight paint mode, because the left mouse is already used to paint the weight value, I would recommend temporarily turning this off, using right mouse to select, while skinning a mesh to an armature to avoid this issue.

There is also the option to recreate all the Activate/Select keymap items, normally located within:

User Preferences → Input → 3D View → 3D View (Global)

Recreating these keymap items within:

User Preferences → Input → 3D View → Weight Paint

using Right Mouse as the event value (keybinding) rather then Select Mouse this will allow you to select bones with the right mouse button while in weight paint mode. Note that this is unnecessary if you are using right mouse to select by default.



## bones

Blender bones Tutorial - Low Poly Chest Animation 

Ter mais que uma Armature num ficheiro blender confude o Unity.

<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/bbonesC.png"   height="150" /> [video](https://www.youtube.com/watch?v=xlYQp8pJqwk)


<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/armatureBones.png"   height="150" /> [video](https://www.youtube.com/watch?v=tTM1TE40Loc)

<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/RotateAround.gif"   height="150" />humanoide [blog](https://www.raywenderlich.com/6055-creating-reusable-characters-with-blender-and-unity)

<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/ch-01.jpg" height="150" /><img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/rigging-11.jpg" height="150" />
how-to-rig-a-2d-character-in-blender [blog](https://cgi.tutsplus.com/tutorials/how-to-rig-a-2d-character-in-blender-for-cut-out-animation-or-explainer-videos-part-1--cms-26159)

<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/btuw.jpg" height="150" />    <img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/btuR.jpg" height="150" />
blender-to-unity-workflow [part-6](http://zakjr.com/blog/blender-to-unity-workflow-part-6)

<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/latti.png"   height="200" />
Lattice Rig Tutorial Blender [video](https://www.youtube.com/watch?v=pUFzpIqlCfg)



<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/faceAnim.png"   height="300" />

face Animation [video](https://www.youtube.com/watch?v=b8-4IQr6PEg&t=9575s)

https://lmhpoly.com/blender-tutorial-origin-point/



Atencao se carregar neste icon a rotacao de objectos nao funciona
<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/rotacao.jpg" height="150" />  


## shading 
<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/sh1.png" height="150" />   <img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/sh2.png" height="150" />

Shaders Case Study - Brawl Stars: Toon Shading [video](https://www.youtube.com/watch?v=W3Yg2i17TDo&t=166s)

<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/shGr.jpg" height="150" />  
https://connect.unity.com/p/zelda-inspired-toon-shading-in-shadergraph


<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/toonSh1.png" height="150" />

Tutorial Toon Outlines [video](https://www.youtube.com/watch?v=eZlIbvbQtqs)


<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/zeldaPartic.png" height="150" />

Particles Case Study - The Legend Of Zelda: The Wind Waker[video](https://www.youtube.com/watch?v=0IrCggoJCno)



<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/SF1.jpeg" height="150" />[blog unity](https://blogs.unity3d.com/2018/10/05/art-that-moves-creating-animated-materials-with-shader-graph/)

https://forum.unity.com/threads/dd-standard-toon.496744/
https://forum.unity.com/threads/guilty-gear-xrd-shader-test.448557/page-2
https://www.patreon.com/minionsart
https://www.patreon.com/posts/tutorial-list-10663597
http://panupat3d.blogspot.com/2014/07/guilty-gear-xrd-part-1-model-shading.html
http://panupat3d.blogspot.com/2014/07/guilty-gear-xrd-part-2-camera-animation.html


<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/uniShJ.png"   height="200" >https://www.slideshare.net/Unite2017Tokyo/unite-2017-tokyounity-75800622


https://twitter.com/minionsart

<img src="https://pbs.twimg.com/tweet_video_thumb/DLNvX_vW0AUS7jU.jpg"  height="200" >[anim](https://video.twimg.com/tweet_video/DLNvX_vW0AUS7jU.mp4)

<img src="https://pbs.twimg.com/tweet_video_thumb/DoI9-siUYAA6275.jpg"   height="200" >[anim](https://video.twimg.com/tweet_video/DoI9-siUYAA6275.mp4)

Link LOSES his TOON! BotW in UNREAL Engine 4?! weirdness in Zelda Breath of the Wild
<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/zeld.png"    height="200" >
https://www.youtube.com/watch?v=oc6oVjWY_Gg

## 3D Photoscan 
3D Photoscan video

<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/3dScan.jpg"   height="200" />

https://www.youtube.com/watch?v=k4NTf0hMjtY

<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/meshroom.png"   height="100" />https://alicevision.github.io/#meshroom
