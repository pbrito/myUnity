![f: id: tsubaki_t 1: 2020903232324154 j: plain](https://cdn-ak.f.st-hatena.com/images/fotolife/t/tsubaki_t1/20190403/20190403232154.jpg "f: id: tsubaki_t 1: 2020903232324154 j: plain")

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

![f: id: tsubaki_t 1: 2020903403220649 j: plain](https://cdn-ak.f.st-hatena.com/images/fotolife/t/tsubaki_t1/20190403/20190403220649.jpg "f: id: tsubaki_t 1: 2020903403220649 j: plain")

By the way, Visual Effect Graph is a system that uses the Compute Shader to generate the timing and position of each particle (particle), and the actual drawing is done with the normal Shader. The interesting part of this system is that you can generate a Compute Shader from a node that generates particle coordinate motion.

This "particle movement" can be used in other pipelines, so if you replace the drawing part, you can expect it to be used in other pipelines. In other words, to use the Visual Effect Graph in LWRP, the **final drawing shader template should be replaced with the LWRP one** .

(The drawing part seems to match the output node)

![f: id: tsubaki_t 1: 2020903223223736 j: plain](https://cdn-ak.f.st-hatena.com/images/fotolife/t/tsubaki_t1/20190403/20190403223736.jpg "f: id: tsubaki_t 1: 2020903223223736 j: plain")

![f: id: tsubaki_t 1: 202090323072626 j: plain](https://cdn-ak.f.st-hatena.com/images/fotolife/t/tsubaki_t1/20190403/20190403230726.jpg "f: id: tsubaki_t 1: 202090323072626 j: plain")

Procedure for LWRP
==================

The Visual Effect Graph makes it easy to replace the drawing function (currently). So I will replace the template used for drawing.

There is a template folder for LWRP `Packages/visual effect graph/Shaders/RenderPipeline/LWRP`.

So `Project Settings > VFX`for `Render Pipeline Settings Path`a, `Packages/com.unity.visualeffectgraph/Shaders/RenderPipeline/LWRP`you'll do to change to.

![f: id: tsubaki_t 1: 2020903231401j: plain](https://cdn-ak.f.st-hatena.com/images/fotolife/t/tsubaki_t1/20190403/20190403231401.jpg "f: id: tsubaki_t 1: 2020903231401j: plain")

![f: id: tsubaki_t 1: 202090302342424 j: plain](https://cdn-ak.f.st-hatena.com/images/fotolife/t/tsubaki_t1/20190403/20190403231424.jpg "f: id: tsubaki_t 1: 202090302342424 j: plain")

After that, open the Visual Effect Graph editor and press the Comple button.

Now that the LWRP compliant shader is generated, you can use the Visual Effect Graph with LWRP.

![f: id: tsubaki_t 1: 20190203231602 p: plain](https://cdn-ak.f.st-hatena.com/images/fotolife/t/tsubaki_t1/20190403/20190403231602.png "f: id: tsubaki_t 1: 20190203231602 p: plain")

<figure class="figure-image figure-image-fotolife" title="LWRP compatible setup procedure">![f: id: tsubaki_t 1: 2020903234205 g: plain](https://cdn-ak.f.st-hatena.com/images/fotolife/t/tsubaki_t1/20190403/20190403234205.gif "f: id: tsubaki_t 1: 2020903234205 g: plain")

<figcaption>LWRP compatible setup procedure</figcaption>

</figure>

Bonus: Legacy Render Pipeline support
=====================================

The difference between LWRP and HDRP is mostly "shader for drawing" ... so if it's really normal, you can use it in a pipeline as well? The idea is that it can actually be used.

`Render Pipeline Settings Path`, `Packages/com.unity.visualeffectgraph/Shaders/RenderPipeline/Legacy`And [VFX-](http://d.hatena.ne.jp/keyword/VFX) Graph ver 5.10 could be used as it is.

![f: id: tsubaki_t 1: 202090302382424 j: plain](https://cdn-ak.f.st-hatena.com/images/fotolife/t/tsubaki_t1/20190403/20190403231824.jpg "f: id: tsubaki_t 1: 202090302382424 j: plain")

However, this is not to say that it is a formal response, but it may not be usable if the version goes up in a standing position that "We made it in the legacy pipeline and thought it was better to publish. It is also an item. If you want to support Mesh etc, it is likely that you need to write your own template, referring to other pipeline templates.

<https://t.co/JNgk1Q1s4P>

However, there are cases where it is not possible to make a full transition to the Scriptable Render Pipeline system at present, so I would like to thank you very much.

Impression
==========

[GPU](http://d.hatena.ne.jp/keyword/GPU) particles are fun. Even if the amount is increased, there is no increase in CPU.

Relation
========

<iframe src="https://hatenablog-parts.com/embed?url=https%3A%2F%2Fblogs.unity3d.com%2Fjp%2F2018%2F11%2F27%2Fcreating-explosive-visuals-with-the-visual-effect-graph%2F" title="Creating Explosive Effects Using the Visual Effect Graph-Unity Blog" class="embed-card embed-webcard" scrolling="no" frameborder="0" style="display: block; width: 100%; height: 155px; max-width: 500px; margin: 10px 0px;"></iframe>*[blogs.unity3d.com](https://blogs.unity3d.com/jp/2018/11/27/creating-explosive-visuals-with-the-visual-effect-graph/)*

[* 1](#fn-868ef1d4) : Everyone on the [iPhone](http://d.hatena.ne.jp/keyword/iPhone) ~ ☆