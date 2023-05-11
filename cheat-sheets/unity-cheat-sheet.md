# Unity Cheat Sheet
=================
Unity is one of the top
platforms for game developer and a great skill to learn if you want to
become a Game Developer.

Contents
--------

### [Keyboard Shortcuts](#keyboard-shortcuts)

### [MonoBehaviour](#monobehaviour)

### [Script Lifecycle](#script-lifecycle)

### [Serializing Variables](#serializing-variables)

### [Instantiating Game Objects](#instantiating-game-objects)

### [Finding Game Objects](#finding-game-objects)

### [Destroying Game Objects](#destroying-game-objects)

### [Components](#components)

### [Vectors](#vectors)

### [Quaternion](#quaternion)

### [Physics Events](#physics-events)

### [Custom Unity Events](#custom-unity-events)

### [Scriptable Objects](#scriptable-objects)

### [Useful Links](#useful-links)


Keyboard Shortcuts
------------------

Boost your productivity by remembering the most common keyboard
shortcuts in the Unity Editor.

  -----------------------------------------------------------------------
  Action                              Key Binding
  ----------------------------------- -----------------------------------
  View Tool                           Q

  Move Tool                           W

  Rotate Tool                         E

  Scale Tool                          R

  Rect Tool                           T

  Transform Tool                      Y

  New Game Object                     Windows: CTRL + SHIFT + N\
                                      Mac: CMD + SHIFT + N

  New Child Game Object               ALT + SHIFT + N

  Toggle Window Size                  SHIFT + SPACE

  Duplicate                           Windows: CTRL + D\
                                      Mac: CMD +D

  Play/Pause                          Windows: CTRL + P\
                                      Mac: CMD + P

  Focus Game Object                   F
  -----------------------------------------------------------------------

If you're using [Visual Studio Code](https://code.visualstudio.com/),
here are some handy keyboard shortcuts.

  -----------------------------------------------------------------------
  Action                              Key Binding
  ----------------------------------- -----------------------------------
  Command Palette                     Windows: CTRL + SHIFT + P\
                                      Mac: CMD + SHIFT + P

  Quick File Open                     Windows: CTRL + P\
                                      Mac: CMD + P

  Toggle Sidebar                      Windows: CTRL + B\
                                      Mac: CMD + B

  Multi-Select Cursor                 Windows: CTRL + D\
                                      Mac: CMD + D

  Copy Line                           Windows: SHIFT + ALT + UP or SHIFT
                                      + ALT + DOWN\
                                      Mac: OPT + SHIFT + UP or OPT +
                                      SHIFT + DOWN

  Comment Code Block                  Windows: SHIFT + ALT + A
                                      (Multi-line comment), CTRL + K + C
                                      (Single-line comment)\
                                      Mac: SHIFT + OPT + A

  Show All Symbols                    Windows: CTRL + T\
                                      Mac: CMD + T

  Trigger suggestion and Trigger      Windows: Ctrl + Space, Ctrl + Shift
  parameter hints                     + Space\
                                      Mac: CMD + Space, CMD + Shift +
                                      Space

  Show References                     Windows: Shift + F12\
                                      Mac: Shift + F12

  Global Find                         Windows: CTRL + SHIFT + F\
                                      Mac: CMD + SHIFT + F
  -----------------------------------------------------------------------

MonoBehaviour
-------------

The `MonoBehaviour`{.language-text} class is defined by Unity to help
you transform your class into a component for game objects:

``` 
using UnityEngine;

public class ExampleClass : MonoBehaviour
{

}
```

Script Lifecycle 
----------------

All components that derive from the `MonoBehaviour`{.language-text}
class executes a number of event functions in a predetermined order.
They\'re the following:

-   `Awake()`{.language-text} - This function is called after a game
    object has been instantiated.
-   `OnEnable()`{.language-text} - This function is called when a game
    object is enabled.
-   `Start()`{.language-text} - This function is called before the first
    frame update.
-   `Update()`{.language-text} - This function is called on every frame.
-   `LateUpdate()`{.language-text} - This function is called on every
    frame **after** the `Update()`{.language-text} function is called.
-   `OnBecameVisible()`{.language-text} - This function is called when
    the current game object becomes visible via any camera.
-   `OnBecameInvisible()`{.language-text} - This function is called when
    the current game object no longer becomes visible via any camera.
-   `OnDrawGizmos()`{.language-text} - This function is called for
    drawing gizmos in the **scene** window.
-   `OnGUI()`{.language-text} - This function is called multiple times
    for GUI events.
-   `OnApplicationPause()`{.language-text} - This function is called
    when the game is paused via the Unity editor.
-   `OnDisable()`{.language-text} - This function is called when the
    game object is disabled.
-   `OnDestroy()`{.language-text} - This function is called when the
    game object is destroyed.

There\'s a lifecycle function called `FixedUpdate`{.language-text},
which is called a fixed number of times per second. You can configure
the frequency in the **Edit ▸ Project Settings ▸ Time ▸ Fixed
Timestep**.

Serializing Variables
---------------------

Unity is capable of performing serialization on your variables.
Serialization is the process of transforming your data into a format
that can be read and edited from the Unity editor. Variables can be
serialized based on either the attribute or access modifiers applied to
a variable.

If a variable is `public`{.language-text}, it\'ll be automatically
serialized:

``` 
public int age = 10;
```

If you don\'t want public variables to be serialized, you can use the
`NonSerialized`{.language-text} attribute from the
`System`{.language-text} namespace like so:

``` 
[NonSerialized] public int age = 10;
```

Private variables not serialized. However, if you want them to be
serialized, Unity has an attribute called
`SerializeField`{.language-text} that can be found from the
`Unity`{.language-text} namespace. It can be applied like so:

``` 
[SerializeField] private int age = 10;
```

Instantiating Game Objects
--------------------------

New game objects can be inserted into the scene programmatically by
calling the `Instantiate()`{.language-text} function. This function has
three arguments.

-   The Game Object
-   (Optional) Global Position
-   (Optional) Rotation

``` 
Instantiate(someGameObject);
Instantiate(someGameObject, new Vector3(0, 0, 10));
Instantiate(someGameObject, new Vector3(0, 0, 10), Quaternion.identity);
```

Finding Game Objects
--------------------

The `GameObject`{.language-text} class has a few methods for finding
game objects within the hierarchy.

-   `Find()`{.language-text} - Searches for a game object based on its
    name.
-   `FindGameObjectsWithTag()`{.language-text} - Finds multiple game
    objects that are stored in an array and returned. Uses a game
    object\'s tag to find them.
-   `FindWithTag()`{.language-text} - Finds a game object based on its
    tag.

``` 
GameObject myObj = GameObject.Find("NAME IN HIERARCHY");
GameObject myObj = GameObject.FindGameObjectsWithTag("TAG");
GameObject myObj = GameObject.FindWithTag("TAG");
```

Destroying Game Objects
-----------------------

Game objects can be destroyed by calling the `Destroy()`{.language-text}
function:

``` 
Destroy(gameObject);
```

Components {#components}
----------

By themselves, game objects can\'t do anything by themselves. We must
add components to add specific functionality. If you add custom
components, you might want to select other components. Unity offers
various solutions to grab components from a game object.

The first solution is to use the `GetComponent()`{.language-text}
function. There are different ways to call this function. The most
common is to pass in the name of the class for the component as a
generic like so:

``` 
AudioSource audioSource = GetComponent<AudioSource>();
```

Alternatively, you can use the `typeof`{.language-text} keyword and
assert the value like so:

``` 
AudioSource audioSource = GetComponent(typeof(AudioSource)) as AudioSource;
```

Lastly, you can pass in the name of the component as a string like so:

``` 
AudioSource audioSource = GetComponent("AudioSource") as AudioSource;
```

Vectors
-------

Vectors are used for the positions of game objects. You can use them to
help you calculate distance and movement. There are two vector classes,
which are `Vector2`{.language-text} and `Vector3`{.language-text}.

`Vector2`{.language-text} is primarily used for 2D games that have two
coordinates (x, y). `Vector3`{.language-text} is primarily used for 3D
games that have three coordinates (x, y, z).

**X = Left/Right Y = Up/Down Z = Forward/Back**

Unity supplies you with constants that can be accessed from their
respective vector class.

**Vector 3**

``` 
Vector3.right   /* (1, 0, 0)  */
Vector3.left    /* (-1, 0, 0) */
Vector3.up      /* (0, 1, 0)  */
Vector3.down    /* (0, -1, 0) */
Vector3.forward /* (0, 0, 1)  */
Vector3.back    /* (0, 0, -1) */
Vector3.zero    /* (0, 0, 0)  */
Vector3.one     /* (1, 1, 1)  */
```

**Vector2**

``` 
Vector2.right /* (1, 0)  */
Vector2.left  /* (-1, 0) */
Vector2.up    /* (0, 1)  */
Vector2.down  /* (0, -1) */
Vector2.zero  /* (0, 0)  */
Vector2.one   /* (1, 1)  */
```

If you\'re just interested the direction of a specific vector, you can
access its `normalized`{.language-text} property like so:

``` 
myVector.normalized
```

The distance between two vectors can be calculated with the
`Vector3.Distance()`{.language-text} method, which returns a
`float`{.language-text}:

``` 
float distance = Vector3.Distance(vectorOne, vectorTwo);
```

Quaternion {#quaternion}
----------

Quaternions are used for the rotation of the game object. The current
game object\'s rotation can be read/updated from via the
`transform.rotation`{.language-text} property.

Unity has a function called `Quaternion.LookRotation()`{.language-text}.
This function returns a Quaternion that takes in a vector. Typically,
the vector would be the position of the game object you would like to
look at.

``` 
Quaternion.LookRotation(gameObjectPosition);
```

Physics Events {#physics-events}
--------------

If you add a collider component to a game object, you can detect
collision events from your components by defining a specific set of
methods. The following methods are only called when you have a
**Collider** or **Rigid Body** component on both game objects.

-   `OnCollisionEnter`{.language-text} - This function is called once
    when another object has collided with the current game object.
-   `OnCollisionStay`{.language-text} - This function is called on every
    frame when another object has collided with the current game object.
-   `OnCollisionExit`{.language-text} - This function is called once
    when an object exits the collision zone of the current object.

``` 
private void OnCollisionEnter(Collision hit) {
  Debug.Log($"{gameObject.name} hits {hit.gameObject.name}");
}
private void OnCollisionStay(Collision hit) {
  Debug.Log($"{gameObject.name} is hitting {hit.gameObject.name}");
}
private void OnCollisionExit(Collision hit) {
  Debug.Log($"{gameObject.name} stopped hitting {hit.gameObject.name}");
}
```

The following functions are only called when the **On Trigger** option
is turned on from the respective collider component.

-   `OnTriggerEnter`{.language-text} - This function is called when
    another object has collided with the current game object.
-   `OnTriggerStay`{.language-text} - This function is called on every
    frame when another object has collided with the current game object.
-   `OnTriggerExit`{.language-text} - This function is called once when
    an object exits the collision zone of the current object.

``` 
private void OnTriggerEnter(Collider hit) {
  Debug.Log($"{gameObject.name} hits {hit.gameObject.name}");
}
private void OnTriggerStay(Collider hit) {
  Debug.Log($"{gameObject.name} is hitting {hit.gameObject.name}");
}
private void OnTriggerExit(Collider hit) {
  Debug.Log($"{gameObject.name} stopped hitting {hit.gameObject.name}");
}
```

Lastly, there are counterpart functions for 2D colliders. The functions
share the same name as the 3D functions, but have the word
`2D`{.language-text} appended at the end. The same goes for the
parameter\'s type. It\'s `Collision2D`{.language-text} instead of
`Collision`{.language-text}.

-   `OnCollisionEnter2D`{.language-text}
-   `OnCollisionStay2D`{.language-text}
-   `OnCollisionExit2D`{.language-text}
-   `OnTriggerEnter2D`{.language-text}
-   `OnTriggerStay2D`{.language-text}
-   `OnTriggerExit2D`{.language-text}

``` 
private void OnCollisionEnter2D(Collision2D hit) {
  Debug.Log($"{gameObject.name} hits {hit.gameObject.name}");
}
private void OnCollisionStay2D(Collision2D hit) {
  Debug.Log($"{gameObject.name} is hitting {hit.gameObject.name}");
}
private void OnCollisionExit2D(Collision2D hit) {
  Debug.Log($"{gameObject.name} stopped hitting {hit.gameObject.name}");
}
private void OnTriggerEnter2D(Collision2D hit) {
  Debug.Log($"{gameObject.name} hits {hit.gameObject.name}");
}
private void OnTriggerStay2D(Collision2D hit) {
  Debug.Log($"{gameObject.name} is hitting {hit.gameObject.name}");
}
private void OnTriggerExit2D(Collision2D hit) {
  Debug.Log($"{gameObject.name} stopped hitting {hit.gameObject.name}");
}
```

Custom Unity Events {#custom-unity-events}
-------------------

Custom events can be created to help you communicate between various
game objects. First, you must include the correct namespace:

``` 
using UnityEngine.Events;
```

Next, you can create a custom event by defining a variable with the
`UnityEvent`{.language-text} type like so:

``` 
public event UnityEvent OnCustomEvent;
```

Unity has another data type called `UnityAction`{.language-text} for
creating custom events:

``` 
public event UnityAction OnCustomEvent;
```

The main difference is that the `UnityEvent`{.language-text} type can be
serialized into the Unity editor. If you don\'t need an event to be
publicly modifiable through the Unity editor, you\'re better off with
the `UnityAction`{.language-text} type.

You can use generics to send additional data with your event. Up to 4
data types are supported.

``` 
// 1 Parameter
public event UnityAction<int> OnCustomEvent;
// 2 Parameters
public event UnityAction<int, float> OnCustomEvent;
// 3 Parameters
public event UnityAction<int, float, bool> OnCustomEvent;
// 4 Parameters
public event UnityAction<int, float, bool, string> OnCustomEvent;
```

Scriptable Objects {#scriptable-objects}
------------------

Scriptable objects are data containers. They can be a great way to
centralize data that can be used across game objects and components. You
can create a scriptable object by using the
`ScriptableObject`{.language-text} class from the
`UnityEngine`{.language-text} namespace.

``` 
using UnityEngine;

[CreateAssetMenu(fileName = "Data", menuName = "Parent Menu/Child Menu", order = 1)]
public class AudioSO : ScriptableObject
{

}
```

Scriptable objects allow users to create files from these classes. You
can add a menu item by using the `CreateAssetMenu`{.language-text}
attribute, which has the following parameters:

-   `fileName`{.language-text} - The name of the file created by Unity
    when the option is selected.
-   `menuName`{.language-text} - The menu name that will be displayed in
    the create menu.
-   `order`{.language-text} - The priority of the menu item when
    positioned alongside the other menu items.

Useful Links {#useful-links}
------------

-   [Unity Documentation](https://docs.unity3d.com/Manual/index.html)
-   [Unity Blog](https://blog.unity.com/)
-   [Unity Learn](https://learn.unity.com/)
-   [Unity Asset Store](https://assetstore.unity.com/)
-   [Order of execution for event
    functions](https://docs.unity3d.com/Manual/ExecutionOrder.html)

#### **[Back To Top](#contents)**