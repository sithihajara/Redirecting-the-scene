# Redirecting-the-scene

## Aim:

To Redirect the scene in the unity engine.
## Algorithm:


### Step 1 :
Create a new 3D scene in the unity and save it as Level1.

### Step 2 :
From the Hierarchy , select a plane , cube and a sphere and place in the scene. Scale of plane is (4,1,4) .Scale of Cube is (2,1,2).Scale of sphere is (1,1,1).

###  Step 3 :
Right Click on Assets , choose material and give color to your cube and sphere.

### Step 4 :
Add rigid body component to cube and sphere.

### Step 5 :
Select the sphere, in the inspector - select tag and add a new tag named "cube".And tag the cube in sphere inspector.

### Step 6 :
From File , create another scene and name that scene as "Level2".

### Step 7 :
Create a C# file named Prog and type the code required to redirecting the scene. And Add the C# file to the cube.

### Step 8 :
From File, select Build settings and add open scene.Both the scene should be added.

### Step 9 :
From Hierarchy , Select text and type " YOU WON ", and uncheck the text in inspector.

### Step 10 :
Slect the cube inspector , add the text object in the WinText feild under the C# file.

### Step 11 :
Compile and run the program, as a result when the sphere falls on the cube ,it gets disappeared and the text message will pop up on the scene . On clicking "R",the level1 scene will be redirected to Level2 scene.

## Program:
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.SceneManagement;

public class Prog : MonoBehaviour
{
    Rigidbody rb;
    public GameObject WinText;
    // Start is called before the first frame update
    void Start()
    {
        rb = GetComponent<Rigidbody>();
    }

    // Update is called once per frame
    void Update()
    {
        if (Input.GetKeyDown(KeyCode.R))
        {
            SceneManager.LoadScene("Level2");
        }
    }
    public void OnMouseDown()
    {
        Destroy(gameObject);
    }
    private void OnCollisionEnter(Collision collision)
    {
        if (collision.gameObject.tag == "cube")
        {
            Destroy(collision.gameObject);
            WinText.SetActive(true);
        }
    }
}
```
## Output:
### After the Ball hit the cube:
![244884206-4a4f0c08-db9c-46ca-b5ce-e2b7bc981f18](https://github.com/MEENA155/Redirecting-the-scene/assets/94677128/c721e22f-91ee-45a7-a5cf-2c44813738cf)

### Redirected scene:
![244884329-14013ead-d279-4acb-b879-56565f405532](https://github.com/MEENA155/Redirecting-the-scene/assets/94677128/63e11056-f3c9-4b0c-b15a-8a0595e3e05e)

## Result:
Thus redirecting a scene is done successfully in the unity engine.
