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


## bones
