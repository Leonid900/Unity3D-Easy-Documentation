# Unity3D-Easy-Documentation (WIP)

## What is that?

I just making some list of super-basic snippets and functions of Unity3D. Mostly for myself.

## Useful Packages and Addons
* Cinemachine — for TPS camera movement.

## Basic Functions <img src="https://cdn.jsdelivr.net/npm/programming-languages-logos/src/csharp/csharp.png" height="24">
### Print stuff in console 
You can print stuff in console with Debug.Log function

```csharp
Debug.Log("Hello World");
```
<p align="right"><sub>
<i>How it is in other languages:</i>
<img src="https://cdn.jsdelivr.net/npm/programming-languages-logos/src/javascript/javascript.png" height="16"> <code>console.log('Hello World!');</code>
<img src="https://cdn.jsdelivr.net/npm/programming-languages-logos/src/python/python.png" height="16"> <code>print('Hello World')</code>
</sub></p>

### Get Object by editor field

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

### Destroy object
```csharp
Destroy(gameObject);				// Destroy UnityObject immidiately
Destroy(gameObject, 2); 			// Destroy UnityObject after 2 seconds
Destroy(self);						// Destroy script from object components
Destroy(GetComponent<Rigidbody>()); // Destroy specific component
Rigidbody myRigidbody = GetComponent<Rigidbody>()
```

### Create object
```csharp
public GameObject enemy; // Can be dragged as prefab from assets
Instantiate(enemy);
```

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

### Set maximum scale value by one axis (3D)
```csharp
if (transform.localScale.y > 5f) {
transform.localScale = new Vector3(transform.localScale.x, 5f, transform.localScale.z);}
```

### Animated Sinus function
?

### Input keyboard
	if (Input.GetKey(KeyCode.my_key_code)) {}

### Input gamepad


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

### Private\Public
```csharp
[HideInInspector]
public float strength;
```

```csharp
[SerializeField]
private float strength;
```


