## shape key 
How can I animate oval shaped eyes (Blender to Unity)?
[forum.unity](https://forum.unity.com/threads/how-can-i-animate-oval-shaped-eyes-blender-to-unity.455147/)

I made a cartoon character in Blender with oval shaped eyes and I want to use it in a game. But I have some problems with the animation of the eyes. I couldn't just rotate the eye-mesh because of its shape, its coming out of its sockets, so I animated the pupil using bones and the UVWarp modifier. It's working nicely in Blender but whenever I import it to Unity, the animation plays but nothing happens, the pupil doesn't move. I tried to export it as .blend and as .fbx., the result is the same. I assume Unity doesn't understand the modifier or something else is going wrong. 
So how can I animate eye movement on oval shaped eyes in Unity? How can I export it from Blender to Unity or do I have to animate it directly in Unity?
I'm fairly new to the program so thank you for any help!


DimitriX89

UVWarp is a Blender-specific modifier, so it wont export anywhere. 
What you could use is shape key animation. The common solution for cartoon eyes is Lattice modifier

<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/b2.png"   height="200" />
https://www.youtube.com/watch?v=g6ozlmgvesc
,use it to produce shape keys representing all look directions (4 for each eye). 

<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/b1.png"   height="200" />
https://www.youtube.com/watch?v=gDZcmAWL2jA
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

<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/btu.png"     height="200" >
https://www.youtube.com/watch?time_continue=55&v=8181FF9zQlo

https://www.youtube.com/watch?v=unFd5a9-Ga8



## bones

Blender bones Tutorial - Low Poly Chest Animation 

<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/bbonesC.png"   height="150" />

https://www.youtube.com/watch?v=xlYQp8pJqwk

<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/RotateAround.gif"   height="150" />
https://www.raywenderlich.com/6055-creating-reusable-characters-with-blender-and-unity

<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/ch-01.jpg" height="150" /><img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/rigging-11.jpg" height="150" />

https://cgi.tutsplus.com/tutorials/how-to-rig-a-2d-character-in-blender-for-cut-out-animation-or-explainer-videos-part-1--cms-26159

http://zakjr.com/blog/blender-to-unity-workflow-part-8



## shading 
<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/sh1.png" height="150" />   <img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/sh2.png" height="150" />
https://www.youtube.com/watch?v=W3Yg2i17TDo&t=166s

<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/shGr.jpg" height="150" />  
https://connect.unity.com/p/zelda-inspired-toon-shading-in-shadergraph

<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/SF1.jpeg" height="150" />  
https://blogs.unity3d.com/2018/10/05/art-that-moves-creating-animated-materials-with-shader-graph/

https://forum.unity.com/threads/dd-standard-toon.496744/
https://forum.unity.com/threads/guilty-gear-xrd-shader-test.448557/page-2
https://www.patreon.com/minionsart
https://www.patreon.com/posts/tutorial-list-10663597
http://panupat3d.blogspot.com/2014/07/guilty-gear-xrd-part-1-model-shading.html
http://panupat3d.blogspot.com/2014/07/guilty-gear-xrd-part-2-camera-animation.html


<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/uniShJ.png"   height="200" >
https://www.slideshare.net/Unite2017Tokyo/unite-2017-tokyounity-75800622


https://twitter.com/minionsart

<img src="https://pbs.twimg.com/tweet_video_thumb/DLNvX_vW0AUS7jU.jpg"  height="200" > https://video.twimg.com/tweet_video/DLNvX_vW0AUS7jU.mp4

<img src="https://pbs.twimg.com/tweet_video_thumb/DoI9-siUYAA6275.jpg"   height="200" >https://video.twimg.com/tweet_video/DoI9-siUYAA6275.mp4

Link LOSES his TOON! BotW in UNREAL Engine 4?! weirdness in Zelda Breath of the Wild
<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/zeld.png"    height="200" >
https://www.youtube.com/watch?v=oc6oVjWY_Gg

## 3D Photoscan 
3D Photoscan video

<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/blender/3dScan.jpg"   height="200" />

https://www.youtube.com/watch?v=k4NTf0hMjtY

: https://alicevision.github.io/#meshroom
