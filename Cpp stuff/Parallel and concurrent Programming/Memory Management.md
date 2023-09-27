

We need to understand how memory organised cause if we cannot access memory fast enough, then we will not be able to do shhhitt! 



|Shared #SharedMemory| Distributed Memory #DistributedMemory|
|-------|---------------------|
|Every process can see changes in shared memory| Each Process has it's own local memory, so no global access space.| 
|Types : Uniform Memory Access and Non Uniform memory access| change to local is not accessed to another.  |


## Shared memory 
#SharedMemory 
### Uniform Memory access 
- All processors have equal access to memory 
#### Architectures
- SMP or Symmetric MultiProcessing #SMP-Memory-Architecture 
	- In SMP ![[Screenshot 2023-09-26 at 11.35.29.png]]
### Non Uniform Memory access 
#Non-Uniform-Memory-Accesss 
this is a collection of multiple #SMP-Memory-Architecture put together. 
![[Screenshot 2023-09-26 at 11.44.42.png]]

sometimes does not scale well and takes longer to access things cause some processors might have quicker access 

But! all processes can see everything. 
this does not scale well cause well... cause it becomes a lot of comms my boi ! too much traffic

## Distributed Memory. 
- Each proces has it's own local memory\
- connected thorugh a network and the change is not automatically refeclted 
- this network can be ethernet 
- BUT ! this is highly scaleable. This can allow us to use off the shelf computers and do things with them. 
# Memory Problems to look out for 
#CashCoherency-Problem 
when the local cash of a CPU updates a value in the shared memory . this value when it's not updated on the Shared memory before another process uses the value is called the CashCoherancy Problem.
