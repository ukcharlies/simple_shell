0x16. C - Simple Shell

Concepts

For this project, we expect you to look at these concepts:

1. Everything you need to know to start coding your own shell
2. Approaching a Project

Background Context
Write a simple UNIX command interpreter.

Resources
Read or watch:
1. Unix shell

2. Thompson shell

3. Ken Thompson

4. Everything you need to know to start coding your own shell concept page man or help:

5. sh (Run sh as well)

General Learning Objectives:
1. Who designed and implemented the original Unix operating system

2. Who wrote the first version of the UNIX shell

3. Who invented the B programming language (the direct predecessor to the C programming language)

4. Who is Ken Thompson?

5. How does a shell work!

6. What is a pid and a ppid?

7. How to manipulate the environment of the current process

8. What is the difference between a function and a system call?

9. How to create processes

10. What are the three prototypes of main?

11. How does the shell use the PATH to find the programs?

12. How to execute another program with the execve system call

14. How to suspend the execution of a process until one of its children terminates

15. What is EOF / “end-of-file”?

General Requirements:

1. Allowed editors: vi, vim, emacs

2. All your files will be compiled on Ubuntu 20.04 LTS using gcc, using the options -Wall -Werror -Wextra -pedantic -std=gnu89

3. All your files should end with a new line

4. A README.md file, at the root of the folder of the project is mandatory

5. Your code should use the Betty style. It will be checked using betty-style.pl and betty-doc.pl

6. Your shell should not have any memory leaks

7. No more than 5 functions per file

8. All your header files should be include guarded

9. Use system calls only when you need to (why?)

10. Write a README with the description of your project

11. You should have an AUTHORS file at the root of your repository, listing all individuals having contributed content to the repository. Format, see Docker

More Info

Output

1. Unless specified otherwise, your program must have the exact same output as sh (/bin/sh) as well as the exact same error output.

2. The only difference is when you print an error, the name of the program must be equivalent to your argv[0] (See below)
Example of error with sh:

$ echo "qwerty" | /bin/sh
/bin/sh: 1: qwerty: not found
$ echo "qwerty" | /bin/../bin/sh
/bin/../bin/sh: 1: qwerty: not found
$
Same error with your program hsh:

$ echo "qwerty" | ./hsh
./hsh: 1: qwerty: not found
$ echo "qwerty" | ./././hsh
./././hsh: 1: qwerty: not found
$

Compilation
Your shell will be compiled this way:

gcc -Wall -Werror -Wextra -pedantic -std=gnu89 *.c -o hsh Testing Your shell should work like this in interactive mode:

$ ./hsh
($) /bin/ls
hsh main.c shell.c
($)
($) exit
$
But also in non-interactive mode:

$ echo "/bin/ls" | ./hsh
hsh main.c shell.c test_ls_2
$
$ cat test_ls_2
/bin/ls
/bin/ls
$
$ cat test_ls_2 | ./hsh
hsh main.c shell.c test_ls_2
hsh main.c shell.c test_ls_2
$
