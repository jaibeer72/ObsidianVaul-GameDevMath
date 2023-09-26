# Process 
#process

Contains 
- Code 
- Data 
- state information 
Each process is independent and has its own address space. 

A Computer can have multiple and have to manage them. 

- To communicate between Process we need 
	- Sockets and Pipes #Sockets and #Pipes 
	- Inter-process #SharedMemory space. 
	- Or #RemoteProceadureCalls
# Thread 
#thread 

The sub-process is called a thread. 
These are the basic units of a process. These are independent, too and are a part of a process. 

Threads that belong to the same process have access to the same address space. 

Sharing resources is not equal to thread or process.  #SharedMemory between the same process 


```run-cpp 
#include <thread>
#include <chrono>
#include <unistd.h>

// a simple function that wastes CPU cycles "forever"
void cpu_waster() {
    printf("CPU Waster Process ID: %d\n", getpid());
    printf("CPU Waster Thread ID %d\n", std::this_thread::get_id());
    while(true) continue;
}

std::cout<<"Main Process ID:" << getpid() <<"\n";

std::thread thread1(cpu_waster);
std::thread thread2(cpu_waster); 

    while(true) { // keep the main thread alive "forever"
        std::this_thread::sleep_for(std::chrono::seconds(1));
    }



```

Read more on #POSIX #Cigwin
