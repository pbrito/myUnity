# Unity

## mouse selection

Por vezes quando o Low Resolution não esta selecionado o click sobre um objecto não funciona.

![Screenshot](./img/unity/resolution.png?raw=true)

Drag object(com boxcollider) funciona quanda a camera esta em modo ortho

```cs
private void OnMouseDrag()
{
	Vector3 tt=Camera.main.ScreenToWorldPoint(Input.mousePosition);
	transform.position = new Vector3(tt.x, tt.y, transform.position.z);
}
```
Drag and drop

```cs
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
// © 2017 TheFlyingKeyboard and released under MIT License
// theflyingkeyboard.net
public class DragAndDrop : MonoBehaviour {
    public float moveSpeed;
    public float offset = 0.05f;
    private bool following;
    // Use this for initialization
    void Start () {
        following = false;
        offset += 10;
    }
  
  // Update is called once per frame
  void Update () {
        if (Input.GetMouseButtonDown(0) && ((Camera.main.ScreenToWorldPoint(Input.mousePosition) - transform.position).magnitude <= offset))
        {
            if (following)
            {
                following = false;
            }
            else
            {
                following = true;
            }
        }
        if (following)
        {
            transform.position = Vector2.Lerp(transform.position, Camera.main.ScreenToWorldPoint(Input.mousePosition), moveSpeed);
        }
    }
}

```

Espera que a timeline chegue ao fim

```cs
    IEnumerator playWin(PlayableDirector playableDirector)
    {

        playableDirector.Play();

        while (playableDirector.state == PlayState.Playing)
        {
         yield return new WaitForSeconds(0.5f);
        }

        GameManager.gameManager.nextScene(111);
    }
```
---
# Animation
--

### Animation TimeLine Animator

```cs
public class ExampleClass : MonoBehaviour {
    public Transform target;
    public float speed;
    void Update() {
        float step = speed * Time.deltaTime;
        transform.position = Vector3.MoveTowards(transform.position, target.position, step);
    }
}
```



### Animator

![Screenshot](./img/unity/animator.png?raw=true)

```cs
Animator anim;
int clicked = Animator.StringToHash("clicked");

// Use this for initialization
void Start()
{
    anim = GetComponent<Animator>();
}
    
```
trigger animation:

```cs

anim.SetTrigger(clicked);
//there are othr types: SetBool ,SetInteger
```
```cs
if (Input.GetButtonDown("Jump"))
  

    private void OnMouseDown()
    {
        if (Input.GetMouseButton(0))
}
```
"Has Exit Time" quer dizer que a animac~ao corre at'e ao fim.
Para a animacao parar imediatamente e iniciar a transic~ao tem de estar uncheck.

<img src="./img/unity/transition.png?raw=true" width="300">

post com um exemplo em que um playable é alterado em runtime SetTransformTweenEndLocation
http://westhillapps.blog.jp/archives/52975464.html

----
windows Log
C:\Users\diogo\AppData\LocalLow\DefaultCompany\fono6

# NavMesh

NavMeshComponents - [Git repo](https://github.com/Unity-Technologies/NavMeshComponents)
Clone or download this repository , copy the contents of Assets/NavMeshComponents to an existing project

NavMeshComponents has four components for the navigation system.
Utilizo o componente NavMeshSurface.

# TextMesh Pro
--

Para a fonte comportar como monospace

```
<mspace=2.75em>pato</mspace>
```

gameObject

transform 

#Game
```cs


using System.Collections.Generic;       //Allows us to use Lists.
using Random = UnityEngine.Random;      //Tells Random to use the Unity Engine random number generator.

namespace Completed

    

      
private List <Vector3> gridPositions = new List <Vector3> ();   //A list of possible locations to place tiles.
        
GameObject instance =Instantiate (toInstantiate, new Vector3 (x, y, 0f), Quaternion.identity) as GameObject;
                  
instance.transform.SetParent (boardHolder);
int randomIndex = Random.Range (0, gridPositions.Count);
            

public static GameManager instance = null;              //Static instance of GameManager which allows it to be accessed by any other script.

//Awake is always called before any Start functions
void Awake()
{
    //Check if instance already exists
    if (instance == null)
        
        //if not, set instance to this
        instance = this;
    
    //If instance already exists and it's not this:
    else if (instance != this)
        
        //Then destroy this. This enforces our singleton pattern, meaning there can only ever be one instance of a GameManager.
        Destroy(gameObject);    
    
    //Sets this to not be destroyed when reloading scene
    DontDestroyOnLoad(gameObject);
    
     boardScript.SetupScene(level);
}
  
    
    

```

## Criar um target com ScriptableObject

https://www.youtube.com/watch?v=F5S2gq-30D8


```cs

[CreateAssetMenu(fileName = "NewTranformVariable", menuName = "Variables/Transform", order = 1)]

public class TransformVariableClass : ScriptableObject {
    [HideInInspector]
    public Transform Value;

}
```

Depois crio um objecto  atraves do menu Create> "Variables/Transform"
<img src="./img/unity/target0.png?raw=true" width="300">

```cs
public class SetPursuitTarget : MonoBehaviour {

    public TransformVariableClass transformVar;

    void Awake(){
        transformVar.Value = transform;
    }
}

```
Associo-o a um GameObject no campo do Componente(Script) SetPursuitTarget e a sua variable "transformVar".

<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/unity/target.png" width="300">

Agora no PreFab CuboLetra a variavel Zero é associada  a um ScriptableObject (do tipo TranformVariableClass) 

<img src="./img/unity/target1.png?raw=true" width="300">

<br>

--
###About ScriptableObjects:



Scriptable Objects can:

- Be serialized and deserialized in the editor
- Be deserialized in builds

Scriptable Objects cannot:

- Be serialized in builds (the same way as in editor)
<br>
<br>

So you can't use them to do things like save game progress or make an in-game map editor. You can still use them for predefined content.
<br>
<br>
<br>

## Coroutines
Se tiver um IEnumerator chamado Start o unity vai invocar automaticamente como faz para a funcao Start

```cs
IEnumerator Start(){
        for (int i = 0; i < 3; i++)
        {
            //do something...
        }
    }
```



----
#PreLoad (use DontDestroyOnLoad)
--
*replced by
https://blogs.unity3d.com/2018/07/19/spotlight-team-best-practices-guid-based-references/

[stackoverflow]( http://stackoverflow.com/a/35891919/294884)

#### Step 1.

Make a scene named "preload". It must be scene 0 in Build Manager.

enter image description here

#### Step 2.

In the "preload" scene make an empty GameObject called, say, "__app".

Simply, put DontDestroyOnLoad on '__app' via script.
Like a one-line DDOL script:
<img src="./img/unity/3DiYn.png?raw=true" width="300">

Note:
This is the only place in the whole project you use DontDestroyOnLoad.

It's that simple.

To finding say "SoundEffects" or "GameManager" components of -preload from any script in any of your scenes.

```cs
Sound sound = Object.FindObjectOfType<Sound>();
Game game = Object.FindObjectOfType<Game>();
```

or 

Write this in what class you want to access from anywhere, where XXXXX is the name of the class, for example "Sound"

```cs
public static XXXXX Instance { get; private set; }
void Awake()
{
  if (Instance == null)  {
    Instance = this; 
  } 
  else {
    Debug.Log("Warning: multiple " + this + " in scene!"); 
  }
}
```

Now instead of your example

```cs
Sound sound = Object.FindObjectOfType<Sound>();
```
Just simply use it, without looking, and no extra variables, simply like this, right off from anywhere:

```cs
Sound.Instance.someWickedFunction();
```

Alternately (technically identical), just use one global class, usually called Grid, to "hold" each of those. https://answers.unity.com/answers/663681/view.html. So,

```cs
Grid.sound.someWickedFunction();
Grid.networking.blah();
Grid.ai.blah();
```
####"During development"

DylanB asks: "During development it's quite annoying that you have to click to the preload scene every time before you click `Play`. Can this be automated?"

Sure, every team has a different way to do this. Here's a trivial example:

```cs

// this should run absolutely first; use script-execution-order to do so.
// (of course, normally never use the script-execution-order feature,
// this is an unusual case, just for development.)
...
public class DevPreload:MonoBehaviour
 {
 void Awake()
  {
  GameObject check = GameObject.Find("__app");
  if (check==null)
   { UnityEngine.SceneManagement.SceneManager.LoadScene("_preload"); }
  }
 } 
```
 
**But don't forget:** "what else can you do?" Games have to start from a preload scene. What else can you do, other than go to the preload scene, to start the game? You may as well ask "it's annoying launching Unity to run Unity - how to avoid launching Unity?" Games simply, of course, absolutely have to start from a preload scene - how else could it be? So sure, you have to "click to the preload scene before you click Play" when working in Unity - how else could it be?

##Event System
Add EventSystem, InputModule and PhysicsRaycaster

- EventSystem in Unity [video](https://www.youtube.com/watch?v=gefnPTCFeIc)

- UnityEvents Tutorial [video](https://www.youtube.com/watch?v=ju6mK6-e3Oo&t=982s)


#### Unity Mobile - Swipe Controls
- Unity Mobile - Swipe Controls - Unity 3D [TutorialVideo](https://www.youtube.com/watch?v=rDK_3qXHAFg)

- How to drag and drop game object in Android Unity game? Unity tutorial. [video](https://www.youtube.com/watch?v=sXc8baUK3iY)

- Unity Drag and Drop Tutorial - How To Drag and Drop UI Elements in Unity 5 | Unity 5 UI Tutorial
 [video](https://www.youtube.com/watch?v=fhBJWTO09Lw&t=816s)

- MAKING A DRAG AND DROP CUSTOMIZATION MENU IN UNITY - EASY TUTORIAL
[video](https://www.youtube.com/watch?v=We1ab6yHrwI)

- Unity Mobile From Scratch: TouchPhases and Touch Count
[video](https://www.youtube.com/watch?v=ay9bbWJQ01w&t=171s)





 if you want to test other scene without loading the first scene, 
then you'll need to place the gameManager in each scene 
(but remember to remove/disable it later)



#Find (GetComponent vs FindObjectOfType vs tag)
--

- **instance.transform.GetComponent<T>** (return Component type T) - finds a component only if it's attached to the same GameObject.(is like a "local call"). As a particualr case: GetComponent<Object> will return the first component of the GameObject (which should always be the Transform).

- **GameObject.FindObjectOfType<T>** (returns the first active loaded Object that matches type T) 	- searches whole hierarchy and returns the first "object" that matches! is more of a scene wide search and isn't the optimal way of getting an answer.

- Using a **tag** to search in the awake function.

<img src="https://raw.githubusercontent.com/pbrito/myUnity/master/img/unity/Tag-Unity.png" width="300">

```cs
private LevelManager levelManager;

void Awake () {
    levelManager = GameObject.FindGameObjectWithTag ("Manager").GetComponent<LevelManager>();
}

```
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
<br>
</br>

&nbsp;
&nbsp;

----
<br>
</br>

&nbsp;
&nbsp;
<br>
</br>
#Events Unite 2017.
--

https://unity3d.com/how-to/architect-with-scriptable-objects
http://www.roboryantron.com/2017/10/unite-2017-game-architecture-with.html

I have a question about the events. All the events in your demo were static events (no arguments). How do you handle dynamic events (with arguments)?For example, if want to call a custom event with a GameObject argument.

REPLY

In the much more elaborate system I built in the studio, we allow for argument passing with events. This means that you need a new event type definition for each passed type. for example, *GameObjectEvent : GameEvent*. You also need a listener type, *GameObjectEventListener : GameEventListener* and a UnityEvent type, *GameObjectUnityEvent : UnityEvent*.

I have this code get auto generated to make it easy to add new types, but it is still simple to implement each one.


-----

nexxogen
nexxogen
Há 7 meses

So what if I want to invoke an event with parameters? Is there a good way to do it with this system? He said that the possibilities of Unity events far surpass what it serializable, but I don't see that his system is any different when it comes to that.﻿



Ryan Hipple
Ryan Hipple
Há 7 meses
Our internal version of the event system does support parameters! One limitation of Unity's serialization is that it can not serialize open types, so when working with generics you need to author closed constructed types. This is why you need to define your own class for [Serializable] UnityStringEvent : UnityEvent<string> rather than just using UnityEvent<string>.

Because of this limitation, you need an event class for each potential argument type. We actually generate code when you select an argument to pass in the editor (if it has not been generated already) that simply creates a definition extending our game event class , StringGameEvent : GameEvent<String>. The actual implementation I have resulted in a relatively complex generic base class to make the code gen simpler.﻿
 


nexxogen
nexxogen
Há 7 meses (editado)

Ryan Hipple So if I understood correctly, you have presented the basic GameEvent class, but the actual implementation you're using in order to enable events with arguments is a more complicated one? I don't suppose there is a code example to be found somewhere? :)﻿



Ryan Hipple
Ryan Hipple
Há 7 meses

You are correct! I used the simplified GameEvent to present a concept. It is a usable starting point, but a full code dive would eat up way more than an hour. The event framework I have built up at our studio over the years is not open source. We have been talking about putting some of it on the Asset Store though....﻿



nexxogen
nexxogen
Há 7 meses
Ryan Hipple Alright, thanks for the answer. Might be a good homework for me to try and expand it in my own way. Btw, I've used it already in this basic form and I like it a lot.﻿



nexxogen
nexxogen
Há 7 meses
Just one more question if it's OK. Since you're using Unity events as sending and receiving points of your event system, doesn't that mean that you can't visualize events with arguments in the inspector, no matter what? If you extended your GameEvent class to accept arguments, you still have to call GameEvent.Raise() inside a Unity Event's callback in the inspector, so how can you do it when it's GameEvent.Raise(arg1, arg2...)?﻿
 


Ryan Hipple
Ryan Hipple
Há 7 meses
When inspecting the event object, we have a custom inspector that can display any argument type, even if the UnityEvent can not. For the raising, we only use UnityEvent when it is a supported type, otherwise it is raised with a code hook (and we can write our own visualizer for that). Receiving is easier. UnityEvents can forward along more data types than they can serialize. For instance, you can not serialize a UnityEvent with a static Vector3 argument, but you can still raise it with a dynamic Vector3 and select a target function to forward to.

Regarding the multiple arguments, we do not support it. Each event passes one type. We can build container classes if more complex data is needed. In most projects using this we do not end up with a lot of event type definitions. The most useful arguments are void (OnPlayerDied), bool (OnPauseChanged), float (FadeOutScreen), InventoryItem (OnItemGained), etc.﻿

----------------


I've been using this architecture for a year in production projects, and I can say that is much better than anything that have been implemented until now.

Said that, I have to remark some things that I had to do to make that architecture viable.

I implemented a code generator -ripped from / like- the one that is included with the default playables package ( https://assetstore.unity.com/packages/essentials/default-playables-95266 ) to make the code needed for the scriptableObject events with any parameter I want, from 1 to 4 (to maintain UnityEvents compatibility).

The code generator makes the Event, a Listener like the one of the video, and a Handler that is like the listener but using System.Action. Also it makes the drawers and inspectors for the event, so I can test in editor and see what elements are listening to the event.

With this resolved, the only problem I have currently is that is I have lots of NPCs, they will be listening to the same scriptableObject event, so it can become slow to iterate and it have to check for the wanted listener inside the same listener. I didn't have a fix for this yet.

Also, I can't put prefabs with these events inside asset bundles, because they will be instantiated and then they will not be the same object, so the event will not work.

There are the only two unresolved problems that I have with this architecture, but I'll wait to see how it behaves with ECS before I search for an alternative or to modify something important.

------------

- GameObjectEvent.cs

```cs
using System.Collections.Generic;
using UnityEngine;

[CreateAssetMenu(fileName = "NewGameEvent", menuName = "Events/GameObjEvent", order = 1)]
public class GameObjectEvent : GameEvent
{
    private string meu;

    public GameObjectEvent(string name)
            : base()
    {
        meu = name;
    }

}
```
- GameObjectEventListener.cs

```cs
using UnityEngine;
using UnityEngine.Events;

public class GameObjectEventListener : GameEventListener
{
    [Tooltip("Event to register with.")]
    public GameObjectEvent Event;

    [Tooltip("Response to invoke when Event is raised.")]
    public UnityObjectEvent Response;

    private void OnEnable()
    {
        Event.RegisterListener(this);
    }

    private void OnDisable()
    {
        Event.UnregisterListener(this);
    }

    public void OnEventRaised()
    {
        string h=Event.letra;
    Debug.Log(h + "  --------------------");
		Response.Invoke();
    }
}

```
- GameObjectUnityEvent.cs

```cs
GameObjectUnityEvent : UnityEvent
```
##SVG
Also it seems like the Color field of the SpriteRenderer doesn't work for SVG imported sprites (with either the UnlitVector material or the Sprites-Default). I added an extra script that sets "_Color" on the material and that works fine with both materials though. I'm guessing it has something to do with "_RendererColor".

I'm guessing it has something to do with "_RendererColor".
This is probably a side-effect of the SVG sprites already making use of the color channel of the vertices. For that reason, I would expect the _RendererColor to work when instancing is enabled. So it may be worth trying a new material with instancing enabled to see if that helps.

Can we modify the mesh like any other normal mesh at runtime?
Yes. The imported sprite is a regular sprite and you could modify the mesh using the Sprite.OverrideGeometry() method. Alternatively, you can also fill a Mesh object with tessellated geometry. We provide the 
VectorUtils.FillMesh() method for that matter (the Spline.cs example in the sample project does that).

####At the moment changing sprite renderer's color property seems doing nothing.
Yes, this is a known issue. This is caused by the renderer's color property trying to make use of the vertex color channel, which is already used by the SVG sprite.

A workaround for this is to create a new material for the vector sprite. Set the shader to "Unlit/Vector" or "Unlit/VectorGradient" (if you need textures/gradients) and check the "Enable GPU Instancing" checkbox on the material. By enabling GPU instancing, the color will be passed as an "instanced property" and should have an effect on the vector sprite.

####Can I change stroke width of imported SVG?
Once and SVG is imported, the vector shapes are "baked" into the resulting sprite as a triangulated mesh. For that reason, you won't be able to dynamically change the stroke width of an imported SVG.

However, you can import the SVG file using the SVGParser.ImportSVG() method and modify the resulting Scene object, including the stroke width. You can then tessellate and generate a sprite from that modified Scene afterward. The SVGRuntimeLoad.cs example in the samples project does something similar.

Note that the SVG parsing/tessellation process is expensive, so use it carefully :) Hope this helps!

####Can the Unlit Sprite Shader be switched to Lit so they can take advantage of lighting?
I would think this should be relatively easy to achieve. The Unlit/Vector shader basically only output the color associated to the vertices, so doing a custom lit shader that takes that color as the albedo factor should be simple.

####What is the performance like?
Performance for colored SVG sprites should be very similar to regular sprites. However, textured/gradient sprites are more expensive to render as they required a couple of additional texture taps and more per-fragment processing. Highly tessellated sprites may cause some performance issues as well.

You are correct, we do rely on the multi-sample antialiasing of Unity (MSAA). This usually performs quite well, but it certainly does require more memory. There are other anti-aliasing techniques out there that we could use, but none of them are free (either in computational or memory usage), and all have pros and cons. We opted for MSAA essentially because of its performance and high-quality results.

You should see if the cost of MSAA it too high on your low-spec devices. Sometimes, even a 2x anti-aliasing value goes a long way. If the cost is still too high, you have other options. Some user decided to render the SVG sprites to and texture (with multi-sampling turned on), and then use the resulting anti-aliased texture as normal sprites. This gives the high-quality anti-aliased results and high performance, but you lose the "infinite" resolution of SVG sprites.

I hope this helps :)

####BTW, is there a simple way how to use these SVG assets with a new ECS? As far as I know there is just a MeshInstanceRenderer, so I probably need to create a mesh from this SVG somehow and pass it to the MeshInstanceRenderer?
This has very good chances to work as far as I can tell, but I never tried it personally. We have a utility method to fill a mesh with all the required attributes: VectorUtils.FillMesh(). So you could use that to create the mesh to plug into the MeshInstancedRenderer.


https://forum.unity.com/threads/vector-graphics-preview-package.529845/page-2

```cs

void OnDrawGizmosSelected(){
 
    var nav = GetComponent<NavMeshAgent>();
    if( nav == null || nav.path == null )
        return;
 
    var line = this.GetComponent<LineRenderer>();
    if( line == null )
    {
        line = this.gameObject.AddComponent<LineRenderer>();
        line.material = new Material( Shader.Find( "Sprites/Default" ) ) { color = Color.yellow };
        line.SetWidth( 0.5f, 0.5f );
        line.SetColors( Color.yellow, Color.yellow );
    }
 
    var path = nav.path;
 
    line.SetVertexCount( path.corners.Length );
 
    for( int i = 0; i < path.corners.Length; i++ )
    {
        line.SetPosition( i, path.corners[ i ] );
    }
 
}
 
```

Adicionar comentário · thub.questions.view.hide-n-comments · Partilhar
avatar imageexorakhilas · 21 de Oct de 2015 às 09:44 1
Thank you for sharing!

 avatar imagechainalonez · 23 de Mar de 2016 às 04:07 1
it's nice sample, thanks a lot :)

 avatar imageFredex8  chainalonez · 23 de Mar de 2016 às 04:45 4
Since this has been resurrected already...

If you only need it for debugging this can be done easier than that.
```cs
for (int i = 0; i < path.corners.Length - 1; i++)
{
    Debug.DrawLine(path.corners[i], path.corners[i + 1], Color.red);
}
```
 avatar imageTakuanDaikon  Fredex8 · 23 de Mar de 2016 às 06:24 1
True, although the LineRenderer supplied some styling options I preferred that Debug.DrawLine() didn't, which of course I removed before posting the code.

Your way is indeed simple, effective, and concise.

You should promote the comment to an answer :)

## path
https://www.youtube.com/watch?v=saAQNRSYU9k


## Addressables

https://www.youtube.com/watch?v=cfp_bx_C094

using UnityEngine.ResourceManagement;
using UnityEngine.AddressableAssets;






   /*
       var toi= Addressables.ResourceLocators.OfType<ResourceLocationMap>()
            .SelectMany(locationMap =>
                locationMap.Locations.Values.Select(key => key.First())
            );
       foreach (var s in toi)
       {
           Debug.Log( s.Data.+ "++++");
       }
             */
      
      
        /*

        foreach (var resourceLocator in Addressables.ResourceLocators)
        {
            
            foreach (var resourceLocatorKey in resourceLocator.Keys)
            {
                IList<IResourceLocation> locs;
                resourceLocator.Locate(resourceLocatorKey, out locs);
                foreach (var resourceLocation in locs)
                {
                    Debug.Log(resourceLocation.InternalId+"++++"+resourceLocation.ToString());
                    
                }
                if(locs.First().Data!=null)
                Debug.Log( resourceLocator.GetType().ToString()  +" ~~~ "+locs.Count+ " x " +locs.First().ToString() +" @  "+ locs.First().Data.ToString()+"  ###############   "+ resourceLocatorKey.ToString()   );

            }
            
        }
        */