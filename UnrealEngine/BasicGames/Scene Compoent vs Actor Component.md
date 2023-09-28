### Formal Explanation:

|**Component Type**|**Description**|
|---|---|
|`ActorComponent` #ActorComponent|Base class for components that are attached to actors and are updated automatically each frame. They do not have a transform and don't know about the world they are in.|
|`SceneComponent` #SceneComponent|Inherits from `ActorComponent` and adds a transform (location, rotation, scale). It serves as a base class for all components that can be attached to a scene.|

### Explanation Like I’m 5:

Imagine you have a toy robot:

- **`ActorComponent`**: Think of this like the robot's battery. It is a part of the robot, but it doesn't know where the robot is. It just gives it power to move and do things.
- **`SceneComponent`**: Now, think of this like the robot's arm. It is also a part of the robot, but it knows where it is (like up or down, left or right). It can move around and do things in a certain place.

So, `SceneComponent` is like parts of a toy that know where they are and can move, while `ActorComponent` is like parts that help the toy work but don’t move by themselves.