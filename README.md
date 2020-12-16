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
C# is strongly typed language, so you should setup data type of each variable every time when you declarating it.
You can also write just `var` as automatic way, but that is not recommended.
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

You can setup field\variable

```csharp
[SerializeField]
private GameObject myObject;
```

### Get Object by name ('only in Start or Awake, not in Class Constructor')
```csharp
myObject = GameObject.Find("ObjectName");			//Find object by name (las in object list)
myObject = GameObject.Find("ObjectName/ObjectParent");		//Find object parent via Path (child of parents)
myObject = GameObject.Find("/ObjectInRoot"); 			//Find object in root without parent (specifically object without parent)
if (!myObject) {Debug.Log("there is no such an object");}	//Check if object found
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





## Useful Packages and Addons
* Cinemachine — for TPS camera movement.
