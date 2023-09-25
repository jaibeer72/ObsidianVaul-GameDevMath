
# CPU scheduling and processes.


The manager resolves conflicts to take a call. 
Deadlock management happens in an OS level. 

OS allows the User to communicate between computer and hardware nothing new here 

## Types of OS. 

| Uni  Programming | MultiProgramming| 
|-------------------|-------------------|
| Runs on a single program at at time| Runs on multiple progarms at once |
|  eg ATM Machine or single task ones | Run's multiple things like Windows| 

Preemptive and non-preemptive OS. 

- OS has multiple programs at the same time in memory, ready to be executed. 

Preemptive is when you have programs that allow 2 programs to use the CPU process for time periods. 

like eg P1 and P2 are 2 programers 

it will run P1(dt)->P2(dt)->P1(dt).. so on till P1 and P2 are done. 

so rather than 
wait for(p1) then run P2 which is non preemptive 
#CPU #Premptive #NonPreemptive

Process Control Block / Reprasents a process 
- Has all the information about the process 
	- Instructions. 
	- Pointer to the line of code (Program Counter) #ProgramCounter 
	- ProcessId
	- Registers
	- Process state
	- FilePointers  Rosources infomation

The representation of a Process control block will be on class or structure. 

Certain processes are I/O Bound processes. 
- Accessing the Disk 
- Waiting on the input. 
- Putting the output somewhere 
- Network access. 

Disk -> RAM -> CPU Executes 
IO bound processes the CPU is idle. 


## Problems due to CPU scheduling 
- Context Switching 
	- When one process is being prioritised over the other. 
	- Too many context switching is a bad Idea 

#algorithms #CPUSceduling

## FCFS ( first come first Serve) 
this is a CPU algorithm based on Queue 


so this world ons 

Time is Theoritial algo times infer it. 
or past dated. 

so 

| PID | ArrivalTime | Time To Complete | 
| --- | ---------- |--------------------|
| 1 | 1| 4| 
|2|2|3| 
![[Screenshot 2023-09-25 at 13.13.35.png]]
so in the above

so empty no process at time 1 

