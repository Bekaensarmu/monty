0x19. C - Stacks, Queues - LIFO, FIFO

In this project, we created a simple interpreter for Monty ByteCodes. The interpreter reads a bytecode file and executes the bytecode commands.

The Monty language
Monty 0.98 is a scripting language that is first compiled into Monty byte codes (Just like Python). It relies on a unique stack, with specific instructions to manipulate it. The goal of this project is to create an interpreter for Monty ByteCodes files.

Monty byte code files
Files containing Monty byte codes usually have the .m extension. Most of the industry uses this standard but it is not required by the specification of the language. There is not more than one instruction per line. There can be any number of spaces before or after the opcode and its argument:

Objectives:
To know what LIFO and FIFO mean
To know what a stack is, and when to use it
To know what a queue is, and when to use it
To know the common implementations of stacks and queues
To know the most common use cases of stacks and queues
To know the proper way to use global variables

Environment
Ubuntu 14.04 LTS via Vagrant in VirtualBox and compiled with GCC version 4.8.4

Instructions
Resources📚
Read or watch:

Google
Create dynamic libraries on Linux

General Requirements
Allowed editors: vi, vim, emacs
All files is compiled on Ubuntu 20.04 LTS using gcc, using the options -Wall -Werror -Wextra -pedantic -std=gnu89
All files ends with a new line
There is README.md file at the root of the alx-low_level_programming
Maximum of one global variable is allowed
No more than 5 functions per file
The C standard library is allowed
The prototypes of all the functions were included in the header file called monty.h
All the header files are include guarded

Intructions basics
Compiling the program: gcc -Wall -Werror -Wextra -pedantic *.c -o monty

File Monty:

julien@ubuntu:~/monty$ cat -e bytecodes/000.m
push 0$
push 1$
push 2$
  push 3$
                   pall    $
push 4$
    push 5    $
      push    6        $
pall$
julien@ubuntu:~/monty$

Struct:

/**
 * struct instruction_s - opcode and its function
 * @opcode: the opcode
 * @f: function to handle the opcode
 *
 * Description: opcode and its function
 * for stack, queues, LIFO, FIFO Holberton project
 */
typedef struct instruction_s
{
        char *opcode;
        void (*f)(stack_t **stack, unsigned int line_number);
} instruction_t;

Example

vagrant@vagrant-ubuntu-trusty-64:~/monty$ cat bytecodes/00.m
push 1
push 2
push 3
pall
vagrant@vagrant-ubuntu-trusty-64:~/monty$ gcc -Wall -Werror -Wextra -pedantic *.c -o monty -g
vagrant@vagrant-ubuntu-trusty-64:~/monty$ ./monty bytecodes/00.m
3
2
1
vagrant@vagrant-ubuntu-trusty-64:~/monty$

List of files/Descriptions:
S/N	Files	Description
1.		
2.		
3.		
4.		
5.		

Tasks

0. push, pall
The push opcode
-The opcode push pushes an element to the stack.
The pall opcode
-The opcode pall prints all the values on the stack, starting from the top of the stack.

1. pint
The pint opcode

The opcode pint prints the value at the top of the stack, followed by a new line.
The pint opcode

2. pop
The pop opcode

The opcode pop removes the top element of the stack.

3. swap
The swap opcode

The opcode swap swaps the top two elements of the stack.

4. add
The add opcode

The opcode add adds the top two elements of the stack.

5. nop
The nop opcode

The opcode nop doesn’t do anything.

6. sub
The sub opcode

The opcode sub subtracts the top element of the stack from the second top element of the stack.

7. div
The div opcode

The opcode div divides the second top element of the stack by the top element of the stack.

8. mul
The mul opcode

The opcode mul multiplies the second top element of the stack with the top element of the stack.

9. mod
The mod opcode

The opcode mod computes the rest of the division of the second top element of the stack by the top element of the stack.

10. comments
Every good language comes with the capability of commenting. When the first non-space character of a line is #, treat this line as a comment (don’t do anything).

11. pchar
The pchar opcode

The opcode pchar prints the char at the top of the stack

12. pstr
The opcode pstr prints the string starting at the top of the stack, followed by a new line.


13. rotl
The rotl opcode

The opcode rotl rotates the stack to the top.

14. rotr
The rotr opcode

The opcode rotr rotates the stack to the bottom.

15. stack, queue
The stack opcode

The opcode stack sets the format of the data to a stack (LIFO). This is the default behavior of the program

16. Brainf*ck
Write a Brainf*ck script that prints School, followed by a new line.

All your Brainf*ck files should be stored inside the bf sub directory
You can install the bf interpreter to test your code: sudo apt-get install bf
Read: Brainf*ck

17. Add two digits
Add two digits given by the user.

Read the two digits from stdin, add them, and print the result
The total of the two digits with be one digit-long (<10)

18. Multiplication
Multiply two digits given by the user.

Read the two digits from stdin, multiply them, and print the result
The result of the multiplication will be one digit-long (<10)

19. Multiplication level up
Multiply two digits given by the user.

