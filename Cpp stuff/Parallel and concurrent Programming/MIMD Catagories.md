# Single Program Multiple Data 
#SPMD #SingleProgramMultipleData

SPMD multple processing units are running copies of same program but different data. 
Different from #SIMD or #SingleInstructionMultipleData  is that it does not have to run the same counter for all the programs. On all the Processors. 

#SPMD runs Acyncronously #SingleProgramMultipleData 
#SIMD runs synchronously(like the counter is on the same place) but parallel #SingleInstructionMultipleData 

# Multiple Program Multiple data. 
#MPMD #MultipleProgramMultipleData

This will be your build system example there will be a manager that runs a farm of build systems. 

Manager -> sends taks to Other processors. Then, it also keeps track of TaskCompleaction. 
Slaves -> runs the program copies with taks allocated based on data and programmes 