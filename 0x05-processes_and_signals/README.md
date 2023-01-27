# 0x05. Processes and signals
## Notes
	
A PID (i.e., process identification number) is an identification number that is automatically assigned to each process when it is created on a Unix-like operating system.

A *process* is an executing (i.e., running) instance of a program. Each process is guaranteed a unique PID, which is always a non-negative integer.

The process init is the only process that will always have the same PID on any session and on any system, and that PID is 1. This is because init is always the first process on the system and is the ancestor of all other processes. 
	
The default maximum value of PIDs is 32,767. This maximum is important because it is essentially the maximum number of processes that can exist simultaneously on a system.   
The file *pid_max*, which was introduced with the Linux 2.5 kernel, specifies the value at which PIDs wrap around (i.e., the value in this file is one greater than the maximum PID).   
A process can be thought of as an instance of a program in execution. We called this an ‘*instance of a program*’, because if the same program is run lets say 10 times then there will be 10 corresponding processes.   
Each process has its own unique process ID through which it is identified in the system. Besides it own ID, a parent’s process ID is also associated with a process.  
A ‘C’ program always starts with a call to main() function:  

    int main(int argc, int *argv[])

Example C code: 

```c
#include<stdio.h>

int main(int argc, char *argv[])
{
  int count = argc;
  printf("\n The number of arguments passed is [%d] \n", count);

  int c = 0;
  while(c < count)
  {
    printf("\n The argument [%d] is : [%s]\n", c+1, argv[c]);
    c++;
  }
  return 0;
}
```
The above C code prints the number of command line arguments passed to it, and also prints the value of each argument. The return value is always 0 on success. It returns that to the terminal. You can use bash shell special parameter *$?* as shown below to check the return value (0 indicates success).

    $echo $?
    0
## Links
+ What is Linux PID  
http://www.linfo.org/pid.html  
+ All about signals  
https://www.computerhope.com/unix/signals.htm  
+ Linux Process  
https://www.thegeekstuff.com/2012/03/linux-processes-environment/   
+ Linux Signals  
https://www.educative.io/answers/what-are-linux-signals   
+ man ps   
https://man7.org/linux/man-pages/man1/ps.1.html   
+ man grep   
https://man7.org/linux/man-pages/man1/pgrep.1.html   
