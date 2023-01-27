# 0x05. Processes and signals
## Notes
	
A PID (i.e., process identification number) is an identification number that is automatically assigned to each process when it is created on a Unix-like operating system.

A process is an executing (i.e., running) instance of a program. Each process is guaranteed a unique PID, which is always a non-negative integer.

The process init is the only process that will always have the same PID on any session and on any system, and that PID is 1. This is because init is always the first process on the system and is the ancestor of all other processes. 
	
The default maximum value of PIDs is 32,767. This maximum is important because it is essentially the maximum number of processes that can exist simultaneously on a system.   
The file *pid_max*, which was introduced with the Linux 2.5 kernel, specifies the value at which PIDs wrap around (i.e., the value in this file is one greater than the maximum PID).

## Links
+ What is Linux PID  
http://www.linfo.org/pid.html  
+ All about signals  
https://www.computerhope.com/unix/signals.htm  
+ Linux Process  
https://www.thegeekstuff.com/2012/03/linux-processes-environment/   
+ Linux Signals  
https://www.educative.io/answers/what-are-linux-signals   
