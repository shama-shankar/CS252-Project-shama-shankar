# CS252-Project
 
 # Question 4.23

## Question:

Write a multithreaded program that outputs prime numbers. This program should work as follows: The user will run the program and will
enter a number on the command line. The program will then create a
separate thread that outputs all the prime numbers less than or equal to
the number entered by the user.

Output :

![Project Image](https://github.com/shama-shankar/CS252-Project-shama-shankar/blob/main/4.23/A2.jpeg)

## Explanation of code snippets

### Input : 
User input is taken through a local variable n

```
        int n; 

        printf("\n Input Thread \n");
	    printf("Enter a number: ");
	    scanf("%d",&n);
```
### Datatype :
*pthread_t* is the datatype used as it can uniquely identify a thread.
### Functions :

### **1. Function *pthread_join():***

```
        pthread_join(th1,NULL);
```
The pthread_join() function allows the calling thread to wait for the ending of the target thread. If that thread has already been terminated, then
pthread_join() returns immediately. *th1* is the thread to wait for. Second parameter usually stores the location where exit status of the joined thread is stored. We have set it to NULL as we do not require the exit status.

### **2. Function *pthread_create():***
```
        pthread_create(&th1,NULL,thread1,&n);
```
Looking at each argument:

  1. &th1 :
     It is the pointer to the data type for threads as per "pthreads.h" library.
  2. NULL :
     It is an attr pointing to a  structure whose contents are used at thread creation time to determine attributes for the new thread. We use NULL as we want thread with its default attributes.
  3. thread1 : It is a pointer to the start_routine of a thread. start_routine() is the function invoked on the thread creation.
  4. Fourth Argument is *the sole* argument passed to start_routine() when invoked during thread creation. In our case it is NULL i.e. no arg is passed to our start_routine.
  5. On success, these functions return 0. On error, they return a nonzero number.


###  **3. Function \**thread1(void *arg)****

This is a user defined function which calculates the prime numbers less than the input and gives an appropriate output.




## References :


* https://github.com/Ayush3910/OS-Project
* https://www.geeksforgeeks.org/multithreading-c-2/
* https://man7.org/linux/man-pages/man3/pthread_join.3.html
* https://www.ibm.com/docs/en/zos/2.3.0?topic=functions-pthread-create-create-thread#ptcrea

