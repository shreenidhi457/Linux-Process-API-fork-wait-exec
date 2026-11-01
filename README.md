# Linux-Process-API-fork-wait-exec-
Ex02-Linux Process API-fork(), wait(), exec()
## Name:Shreenidhi S
## Register no: 212225040410
# Ex02-OS-Linux-Process API - fork(), wait(), exec()
Operating systems Lab exercise 


# AIM:
To write C Program that uses Linux Process API - fork(), wait(), exec()

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Write the C Program using Linux Process API - fork(), wait(), exec()

### Step 3:

Test the C Program for the desired output. 

# PROGRAM:

## C Program to create new process using Linux API system calls fork() and getpid() , getppid() and to print process ID and parent Process ID using Linux API system calls


~~~
#include <stdio.h>
#include <sys/types.h>
#include <unistd.h>
#include <sys/wait.h>

int main()
{
    pid_t pid;

    pid = fork();

    if (pid == 0)
    {
        printf("Child process ID: %d\n", getpid());
        printf("Parent process ID: %d\n", getppid());
    }
    else
    {
        wait(NULL);
        printf("Parent process ID: %d\n", getpid());
    }

    return 0;
}


~~~







## OUTPUT
<img width="888" height="161" alt="Screenshot 2026-11-01 203033" src="https://github.com/user-attachments/assets/8c848cbd-eb21-4d51-9f24-a58f4fdea555" />








## C Program to execute Linux system commands using Linux API system calls exec() , exit() , wait() family





~~~

#include <stdio.h>
#include <stdlib.h>
#include <sys/wait.h>
#include <unistd.h>

int main()
{
    int status;

    printf("Running ps with execlp\n");

    if (fork() == 0)
    {
        execlp("ps", "ps", "-f", NULL);
        exit(1);
    }

    wait(&status);

    printf("Done.\n");

    return 0;
}
~~~




















## OUTPUT
<img width="872" height="230" alt="Screenshot 2026-11-01 203049" src="https://github.com/user-attachments/assets/72ef5a3c-636f-436a-ae3e-c2f454ef4c0f" />


















# RESULT:
The programs are executed successfully.
