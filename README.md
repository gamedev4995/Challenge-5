# Challenge 5 - Go Ahead and Jump
For this challenge, we implemented action functions for our robot to move based on a player's input!

---

### Player Input Guide
| Actions                  | Mappings                               |
|--------------------------|----------------------------------------|
| Horizontal Movement      | A and D keys, Left and Right arrow     | 
| Vertical movement        | W and S keys, Up and Down arrow        |
| Shoot                    | Left Mouse Button, Left Touchpad Button|
| Jump                     | Spacebar                               | 
| Look                     | Mouse Delta                            |
| Fast Horizontal Movement |                                        | 
| Fast Vertical movement   |                                        |

## Rigid Body

## Capsule Collider

## Player Input 

## Terrain
aqui no va nada wow, solo lo añadi para point out que hicimos uno para que el robot tenga somewhere to land 

## Script

  ### Horizontal Movement 
  
  ### Vertical Movement 
  
  ### Fire
Before diving into the code for shooting, it's important to do the following steps beforehand:
1. Create a bullet prefab

For the bullet, we first created a sphere (GameObject > 3D Object > Sphere) and scaled it down to a small size.

<img width="300" alt="Screenshot 2024-10-04 134242" src="https://github.com/user-attachments/assets/acaf376c-14b3-4ffa-83da-45480abd67a4">

Then we created a new material by right clicking > Create > Material in the assets area or by clicking the ‘+’ symbol > Material.

<img width="385" alt="Screenshot 2024-10-04 133959" src="https://github.com/user-attachments/assets/0f89feb3-595c-4d58-b969-8d4ed8ec6944">

In the inspector tab of the material, within Surface Inputs, we changed the Base Map to our choice of color and added an emission for a glowing effect. 

<img width="300" alt="Screenshot 2024-10-04 134147" src="https://github.com/user-attachments/assets/f2be6b3f-7f4f-41d3-a2ce-977a74201218">

Then we dragged the material onto the sphere previously created. 

<img width="300" alt="Screenshot 2024-10-04 134252" src="https://github.com/user-attachments/assets/31d19f82-db86-46df-97ff-50adc5713589">

With the bullet’s look completed, we turned it into a prefab by dragging the object from the Hierarchy tab onto a prefab folder.

2. Create a new script

Within the prefab of the bullet, in the inspector tab, we created a new script (Add Component > New script) which we named “forwardMovement”. 
For this script, we added the public variable 'speed' and the following code for the purpose of providing movement for when the bullets are shot out.

<img width="500" alt="Screenshot 2024-10-04 160802" src="https://github.com/user-attachments/assets/0e0f3c9e-8f1a-4f60-95b8-3f25db26401b">

Lastly, in Unity, be sure to change the value of the speed.

<img width="350" alt="Screenshot 2024-10-04 161136" src="https://github.com/user-attachments/assets/eb0a6659-a6c3-46ef-9e1e-607e77ed9873">

3. Create empty object

For the character to shoot the bullets, we first had to create an empty object (GameObject > empty) which we referred to as ShootPoint, positioned it where we would want the bullets to come out of and then moved the object onto the hierarchy of the asset.

<img width="600" alt="Screenshot 2024-10-04 140608" src="https://github.com/user-attachments/assets/f022df58-7cca-44ba-ac3b-b7dc88f62510">

Back in with the movement script:

We added the following variables:

<img width="286" alt="Screenshot 2024-10-04 170922" src="https://github.com/user-attachments/assets/d7e90ed0-e2ed-4cc6-8f48-e34ed01035c8">

Continuing, we added the following OnFire function, based on the Fire action already established by Unity, that creates an instance/copy of the bullet prefab and positions it where the shooting point object is located once the left mouse button is pressed.

<img width="700" alt="Screenshot 2024-10-12 213631" src="https://github.com/user-attachments/assets/278a7512-6149-45f2-ae55-c195d39de72b">

Lastly, in Unity, drag the bullet prefab and the shootPoint empty onto their respective variables.

<img width="350" alt="Screenshot 2024-10-04 161206" src="https://github.com/user-attachments/assets/09a3b2d7-8a1d-45f6-ba20-fd0acf25a3e8">

Result:

![OnFireVid-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/f340f864-159e-43c1-99d6-667010abeeff)

  ### Jump 
In the player input actions, we added a new action by pressing on the '+' next to "Actions" to which we named "Jump".

<img width="400" alt="Screenshot 2024-10-12 214242" src="https://github.com/user-attachments/assets/1d55efc5-1711-4b21-8f84-b02d36c7a692">

Then, in the binding properties, next to "Path" we assigned the spacebar of the keyboard. This can be done by typing "spacebar" in the search bar or by pressing "listen" button and tapping the spacebar.

<img width="550" alt="Screenshot 2024-10-12 214500" src="https://github.com/user-attachments/assets/516e10de-fb6d-4917-b6b0-9f3d285c7dd8">

Back in our PlayerMove script, we added the following variable:

<img width="600" alt="Screenshot 2024-10-12 220509" src="https://github.com/user-attachments/assets/9978e12f-f7a7-469f-b31b-762737fecdb4">

_Note:_ Value can be changed for preference

Lastly, we added the following OnJump function, based on the Jump action we added, to allow the player to jump:

<img width="600" alt="Screenshot 2024-10-12 221303" src="https://github.com/user-attachments/assets/1f0b8f94-8c33-4c0d-81e7-46efc73835f4">

Result:

![OnJumpVid-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/116087e7-6317-419d-8073-17d4ae8111d2)

  ### Look
For the player to look around, we started off by adding the following variables:

<img width="600" alt="Screenshot 2024-10-12 220221" src="https://github.com/user-attachments/assets/652ef5ad-d44e-4241-a473-13aae004e5eb">

Then, we added the following OnLook function, based on the Look action already established by Unity:

<img width="550" alt="Screenshot 2024-10-12 221608" src="https://github.com/user-attachments/assets/9f5203a6-2ef0-4cc5-acf9-601d391218d7">

Lastly, with the lookValue, we can apply the rotation in the Update() with the following code:

<img width="650" alt="Screenshot 2024-10-12 221826" src="https://github.com/user-attachments/assets/f49f9ebc-0049-49ee-9d66-1d0495fb859b">

Result:

![OnLookVid-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/ba801ab6-6eac-47af-9dcd-4e1e8cc0a5bf)

  ### Fast Horizontal Movement 
  
  ### Fast Vertical Movement

## Result

[gif]




