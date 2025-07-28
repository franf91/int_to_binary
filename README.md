# int_to_binary

<h1>Problem 5 in chapter 2 [1]</h1>

<img width="669" height="60" alt="Screen Shot 2025-07-27 at 10 12 23 PM" src="https://github.com/user-attachments/assets/b5fb0397-9a2e-49b6-9eda-1d8cb7b86d51" />

<h1>Demo</h1>

- git clone repo
- compile files: gcc binary.c stackADT.c -o binary
- run program: ./binary
- input integer: 25
- result: 11001

<h1>How to solve</h1>

 - (1) calculate the integer modulo 2 
 - (2) push value to stack datastructure
 - (3) divide integer by 2
 - (4) repeat (1) - (3) until integer is no longer greater than 0
 - (5) pop stack until empty to reveal binary version of integer

<h1>Why use a stack </h1>

- Convenient way to retrieve data stored in reverse order

<h1> Why implement stack using linked list</h1>

- The linked list implementation makes it easy to dynamically grow without setting a predefined limit.
- This implementation is inspired by a version found in [2].

<h1>stackADT.c explained</h1>

- terminate() function used to print error statements
- create() instantiates a Stack and sets the head pointer to null
- is_empty() checks if head pointer is null
- is_full() will always return false as linked list implementation does not have a set limit
- make_empty() will pop stack and print result until stack is empty
- destroy() will pop stack until empty and free the Stack
- push() will add new node to the front of the list
- pop() will remove the first node of the list

<h1>binary.c explained</h1>

- the binary function converts integer to binary format
- The while loop is used to push remainder of integer (modulo 2)to stack
- The remainder is either 0 or 1 when modulo 2
- After push the integer is divided by 2 and its value is checked(x>0)
- Once condition is false the make_empty function is used to reveal the binary value
- The main function instantiates the Stack
- The main function asks user for integer
- The binary value is printed
- This can be repeated until program is closed

<h1>References</h1>
[1] R. Sedgewick, Algorithms in C. Reading, MA: Addison-Wesley, 1990.
[2] K. N. King, C Programming: A Modern Approach, 2nd ed. New York: W. W. Norton & Company, 2008.
