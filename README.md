# Ex3---Hurdle-Game-2D

## AIM:

To develop a 2D game using C# program in unity .

## ALGORITHM:

STEP 1:Create a 2D project in unity.

STEP 2:Add player,hurdles,coins,track in the frame and add the valid collider2D component.

STEP 3:Click Assets->Create-># Script.

STEP 4:create player.cs and coinmanger script and add c# code.

STEP 5:Click canvas->Gamemanager->add Score and value.

STEP 6:Drag the script to player and coin.

STEP 7:Run the scene and display the output.

## PROGRAM:

Developed by: M.Pavithra

Register no: 212222100032

### player.cs:
```
using System.Collections;
using System.Collections.Generic;
using System.Runtime.CompilerServices;
using UnityEditor;
using UnityEngine;


public class ex3 : MonoBehaviour
{
    public float speed;
    public float jumpforce;
    private Rigidbody2D rb;
    public Score cc;

    void Start()
    {
        rb = GetComponent<Rigidbody2D>();
    }

    void Update()
    {
        float moveInput = Input.GetAxisRaw("Horizontal");
        transform.position += new Vector3(moveInput, 0, 0) * speed * Time.deltaTime;

        if (Input.GetKeyDown(KeyCode.Space) && Mathf.Abs(rb.velocity.y) < 0.001f)
        {
            rb.AddForce(new Vector2(0, jumpforce), ForceMode2D.Impulse);
        }
    }
    private void OnTriggerEnter2D(Collider2D other)
    {
        if(other.CompareTag("Destroy"))
        {
            cc.coincount++;
            Destroy(other.gameObject);
        }
    }
}
```

### Coin Manager:
```using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.UI;

public class Score : MonoBehaviour
{
    public int coincount;
    public Text value;
    // Start is called before the first frame update
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        value.text = coincount.ToString();
    }
}
```
## OUTPUT:

![Screenshot 2024-03-21 111748](https://github.com/22008686/Ex3---Hurdle-Game-2D/assets/118916413/ce4761db-da32-4bab-8464-2b91658279f9)

![Screenshot 2024-03-21 111903](https://github.com/22008686/Ex3---Hurdle-Game-2D/assets/118916413/bb23c8d6-c347-40ac-8b4b-6b2b4c72804a)


## RESULT:

Thus a 2D game using C# program in unity is developed successfully.
