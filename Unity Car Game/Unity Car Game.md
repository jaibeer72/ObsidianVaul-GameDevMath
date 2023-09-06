# Introduction  The car game assignment was made to test my abilities to make things work. This summary will be divided into Features Below. 

- Game Setup
- NavMesh And Player Inputs 
- Event-Driven Programming 
- Object pooling for AI and Collectables 
- Event-based Explosion spanning 
- Data-Driven Player Stats and Game Configuration 
- UI MVP closeness is a designer-friendly approach.
- Scene Composition to easily add or subtract 


## Game Setup

The game setup was easy. All that was needed to be done was set up the player play area. Put the cars in and ensure the textures are applied, then add them to the prefabs. 

Lastly, setting up the MainCamera to a viable position for gameplay. I like the more isometric view, so I placed it that way.


![[Screenshot 2023-09-06 at 19.21.34.png]]
This is the base of what the end product looks like but the idea is similar. 
Once the setup was done i knew the main model i wanted to push for. 

## NavMesh And Player Inputs 

So when I came to this I wanted it to be as extendable as possible. If needed later we could also shift to the new input system if needed. 

So the criteria for controlling the players and the AI was 
- Isolated Independent systems 
- Singular functionality. 
- Independently testable 
- Debuggable. 

so to start of as I did want to make this fast to be developed I decided to use NavMeh and unities inbuilt systems to get it up and running fast. 

Things we knew we had to do for the player 
- set up the navmesh 
- get the world point from the screen point 
- set the AI's destination. 
- Set up the Rigidbody to make sure we can run them individually. 

So first i needed an input manager sort of class. Initially i was making it so to change waypoints so this class can listen to inputs later. If or when we get the new input systems. 

The overarching design of the Game I wanted to make it so that we can 

``


