# CS252-Project
 
# Question 3.21

## Question
The Collatz conjecture concerns what happens when we take any positive integer n and apply the following algorithm:  
n = { n∕2, if n is even  
      3 × n + 1, if n is odd  
The conjecture states that when this algorithm is continually applied,
all positive integers will eventually reach 1.  
For example, if n = 35, the sequence is
35, 106, 53, 160, 80, 40, 20, 10, 5, 16, 8, 4, 2, 1  
Write a C program using the fork() system call that generates this
sequence in the child process. The starting number will be provided
from the command line. For example, if 8 is passed as a parameter on
the command line, the child process will output 8, 4, 2, 1. Because the
parent and child processes have their own copies of the data, it will be
necessary for the child to output the sequence. Have the parent invoke
the wait() call to wait for the child process to complete before exiting
the program. Perform necessary error checking to ensure that a positive
integer is passed on the command line.

## Output :

![Project Image](https://github.com/shama-shankar/CS252-Project-shama-shankar/blob/main/3.21/A1.jpeg)

## Explanation of the code

## Input
```
 int num, stat_loc = 0;
  pid_t pid;
  printf ("Enter the number:");
  scanf ("%d", &num);
```
## Datatype
The *pid_t* is the datatype used. It is capable of representing a process ID.

## Functions 

1. Collatz - It is a user defined function that performs the algorithm mentioned in the problem statement. 

2. int main() - This is the main function. The system calls fork() and wait() are called in this part.
## Working of the code

<li> Input is taken from the user</li>
 <li> Then <code>fork()</code> is called and the child process is created.</li>
<li><code>if(pid==0)</code> only then the program allows the child process to run the code inside if statement. So child process runs the Collatz Conjecture. </li> 
<li>The parent process will be waiting for the child process to finish its execution because of the <code>wait(NULL)</code> statement.</li>
<li>The child process after completion exits and invokes the wait call and the parent process is prompted to resume its action.</li>
<li>Eventually parent process will also be terminated.</li>
</ul>

## More information about System Calls

### 1. fork()
Fork system call is used for creating a new process, which is called child process, which runs concurrently with the parent prrocess.
It takes no parameters and returns an integer value.  
Different return types of fork() are
1)	Positive value- returned to parent, and the value is the  process id of the newly created child process.
2)	Zero- return to the child process.
3)	Negative – child process creation was not successful

### 2. wait()
A call to wait() blocks the calling process until one of its child processes exits or a signal is received. After child process terminates, parent continues its execution after wait system call instruction.  


## References:

* https://www.includehelp.com/c/process-identification-pid_t-data-type.aspx
* https://www.geeksforgeeks.org/wait-system-call-c/
* https://www.geeksforgeeks.org/fork-system-call/

 

