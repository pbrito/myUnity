# myUnity

- GameDev[facebook](https://www.facebook.com/NeCGM.FEUP/)
- Best Practice Guide[unity](https://docs.unity3d.com/Manual/BestPracticeGuides.html)
- Unity for Humanity 2019 Challenge https://youtu.be/M7-Hk6-cGmY
## Change between Scenes
 - Spotlight Team Best Practices: GUID based references [blog](https://blogs.unity3d.com/2018/07/19/spotlight-team-best-practices-guid-based-references/)
 - [Ketos Games](https://www.youtube.com/watch?v=RlUEZjRUSt0)-Smooth Scene Transition Tutorial(video)
 - [youtube Brackeys](https://www.youtube.com/watch?v=0HwZQt94uHQ)How to Fade Between Scenes in Unity
 - uses timeline [video](https://www.youtube.com/watch?v=vOWEtSXjk2c)
 -  Screen Wipe for level loading / transitions in Unity3D - Using UGUI  [video]( https://www.youtube.com/watch?v=clN7JItftTE)
 
## Mobile
 - [site](https://unity3d.com/learn/tutorials/topics/mobile-touch/building-your-unity-game-android-device-testing)Building your Unity game to an Android device for testing

## Docs

 - [scripting](https://unity3d.com/learn/tutorials/s/scripting) - unity site

## Entity Component System
 - [Entitas](https://github.com/sschmid/Entitas-CSharp)- Entitas is a super fast Entity Component System (ECS) Framework specifically made for C# and Unity
  - [Svelto](https://github.com/sebas77/Svelto.ECS)- Svelto ECS - Lightweight Entity Component System for Unity  
  - [job-system-cookbook](https://github.com/stella3d/job-system-cookbook)
  - ECS Samples by Unity [EntityComponentSystemSamples](https://github.com/Unity-Technologies/EntityComponentSystemSamples)
  - ECS Doc by Unity [Documentation](https://github.com/Unity-Technologies/EntityComponentSystemSamples/blob/master/Documentation/index.md)
  - Survival Shooter using Unity’s Entity Component System (revisited)
  [post](https://medium.com/@gamevanilla/survival-shooter-using-unitys-entity-component-system-revisited-874cd69085ae) written by David Pol 
  
  - [keijiro/Voxelman](https://github.com/keijiro/Voxelman)
 
     ![gif](https://raw.githubusercontent.com/pbrito/myUnity/master/img/Voxelman.gif)
  
## scriptableobjects
 - Unite Austin 2017 - Game Architecture with Scriptable Objects
[[video]](https://www.youtube.com/watch?v=raQ3iHhE_Kk), 
[[github]](https://github.com/roboryantron/Unite2017), 
[[blogpost]](http://www.roboryantron.com/2017/10/unite-2017-game-architecture-with.html)
[[unity-blogpost]](https://unity3d.com/how-to/architect-with-scriptable-objects)
    ![](https://raw.githubusercontent.com/pbrito/myUnity/master/img/scriptObj.png)


- SmartData [github](https://github.com/sigtrapgames/SmartData) implementacao da talk acima referida

    ![](https://raw.githubusercontent.com/pbrito/myUnity/master/img/scripObjScreen.png)

 


 - Unite 2016 - Overthrowing the MonoBehaviour Tyranny in a Glorious Scriptable Object Revolution
[video](https://www.youtube.com/watch?v=6vmRwLYWNRo&t=6s)
   ![](https://raw.githubusercontent.com/pbrito/myUnity/master/img/scriptOOver.jpg)


Unity Scriptable Objects as Variables[video](https://www.youtube.com/watch?v=F5S2gq-30D8)

Unity Scriptable Objects as Enums [video](https://www.youtube.com/watch?v=zo2sxhv8GUk&t)

 ## Unity Events
 
 - UnityEvents Tutorial [video](https://www.youtube.com/watch?v=ju6mK6-e3Oo)
 
      ![](https://raw.githubusercontent.com/pbrito/myUnity/master/img/eventsTut.jpg)
 - Actions - In this episode we look at how scripts can communicate with one another, either through a reference to the other script, or using events
 [video](https://www.youtube.com/watch?v=vDrYDAMdpuc&feature=youtu.be)
 
 - UnityEventVisualizer
[github]( https://github.com/MephestoKhaan/UnityEventVisualizer)
 
      <img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/event2.png"   height="200" />

      <img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/eventflow.gif"   height="200" />


- [EventBus](https://github.com/SaldayOpen/EventBus)is a system, which could dispatch published events to any registered handler accepting particular event argument. This means, that your event sources should no longer contain references to other components, only to event bus.

 ## C# job system
- [examples](https://github.com/stella3d/job-system-cookbook) - Examples of using the C# Job System in Unity 2018
 - [SimpleAnimation](https://github.com/Unity-Technologies/SimpleAnimation)A simple Animation Component that leverages PlayableGraphs [post](https://blogs.unity3d.com/2017/11/28/introducing-the-simple-animation-component/)
 
## Shaders
- keijiro/Swarm [github](https://github.com/keijiro/Swarm)An example of use of compute shaders and procedural instancing.
- ShaderGraphExamples[github](https://github.com/keijiro/ShaderGraphExamples)
- introduction-to-shader-graph [blog](https://blogs.unity3d.com/2018/02/27/introduction-to-shader-graph-build-your-shaders-with-a-visual-editor/)

## Funcional c#

- [video](https://www.youtube.com/watch?v=wJq86IXkFdQ)
- book [amazon](https://www.amazon.co.uk/Functional-Programming-C-Enrico-Buonanno/dp/1617293954/ref=sr_1_fkmr0_1?ie=UTF8&qid=1519648588&sr=8-1-fkmr0&keywords=functional+programming+in+c%23+enrico+bonanno)Functional Programming in C#
by Enrico Buonanno 

## Framework

- StratusFramework
In this repository you will find the source code to the Stratus Framework, a C# gameplay scripting framework for facilitating the composition of gameplay code for the Unity Engine. Its major tenet is to provide useful features with an easy to use interface while removing of as much boilerplate code from your scripts as possible.

I consider this framework very much a work in progress. Even so I find its core features, the Events and Actions systems to be rather robust, and can be used as is. The interface for them won't be changing in the future, as any future work on them will be adding features and fixing any discovered issues.

## Tutorials
- [reddit.com/r/unity_tutorials](https://www.reddit.com/r/unity_tutorials)
- PlaygroundProject A collection of simple scripts to create 2D physics games[github](https://github.com/UnityTechnologies/PlaygroundProject)

*Tips

- [How to Cope with Standard Unity FPS Controller](https://nothkedev.blogspot.com/2017/11/how-to-cope-with-standard-unity-fps.html)
- [procedurally-generated-meshes-in-unity](https://nothkedev.blogspot.com/2018/08/procedurally-generated-meshes-in-unity.html)
- Writing Shaders In Unity - Post Processing Shaders - Beginner Tutorial[video](https://www.youtube.com/watch?v=IRbWGI4Rqeo)
- Drag and Drop [video](https://www.youtube.com/watch?v=Pc8K_DVPgVM)
- click object [youtube](https://www.youtube.com/watch?v=RGjojuhuk_s)
<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/4wayClick.jpg"  height="200" />
## PostProcessing

- keijiro/PostProcessingUtilities[github](https://github.com/keijiro/PostProcessingUtilities)
- PostProcessing [wiki](https://github.com/Unity-Technologies/PostProcessing/wiki),[Quick-start](https://github.com/Unity-Technologies/PostProcessing/wiki/Quick-start)

<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/postProcessingX84.png"   height="200" />


## 2D
- [light](https://www.youtube.com/watch?v=IjP2MeSozIs)
- 2D Animation
<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/image_20.png"   height="200" />

https://github.com/Unity-Technologies/2d-spriteshape-samples


<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/uncleSam.jpg"   height="300" />
	
Exemplo como poderia utilizar o unity com animacao de vectores, embora so teria a estrutura de ossos.
Uncle Sam (Pt2) Spine 2D Animation Process - Time 



## Graphs
- [Procedural-Worlds-Editor](https://github.com/alelievr/Procedural-Worlds-Editor) node based procedural terrain generator which aims to support a complex biome system, multiple surface generation algorithms and an easy and powerful API

<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/MainGraph.png"   height="200" /> <img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/BiomeGraph.png"   height="200" />


## Animation

- keijiro/SkeletalGeometricEffects[github](https://github.com/keijiro/SkeletalGeometricEffects)

![gif](https://raw.githubusercontent.com/pbrito/myUnity/master/img/SkeletalGeometric0.gif)
![gif](https://raw.githubusercontent.com/pbrito/myUnity/master/img/SkeletalGeometric1.gif)

## Unity tools
- [ShaderGraph](https://github.com/Unity-Technologies/ShaderGraph)
![](https://raw.githubusercontent.com/pbrito/myUnity/master/img/shaderNodes.jpg)


- Timeline 
  * Unite Austin 2017 - Bridging Gameplay and Storytelling in an RTS Game[video](https://www.youtube.com/watch?v=nn3SnfNNEmk)
[github](https://github.com/UnityTechnologies/ATerribleKingdom)
  * extending timeline. A practical guide[blog]https://blogs.unity3d.com/2018/09/05/extending-timeline-a-practical-guide/)
  * Animation Events (animation window -AINDA NAO IMPLEMENTADO NA TIMELINE - https://forum.unity.com/threads/timeline-events.479400/page-4)
![](https://raw.githubusercontent.com/pbrito/myUnity/master/img/AnimationEditorEventLine.png)
  https://docs.unity3d.com/Manual/animeditor-AnimationEvents.html
- [animation.rigging](https://docs.unity3d.com/Packages/com.unity.animation.rigging@0.1/manual/index.html)

 <img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/rigAnim.jpg"   height="200" /> <img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/firewatch_04.jpg"   height="200" />

- ProBuilder

![](https://raw.githubusercontent.com/pbrito/myUnity/master/img/probuilder.jpg)


- Highroad Engine : Arcade Racing solution for Unity
![](https://raw.githubusercontent.com/pbrito/myUnity/master/img/Highroad.jpg)



- Attribute Extensions for Unity https://github.com/dbrizov/NaughtyAttributes
- Tool for validating (ensuring no broken / missing outlets) objects like GameObjects, ScriptableObjects, etc, in the Unity Editor. https://github.com/DarrenTsung/DTValidator
## Live Programming

-[keijiro/Beta](https://github.com/keijiro/Beta)

![](https://raw.githubusercontent.com/pbrito/myUnity/master/img/keijiroBeta.gif)

## JOGOS


- inside - docs https://github.com/playdeadgames/publications 

   <img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/inside-cover-1.jpg"   height="200" /><img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/insideAni.png"   height="200" />

- the gardens between - http://www.thegardensbetween.com/

   <img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/gardensBetween.gif"   height="200" /> <img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/animGardenB.gif"   height="200" />

- firewatch

   <img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/firewatch_01.jpg"   height="200" /> <img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/firewatch_04.jpg"   height="200" />

- Return of the Obra Dinn

   <img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/ObraDinn.gif"  width="300" height="169">

- Subnautica

   <img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/subnautica.jpg"  width="300" height="169">

Subnautica was announced by Unknown Worlds Entertainment on December 17, 2013,[3] with Charlie Cleveland as the game director and lead gameplay programmer, and Hugh Jeremy as the producer.[1]


   <img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/subnauticaUnity.jpg"  width="300" height="169"><img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/subnauticaUnity2.jpg"  width="300" height="169">


The development team opted to use the Unity engine rather than Spark, the engine used for the company's previous game, Natural Selection 2. Subnautica producer Hugh Jeremy justified this decision because of the different demands that the game places on the engine, and "because [the team] does not include people working on Spark, it's not appropriate for Subnautica to use Spark. By using Unity for Subnautica, Spark can continue to develop in certain directions, while Subnautica develops in others. To use Spark for Subnautica would be like trying to fit a square peg in a round hole."[14]
#

Opinion alert: the graphical differences between various engines are negligible these days, and we are choosing the engine that is best in terms of workflow, cost, and flexibility. Unity seems like the clear winner there. We think it's worth sacrificing cutting edge graphics tech for all that.
- GTA SA map in unity

<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/GTASA_GoldenGate.png"   height="200" />

https://bitbucket.org/MukaSchultze/grand-theft-auto-for-unity/src


## ScriptableRenderPipeline(SRP)
### Documentation
- [LightweightPipeline](https://github.com/Unity-Technologies/ScriptableRenderPipeline/blob/master/ScriptableRenderPipeline/LightweightPipeline/Documentation/GettingStarted.md)
- [HDRenderPipeline](https://github.com/Unity-Technologies/ScriptableRenderPipeline/blob/master/ScriptableRenderPipeline/HDRenderPipeline/Documentation/HDRenderPipeline.md)

### Tools

- [Materialize](http://www.boundingboxsoftware.com/materialize/index.php) - Free Texture Map Generation Tool
![](https://raw.githubusercontent.com/pbrito/myUnity/master/img/Materialize.png)
![](https://raw.githubusercontent.com/pbrito/myUnity/master/img/Materialize.GIF)


- A console for use in Unity Projects [unity-shell](https://github.com/marijnz/unity-shell) -The goal is to keep it as simple as possible. The console can register console commands to extend its possibilities. Console commands are easy to write and implement. 
There are some examples shipped with the base package.

![](https://raw.githubusercontent.com/pbrito/myUnity/master/img/unishell.gif)
- [unishell](https://github.com/rje/unishell) Interactive C# Shell for the Unity3d editor 

- [Console](https://github.com/peeweek/Console) -
A console for use in Unity Projects. The goal is to keep it as simple as possible. The console can register console commands to extend its possibilities. Console commands are easy to write and implement. There are some examples shipped with the base package.
- [Mapbox unity-sdk](https://www.mapbox.com/unity-sdk)
The Maps SDK for Unity is a collection of tools for building Unity applications from real map data. It enables Unity developers to interact with Mapbox web services APIs (including the Maps, Geocoding and Directions APIs) and create game objects via a C#-based API and graphical user interface.

### Visual scripting
-using_Playmaker_in_Production[link](https://www.gamasutra.com/blogs/YankoOliveira/20180205/314233/Haruspicy_and_Canopic_Jars_using_Playmaker_in_Production.php)
![](https://raw.githubusercontent.com/pbrito/myUnity/master/img/visualScripting.png)

FlowCanvas

 ![](https://raw.githubusercontent.com/pbrito/myUnity/master/img/flowCanvas.jpg) 
 ![](https://raw.githubusercontent.com/pbrito/myUnity/master/img/flowCanvas2.jpg)
 
  ![](https://raw.githubusercontent.com/pbrito/myUnity/master/img/flwch.jpg)
  ![](https://raw.githubusercontent.com/pbrito/myUnity/master/img/flch2.jpg)
### JSON
https://github.com/SaladLab/Json.Net.Unity3D

### uniRX - Reactive Extensions for Unity 
-Reactive Extensions for Unity [github](https://github.com/neuecc/UniRx)
-UniRxSimpleGame - A simple game showing how to use UniRx to make a dumb endless game for Unity [github](https://github.com/Xerios/UniRxSimpleGame)

### UI Prototype
-Prototyping UI in Unity Part 3 — Introduction to UI Components [](https://medium.com/sketch-app-sources/prototyping-ui-in-unity-part-3-introduction-to-ui-components-74cc40432bcb)
-code https://github.com/marianomike/unity-prototype-photoapp

A simple wrapper around Unity's new experimental Vector API, letting you draw as if you were inside a HTML5 canvas. Demonstrates basic fills, strokes and fill rules.[unity-vg-demo](https://github.com/poke1024/unity-vg-demo)

### [ Scene Track](https://edfilms.net/scene-track-game-media-exporter): Game Media Exporter Open Source
Scene Track: Game Media Exporter is an open source animation tool that delivers four kinds of data from Unity. By recording real-time gameplay, artists can now get video, image, MIDI and FBX files. Play. Record. Export. It's that easy. You don't need to know code. Jump in and try. It'll blow your mind!
 - presentation [video](https://www.youtube.com/watch?v=1pkprLEIIMk).
 - [demo-tutorial](https://www.youtube.com/watch?v=G_KMsYsoRg4).
 - Daniel Gies (E*D films) [autor chanel](https://www.youtube.com/channel/UCZD0nBcORFRo8QPxDbb4KDg)


### Links

[Filament "Docs"](https://google.github.io/filament/Filament.md.html) is exceedingly well documented and is a great read for anyone working on a renderer, even if you have little interest in using Filament in your own projec

http://tsubakit1.hateblo.jp/  blog japones

https://github.com/SoylentGraham/PopUnityCommon - Collection of independent & useful unity scripts - submodule this under /Assets/ in your project


https://connect.unity.com/
