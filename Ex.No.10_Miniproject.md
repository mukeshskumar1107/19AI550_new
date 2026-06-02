# Ex.No: 10  Implementation of 2D game using c# language and AI technology.
### DATE: 21-05-26                                                                        
### REGISTER NUMBER : 212223240099
### AIM: 
 To develop a 2D Mario-style platformer game in Unity with coin collection, enemy interaction, and score display using c# language and AI.
### Algorithm:
```
1. Initialize Unity project with 2D settings
2. Create Mario player controller with movement and jump logic
3. Design levels using tilesets and add colliders
4. Add coin prefabs and place them in levels
5. Detect coin collection and update score in UI
6. Detect player death (e.g., fall or enemy hit)
7. Show final coin score on death or level complete
8. Add enemies and simple AI (e.g., patrol behavior)
9. Create main menu and restart level functionality
10. finally, Character perfoms following things in Game:
    side-scrolling stages while avoiding hazards such as enemies
    and pits with the aid of power-ups such as the Super Mushroom,
    Fire Flower, and Starman.

```  
### Program:
```
using UnityEngine;

public class PlayerMovement : MonoBehaviour
{
    public float speed = 5f;
    public float jumpForce = 7f;

    private Rigidbody2D rb;
    private float moveInput;

    void Start()
    {
        rb = GetComponent<Rigidbody2D>();
    }

    void Update()
    {
        moveInput = Input.GetAxis("Horizontal");

        if (Input.GetKeyDown(KeyCode.Space))
        {
            rb.linearVelocity = new Vector2(rb.linearVelocity.x, jumpForce);
        }
    }

    void FixedUpdate()
    {
        rb.linearVelocity = new Vector2(moveInput * speed, rb.linearVelocity.y);
    }
}
```
### Output:
<img width="1919" height="954" alt="image" src="https://github.com/user-attachments/assets/4df42843-5325-47e4-92df-b48de1ea1aed" />



### Result:
Thus the game in Unity  using c# language and adopted AI technology.
