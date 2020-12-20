# Unity3D-Easy-Documentation (WIP)
Table of contents:
* [What is that](#-what-is-that)
* [Basics](#-basics)
* [Get Access to the objects and components](#-get-access-to-the-objects-and-components)
* [Transform Objects](#-transform-objects)
* [Create and Destroy Objects and Components](#-create-and-destroy-objects-and-components)
* [Basic Visibility of Objects](#-basic-visibility-of-objects)
* [Input and Controls](#-input-and-controls)
* [Scenes](#-scenes)

## 🍕 What is that?

I just making some list of super-basic snippets and functions of Unity3D. Mostly for myself.

## 🍕 Basics

### How Unity works?
<img src="https://github.com/Leonid900/Unity3D-Easy-Documentation/blob/main/pic_unity_structure.png">

Each project has some amount of `scenes`. `Scenes` are "levels" in your game and each `scene` holds a list of abstract `"game objects"`. Each `game object` by default is empty point in space, that has location, rotation and scale setting. `GameObjects` can hold a list of `components`, that gives your object some behavior or look. There is `components` such as `sprite renderer` and `mesh renderer` to display actual sprites and 3D models, `rigidbody` to apply physics to the object and much more! Also there is special component, called `script`. `Script` is a code written in `C# language`, that can be applied to an object as `component`. In this code you can `interact` with other `game objects` and their `components`.

<img src="https://github.com/Leonid900/Unity3D-Easy-Documentation/blob/main/unity_window.png">

### Comparsion to GameMaker?
>In Unity3D, you create a `scene` filled with a list of `GameObjects`, that each can hold a list of `components`, like `sprites`, `rigidbody simulation`, `mesh renderer` or `scripts`. Scripts are written in `C# language`. With them you can interact with components and gameobjects. Scripts default events as functions, like `start` and `update`

>In Game Maker, you create a `room` filled with a list of `objects` that each may hold a `sprite` and a series of `events` which in turn trigger a series of `actions`.
Your scripted behavior exists in the `actions` portion. To reproduce this behavior multiple times between objects, you create a `script` that can be executed as a single `action` © [Game Maker to Godot dictionary](https://github.com/coppolaemilio/gamemaker-godot-dictionary).


### C# syntax (expressions and loops)
If expression:
```csharp
if (condition == true) {
//condition is true;
} 
else 
{
//condition is false;
}
```

For loop:
```csharp
for (int i = 0; i < 10; i++) {
//do the loop until "i" variable will be smaller than ten;
}
```

While Loop:
```csharp
while (condition == true) {
//do the loop until condition is true;
}
```

Switch-Case expression:
```csharp
switch (variable_to_check) {
case condition1:
	Action1();
   	break;
case condition2:
	Action2();
   	break;
}
```

### C# variables (data types)
C# is strongly typed language, so you should setup data type of each variable each time when you declarating it.

You can also write just `var myVar = value;` as an automatic way, but that is not recommended.

You can declare variable without setting value, like this: `bool myVar;`

Also you need to setup scope, the two most popular are `private` and `public`. 
[Read about private and public variables]

In general syntax is 'scope type name = value;'

```csharp
bool   myVar = false;
int    myVar = 1337; 
float  myVar = 14.5f; 
double myVar = 14.494457; 
string myVar = ”Hello”; 
var    myVar = "Automatic detect verb type";
```

<p align="right"><sub>
<i>
How it is in Python:<br>
<img src="https://cdn.jsdelivr.net/npm/programming-languages-logos/src/python/python.png" height="16"> <code>//You can change data type of variable anytime</code><br>
<img src="https://cdn.jsdelivr.net/npm/programming-languages-logos/src/python/python.png" height="16"> <code>myVar = False //set myVar type as boolean</code><br>
<img src="https://cdn.jsdelivr.net/npm/programming-languages-logos/src/python/python.png" height="16"> <code>myVar = "Hello World" //set myVar type as string</code>
</i></sub></p>


### C# classes (create classes)
You can create new class instance if you will create new variable with data-type name the same as classname
```csharp
className myVar = new className();
Enemy the_soldier = new Enemy(); //Example: create and Enemy class instance in variable called the_soldier
```

### Private and Public variables\fields
You can hide public variable in Unity3D Inspector view with `[HideInInspector]` line
```csharp
[HideInInspector]
public float strength;
```

You can show private variable as GUI field in Unity3D Inspector view with `[SerializeField]` line
```csharp
[SerializeField]
private float strength;
```


### Print stuff in console 
You can print stuff in console with Debug.Log function. Most basic function.

```csharp
Debug.Log("Hello World");
```
<p align="right"><sub>
<i>
How it is in other languages:<br>  
<img src="https://cdn.jsdelivr.net/npm/programming-languages-logos/src/javascript/javascript.png" height="16"> <code>console.log('Hello World!');</code><br>
<img src="https://cdn.jsdelivr.net/npm/programming-languages-logos/src/python/python.png" height="16"> <code>print('Hello World')</code>
</i></sub></p>

## 🍕 Get Access to the objects and components

### Get Object by editor field

You can setup field that will be in inspector properties, where you can drag'n'drop Unity GameObjects:

```csharp
[SerializeField]
private GameObject myObject; //declare variable myObject that can hold any Unity3D GameObject.
```

### Get Object by name ('only in Start or Awake, not in Class Constructor')
```csharp
myObject = GameObject.Find("ObjectName");			//Find object by name (las in object list)
myObject = GameObject.Find("ObjectName/ObjectParent");		//Find object parent via Path (child of parents)
myObject = GameObject.Find("/ObjectInRoot"); 			//Find object in root without parent (specifically object without parent)
if (!myObject) {Debug.Log("there is no such an object");}	//Check if object found
```

### Get Component
You can get component as `GetComponent <ComponentName> ();`

```csharp
// GetComponent to a variable
ComponentName myComponent = GetComponent<ComponentName>();

// GetComponent to a variable (you can use "var" as well)
var myComponent = GetComponent<ComponentName>();

GetComponent<Rigidbody>().function(); // Access the function of the component
myField = GetComponent<ComponentName>().field; // Get the field from component and put it in myField
```


## 🍕 Transform objects

### Move object (3D)
```csharp
transform.position += new Vector3 (0f, 0f, 0f);
```

### Set myObject position of one axis to axis position of referenceObject (3D)
```csharp
myObject.transform.position = new Vector3(myObject.transform.position.x, myObject.transform.position.y, referenceObject.transform.position.z);
//for example, move camera with object
```

### Rotate object (3D)
```csharp
transform.rotation += new Vector3 (0f, 0f, 0f);
```

### Scale object (3D)
```csharp
transform.scale += new Vector3 (0f, 0f, 0f);
```

### Set maximum scale value by one axis (3D)
```csharp
if (transform.localScale.y > 5f) {
transform.localScale = new Vector3(transform.localScale.x, 5f, transform.localScale.z);}
```

## 🍕 Create and destroy objects and components

### Create object
```csharp
public GameObject enemy; // Can be dragged as prefab from assets
Instantiate(enemy);
```

### Destroy object
```csharp
Destroy(gameObject);				// Destroy UnityObject immidiately
Destroy(gameObject, 2); 			// Destroy UnityObject after 2 seconds
Destroy(self);						// Destroy script from object components
Destroy(GetComponent<Rigidbody>()); // Destroy specific component
Rigidbody myRigidbody = GetComponent<Rigidbody>()
```

## 🍕 Basic visibility of objects

### Hide object
```csharp
GetComponent<Renderer>().enabled = false;
```

### Show object
```csharp
GetComponent<Renderer>().enabled = true;
```

### Toggle object visibility
```csharp
GetComponent<Renderer>().enabled = !GetComponent<Renderer>().enabled; 
```

## 🍕 Input and Controls

### Input keyboard
```csharp
if (Input.GetKey(KeyCode.my_key_code)) {// Do something if key "my_key_code" pressed every time;}
if (Input.GetKeyDown(KeyCode.my_key_code)) {// Do something if key "my_key_code" pressed once;}
if (Input.GetKeyUp(KeyCode.my_key_code)) {// Do something if key "my_key_code" released once;}
```

### Input gamepad
???

## 🍕 Scenes

### Change scene
File → Build Settings → Drag'n'Drop scenes from "Assets" in "Scenes in Build"
```csharp
SceneManager.LoadScene(i);
SceneManager.LoadScene("SceneName");
```

### Restart scene
```csharp
SceneManager.LoadScene(SceneManager.GetActiveScene().buildIndex);
```

***


## 🍕 Advanced Stuff

### How to make Video Player play video from Youtube.
<p>Download https://github.com/iBicha/UnityYoutubePlayer script from Github.<br>
Unarchive everything from Assets folder in archive to your project Assets folder.<br>
Place "Youtube Player (Script)" above ↑ your "Video Player" component.<br>
Video Player should have "Source: URL" and "Play On Awake: True" for the testing.</p>

You can do things with these functions:
```csharp
YoutubePlayer.PlayVideoAsync //Play video
VideoPlayerProgress // allows to display the progress of the video, as well as seeking.
```


## 🍕 Misc Unfinished Stuff

### Animated Sinus function
?

### Collider (WIP)
???
```csharp
void TriggerCollider(Collider other){} ????????
if (other.CompareTage("Player")){}
```

### Change model
???

### Change materials (WIP)
```csharp
public Material[] material;
public int x;
rend = GetComponent<Renderer>()
rend.sharedMaterial = material[x];
```

### Change material texture (albedo/metallic/emission)
???


### Play model animation (?)
???

### Draw HUD
???

### Draw text
???

### Draw simple shapes
??

### How to store data
???

### Set color of the light
```csharp
private Light myLight; //Get Light Component by field
private Light = get; //Get Light Component by field

static float color_hdr = 1f; //HDR Brightness Multiply, because RGB is float
private Color myColor = new Color(1f*color_hdr, 1f* color_hdr, 1f*color_hdr); //create new color

myLight.color = myColor;

```

### Set Text
```csharp
using UnityEngine.UI; // Import in top of the script file
//-----------------------------------------
var myText = GetComponent<Text>();
myText.text = "Hello World";
//or	
[SerializeField]
private Component myText;
myText.text = "Hello World";
```


## Useful Packages and Addons
* Cinemachine — for TPS camera movement.
