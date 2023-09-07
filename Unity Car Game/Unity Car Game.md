# Introduction  The car game assignment was made to test my abilities to make things work. This summary will be divided into Features Below. 

- Game Setup
- NavMesh And Player Inputs (with event-driven programming)
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

### Discussing Events System

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

```mermaid 
classDiagram
    class Events {
        <<abstract>>
        +registerEvent(eventType: string, event: function): void
        +invokeEvent(eventType: string, args: any): void
    }
    
    class GameEvents {
        -gameStartEvent: function
        -gameEndEvent: function
    }
    
    class BoardEvents {
        -boardSetupEvent: function
        -boardResetEvent: function
    }
    
    class InputEvents {
        -keyPressEvent: function
        -mouseClickEvent: function
    }
    
    class EventListeners {
        +onGameStart(callback: function): void
        +onGameEnd(callback: function): void
        +onBoardSetup(callback: function): void
        +onBoardReset(callback: function): void
        +onKeyPress(callback: function): void
        +onMouseClick(callback: function): void
    }
    
    class EventInvokers {
        +invokeGameStart(args: any): void
        +invokeGameEnd(args: any): void
        +invokeBoardSetup(args: any): void
        +invokeBoardReset(args: any): void
        +invokeKeyPress(args: any): void
        +invokeMouseClick(args: any): void
    }
    
    Events <|-- GameEvents
    Events <|-- BoardEvents
    Events <|-- InputEvents
    Events "1" o-- "1" EventListeners : uses
    Events "1" o-- "1" EventInvokers : uses

```
![[mermaid-diagram-2023-09-06-185228.png]]




this for me has been really good as once we have this base it can decrease development times and make code really modular. Loosly coupled code can also lead to easy bug fixing but! 
in the end of the day, events are basically loops that can be invoked at anytime. If not made to be asynchronous or not handled well could lead to a lot of overhead. 

In my experience, this has not yet happened as event listeners do not usually exceed a number. Also, if things are clearly labelled 

### Controlling the player
hence we came up with this Events system where we have different events based on different event classes. 

```Csharp
public static class BoardActionsEvents
{
    public static UnityEvent<Vector3> WayPointChangeEvent = new UnityEvent<Vector3>();
}
```


using public static events we know that we can easily allow any listener that needs to know this event happen can do the necessary things. This also allows us to move away from MonoBehivior a little bit cause now we don't need to create a check in Update() to see if the waypoint has changed. now we can simple just invoke the event once an InputProvider calls the event. 

The second major problem we can have is multiple invokers at the same time. Haveing multiple invokers can cause bugs as there will be a lot of systems working on 2 invokes one after the other which can cause the wrong value to be observed. 

In the new InputSystem this means that we can more easily change this code by reading the Vec2 provided by the system. 

The current version is on the old input systems. 


```Csharp
// WaypointManager.cd 
if(Input.GetMouseButtonDown(0))
        {
            Ray ray = mainCamera.ScreenPointToRay(Input.mousePosition);
            RaycastHit hit;
            if (Physics.Raycast(ray, out hit))
            {
                NavMeshHit navMeshHit;
                if (NavMesh.SamplePosition(hit.point, out navMeshHit, 2.0f, NavMesh.AllAreas))
                {
                    BoardActionsEvents.WayPointChangeEvent.Invoke(navMeshHit.position);
                }
            }
        }
```
We have not isolated this code and it can be encapsulated by the new input system without having to do drastic refactoring 

On the player controller side, we have 
```Csharp 
// PlayerController.cs 
public class PlayerController : MonoBehaviour
{
    public NavMeshAgent agent;
    [SerializeField]
    public PlayerStatsData playerStatsData_Model;
    // Start is called before the first frame update
    void Start()
    {
        Debug.Assert(playerStatsData_Model != null, "PlayerStatsData_Model is not assigned in the editor.");

        agent = GetComponent<NavMeshAgent>();
        // reset data when game starts for later. 
        playerStatsData_Model.ResetDataForObservable(); 
        BoardActionsEvents.WayPointChangeEvent.AddListener(OnWayPointChange);
    }
    private void OnDestroy()
    {
        BoardActionsEvents.WayPointChangeEvent.RemoveListener(OnWayPointChange);
    }
    private void OnWayPointChange(Vector3 arg0)
    {
        agent.SetDestination(arg0);
    }
}
```

this logic is not separated. (Again this is the final code I will be coming to the PlayerStatsData on the Data-driven part )

On the AISide at this point, we could do similar things in the AIObject pool. This listens to the AI's Despwan event and then acts accordingly.  

```Csharp 
// AI/AIObjectPool.cs 
{
	//...in Awake 
        AIEvents.DespwnAI.AddListener(OnDespwnAI);
    }

    private void OnDespwnAI(GameObject arg0)
    {
        // Find the AI object in the dictionary and set it to false
        // then set the game object to false
        DisableAI(arg0);
    }

    private void DisableAI(GameObject arg0)
    {
        if (IsAiAliveDictionary.ContainsKey(arg0))
        {
            IsAiAliveDictionary[arg0] = false;
            arg0.SetActive(false);
            _CurrentOnBoard--;
        }
    }
```


![[Screenshot 2023-09-07 at 11.26.43.png]]