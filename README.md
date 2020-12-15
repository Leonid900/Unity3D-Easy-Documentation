# Unity3D-Easy-Documentation

## Packages and Addons
Cinemachine — for TPS camera movement.

## Basic Functions
### Print stuff in console
You can print stuff in console with Debug.Log function

```
Debug.Log("Hello World")
```

### Get Object by editor field
	[SerializeField]
	private GameObject myObject;
### Get Object by name ('only in Start or Awake, not in Class Constructor')
	myObject = GameObject.Find("ObjectName");			//Find object by name (las in object list)
	myObject = GameObject.Find("ObjectName/ObjectParent");		//Find object parent via Path (child of parents)
	myObject = GameObject.Find("/ObjectInRoot"); 			//Find object in root without parent (specifically object without parent)
	if (!myObject) {Debug.Log("there is no such an object");}	//Check if object found

### Move object (3D)
	transform.position += new Vector3 (0f, 0f, 0f);

### Set myObject position of one axis to axis position of referenceObject (3D)
	myObject.transform.position = new Vector3(myObject.transform.position.x, myObject.transform.position.y, referenceObject.transform.position.z);
	//for example, move camera with object

### Rotate object (3D)
	transform.rotation += new Vector3 (0f, 0f, 0f);

### Scale object (3D)
	transform.scale += new Vector3 (0f, 0f, 0f);

### Destroy object
	Destroy(gameObject);				// Destroy UnityObject immidiately
	Destroy(gameObject, 2); 			// Destroy UnityObject after 2 seconds
	Destroy(self);						// Destroy script from object components
	Destroy(GetComponent<Rigidbody>()); // Destroy specific component
	Rigidbody myRigidbody = GetComponent<Rigidbody>()

### Create object
	public GameObject enemy; // Can be dragged as prefab from assets
	Instantiate(enemy);

### Hide object
	GetComponent<Renderer>().enabled = false;

### Show object
	GetComponent<Renderer>().enabled = true;

### Toggle object visibility
 	GetComponent<Renderer>().enabled = !GetComponent<Renderer>().enabled; 

### Set maximum scale value by one axis (3D)
	if (transform.localScale.y > 5f) {
	transform.localScale = new Vector3(transform.localScale.x, 5f, transform.localScale.z);}

### Animated Sinus function


### Input keyboard
	if (Input.GetKey(KeyCode.my_key_code)) {}

### Input gamepad


### Change scene
	File → Build Settings → Drag'n'Drop scenes from "Assets" in "Scenes in Build"
	SceneManager.LoadScene(i);
	SceneManager.LoadScene("SceneName");

### Restart scene
	SceneManager.LoadScene(SceneManager.GetActiveScene().buildIndex);

### Collider (WIP)
	void TriggerCollider(Collider other){} ????????
	if (other.CompareTage("Player")){}


### Change model


### Change materials (WIP)
	public Material[] material;
	public int x;

	rend = GetComponent<Renderer>()
	rend.sharedMaterial = material[x];

### Change material texture (albedo/metallic/emission)



### Play model animation (?)


### Draw HUD


### Draw text


### Draw simple shapes


### How to store data


### Private\Public
	[HideInInspector]
	public float strength;

	[SerializeField]
	private float strength;


