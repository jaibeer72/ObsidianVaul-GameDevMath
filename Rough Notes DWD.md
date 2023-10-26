Interview. 

1. What is the difference between stack and heap memory allocation in C++?
	1. - Stack allocation is basically on the single use for the scope it's on it is usually just a memoy allocated on the first slot. 
- Heap allocation is on the specifc pointer to be put on the refrence. I son't know how to descirbe it help me 
2. Explain the role of pointers in C++ and why they are important in game engine development.
	1. The main use of pounterts is to "Point" to a memory location of an object. The idea is to have a refrence to all the memory so we can do proper memory management. 
3. How do you manage memory in C++ to avoid memory leaks and ensure efficient memory utilization?
	1. In the new wer version we use smart pointers with weak, shared and unique pointers. thses pointers can be alocated and destroed using new and delete . 
	2. In older version we use malloc and alloc. (Please tell me the difference between thses and what they do ? ) they use free to delete them meory . 
	3. also maintingin a refrence counts for things we creat. I think one way can be having a static refCount in each class created. 
4. Can you describe the process of designing and implementing a game engine feature from scratch?
	1. Break the feature down to its most nessasites. 
	2. Do a full requirement analysis for each feature. 
	3. see if its' SOLID ( go over everything SOLD)
	4. Check dependencies. 
	5. Write a rough version see if it can be done with a TDD. 
	6. Test bug fix so on.
5. What are some common techniques for profiling and optimizing code for speed and memory in a game engine?
	1. Memory is always first cause you can easily see where the problems lie when it comes to meomory. We have good memory profiles built into things like visual studio and we can also create our own Macros. 
	2. CPU : We have great tools by intel AMD and as well the game engine providers that will hook onto a game and give us exact CPU calls being made and how often per frame . we can record high intense aries and see what could be causing the worst of it. 
	3. GPU : rednder docs and draw calls , with also texture allocation deallocation. catching GPU draw errors or overdraws ( explain over draw to me if that is  a thing)
6. How can you run tasks concurrently safely and efficiently in a multi-threaded game engine environment?
	1. mutex or locks can help. to ame sure things are in progres 
	2. Basically we are woirreid about 3 things Deadlocks, Race condition and starvations. 
	3. Deadlocks is when threads wait for each other to release to access a memory, this is when we do not unlock. we can deal with this by basically using a "tryLock" then unlock after a couple cycles if context has been sqitched / give me exmple code for this Chat 
	4. Again the above to manage race cointidion. 
	5. actually no idea bout this.
7. What is the purpose of a mutex, and how is it used in multithreaded programming?
8. What is the role of a game engine's renderer, and how does it interact with other engine components?
9. Describe your experience with concurrent programming, including any challenges you've encountered and solutions you've implemented.
10. Can you explain the difference between Unreal Engine 4 and Unreal Engine 5, and which one do you have experience with?
11. Have you worked on any game projects that involved developing a custom game engine or renderer? If so, describe your contributions.
12. What techniques and tools do you use for optimizing CPU performance in a game engine?
13. How can you optimize GPU performance in a game engine, and what role does the graphics pipeline play in this process?
14. Have you worked on a game project that was released on consoles? What challenges did you face in console development?
15. Explain the principles of shared ownership and how they apply to collaborative game development.
16. Can you describe a situation where you had to facilitate communication between different disciplines within a game development team?
17. How do you ensure that the code you write is maintainable and follows best practices in a collaborative development environment?
18. What are some modern rendering techniques and pipelines you are familiar with and how do they impact game graphics quality?
19. Describe the components of a typical game engine architecture and their interactions.
20. How do you handle memory fragmentation in a long-running game engine?
21. Can you explain the benefits and challenges of using entity-component systems (ECS) in game engine development?
22. What is a virtual function, and how is it used in C++ game development?
23. Discuss the role of shaders in game rendering and the types of shaders commonly used.
24. How do you approach debugging and profiling a game engine to identify and resolve performance bottlenecks?
25. What's your experience with Unreal Engine's scripting system, and how does it contribute to game development?