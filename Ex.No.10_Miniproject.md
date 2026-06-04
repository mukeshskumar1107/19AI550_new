# Ex.No: 10  Implementation of 2D/3D game - ForestEscape
### DATE:25/05/2026                                                                            
### REGISTER NUMBER : 212223240099
### AIM: 
To develop a ForestEscape Game in Unity 
### Algorithm:
```
1. Create a new 2D project in Unity.
2. Import background, ground tiles, player, coin, and enemy assets into the project.
3. Add a background image and create ground platforms using tiles.
4. Add Box Collider 2D components to the ground objects.
5. Add a Player GameObject with Rigidbody2D and Box Collider 2D components.
6. Create and attach a PlayerMove script to move and jump the player using keyboard input.
7. Add Coin GameObjects with Circle Collider 2D and enable “Is Trigger”.
8. Create and attach a CoinCollect script to destroy coins when the player touches them.
9. Add Enemy GameObjects and detect collision with the player to restart or end the game.
10. Add camera follow, score display, background music, test the game, and build the final executable file.
```  
### Program:
#### PlayerMove.cs
```
using UnityEngine;

public class PlayerMove : MonoBehaviour
{
    public float speed = 5f;
    public float jumpForce = 7f;

    Rigidbody2D rb;

    void Start()
    {
        rb = GetComponent<Rigidbody2D>();
    }

    void Update()
    {
        float move = Input.GetAxis("Horizontal");

        rb.linearVelocity = new Vector2(
            move * speed,
            rb.linearVelocity.y
        );

        if (Input.GetKeyDown(KeyCode.Space))
        {
            rb.linearVelocity = new Vector2(
                rb.linearVelocity.x,
                jumpForce
            );
        }
    }
}
```
#### CoinCollect.cs
```
using UnityEngine;

public class CoinCollect : MonoBehaviour
{
    private void OnTriggerEnter2D(Collider2D other)
    {
        if(other.CompareTag("Player"))
        {
            Destroy(gameObject);
        }
    }
}
```
### Output:
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/569649ad-c125-4be3-ae5f-de358559b360" />
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/9dbb01c3-e9a7-468e-a03d-74f7def24d8c" />


### Result:
Thus the game ForestEscape was developed using Unity.
