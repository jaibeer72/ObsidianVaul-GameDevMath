

We need to understand how memory organised cause if we cannot access memory fast enough, then we will not be able to do shhhitt! 



|Shared #SharedMemory| Distributed Memory #DistributedMemory|
|-------|---------------------|
|Every process can see changes in shared memory| opposite| 
|Types : Uniform Memory Access and Non Uniform memory access| |


## Shared memory 
### Uniform Memory access 
- All processors have equal access to memory 
#### Architectures
- SMP or Symmetric MultiProcessing #SMP-Memory-Architecture 
	- In SMP ![[Screenshot 2023-09-26 at 11.35.29.png]]
### Non Uniform Memory access


# Memory Problems to look out for 
#CashCoherency-Problem 
when the local cash of a CPU updates a value in the shared memory . this value when it's not updated on the Shared memory before another process uses the value is called the CashCoherancy Problem.
