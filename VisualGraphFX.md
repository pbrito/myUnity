
![](./img/vfx/2019-04-27-00-06-56.png?raw=true)
Since Visual Effect Graph is compatible with LWRP, how to set it and how to respond.

-   [Visual Effect Graph](#Visual-Effect-Graph)
-   [Visual Effect Graph supports LWRP](#Visual-Effect-GraphがLWRPに対応)
-   [Procedure for LWRP](#LWRP対応の手順)
-   [Bonus: Legacy Render Pipeline support](#おまけLegacy-Render-Pipelineの対応)
-   [Impression](#感想)
-   [Relation](#関連)

Visual Effect Graph
===================

Visual Effect Graph is a node-based effect generation tool.

It is treated as a successor to particle, but it has a very flexible function, and in addition to simple effects, it also feels that various applications such as map-like expressions are effective. As for the movement, the lower video will move up.

<iframe width="480" height="270" src="//www.youtube.com/embed/SUZzJcBIK80?feature=oembed" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen=""></iframe>*[www.youtube.com](https://www.youtube.com/watch?v=SUZzJcBIK80)*

<iframe width="480" height="270" src="//www.youtube.com/embed/uvGX8GPdfTE?feature=oembed" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen=""></iframe>*[www.youtube.com](https://www.youtube.com/watch?v=uvGX8GPdfTE)*

Visual Effect Graph supports LWRP
=================================

Visual Effect Graph is was previously only compatible HDRP, but `ver 5.8.0`more **was also supported LWRP** . This [VR](http://d.hatena.ne.jp/keyword/VR) can be expected to work with and in HDRP such as mobile tough environment.

As a premise, Visual Effect Graph uses Compute Shader, so **it does not work in an environment that does not support Compute Shader.** And **if it is** [Android](http://d.hatena.ne.jp/keyword/Android) , especially OpenGLES3 system, ComputeShader listens to the story that it is very unstable (it's Vulkan The story of moving with you When using it, it is good to check whether it works on the target terminal. [* 1](#f-868ef1d4 "Everyone on the iPhone ~ ☆")

![](./img/vfx/2019-04-26-23-57-47.png?raw=true)

By the way, Visual Effect Graph is a system that uses the Compute Shader to generate the timing and position of each particle (particle), and the actual drawing is done with the normal Shader. The interesting part of this system is that you can generate a Compute Shader from a node that generates particle coordinate motion.

This "particle movement" can be used in other pipelines, so if you replace the drawing part, you can expect it to be used in other pipelines. In other words, to use the Visual Effect Graph in LWRP, the **final drawing shader template should be replaced with the LWRP one** .

(The drawing part seems to match the output node)
![](./img/vfx//2019-04-26-23-58-21.png?raw=true)
![](./img/vfx//2019-04-26-23-58-50.png?raw=true)


Procedure for LWRP
==================

The Visual Effect Graph makes it easy to replace the drawing function (currently). So I will replace the template used for drawing.

There is a template folder for LWRP `Packages/visual effect graph/Shaders/RenderPipeline/LWRP`.

So `Project Settings > VFX`for `Render Pipeline Settings Path`a, `Packages/com.unity.visualeffectgraph/Shaders/RenderPipeline/LWRP`you'll do to change to.
![](./img/vfx//2019-04-26-23-59-18.png?raw=true)
![](./img/vfx//2019-04-26-23-59-43.png?raw=true)


After that, open the Visual Effect Graph editor and press the Comple button.

Now that the LWRP compliant shader is generated, you can use the Visual Effect Graph with LWRP.

![](./img/vfx//2019-04-27-00-00-15.png?raw=true)


<figcaption>LWRP compatible setup procedure</figcaption>

</figure>


Impression
==========

[GPU](http://d.hatena.ne.jp/keyword/GPU) particles are fun. Even if the amount is increased, there is no increase in CPU.
