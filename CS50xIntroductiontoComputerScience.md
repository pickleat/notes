# CS50's Introduction to Computer Science

## Week 0

### Lecture Notes
* CS is more about problem solving than “coding.”
* Inputs or Problems → [ CODE ] → Outputs or Solutions
**Binary**
* The language of computers is only 0s and 1s
* We use the deca system with 10 numbers (0-9)
* 123 = 1 is in the hundredths place, 2 is in the tenths place, and 3 is in the ones place. 
* In Binary 123 would be written with 0s and 1s and everything is a power of 2
* ASCII: maps A = 65, B = 66 … 
* Byte = 8 bits
* Abstraction: very simple ideas that build to solve complex problems. 
* Algorithm: step by step instructions to solve a problem. 
* Computational thinking: humans can read between the lines, but computers only read the lines. 
### Walkthrough Notes
* None this week


## Week 1
### Lecture 1 - Moving on from Scratch
* “Hello word” 
``` c 
#include <stdio.h> = include standard input/output library
Int main(void)  “when green flag clicked”
{
for (int i = 0; i < 50; i++) give me an integer “i” and initialize it at 0, i++ count up
{
     printf(“hello, world”);  print out hello
}
```

* Easiest way to compile a program ```make _program name_```
* Data types:
    * Ints = integers, real numbers (no decimal points)
    * String = string of characters (letters)
    * Floats = floating point integers; put .#of decimals after the %i to get a specific number of decimals .10 would give you 10 digits. 
    * Char = single character use single ‘ ‘ quotes
* Operators
* ```=``` means assignment or “is” as in i = 0 means i IS 0. 
* ```==``` means equals
* ```||``` means “or”
* Can also use a switch function which allows you to give multiple input types like: upper and lower-case letter inputs, however it must have the ```break;``` otherwise the code will continue to run. 
* ``&&`` means “and”
* Design Principles:
    * Fewer lines of codes most often means less chances for mistakes, and better “design” 
    * Correctness: code works. 
    * Design: code is formatted simply (no extraneous code)
    * Style: code is formatted well
* Creating a function
    * ```return``` is what you want to give back when the function completes. 
``` c

int square(int n)
{
	return n * n;
}

```

* Preview
    * If you teach the computer a function later in the program, you can hint at it earlier, by naming the function ahead,
    ```int square(int n);```


### Lecture 2 - Building on C
* Review 
    * ```clang``` is just a compiler “c-language”
    * ```./filename``` runs the file
    * ```string name = get_string(“Name: “);```
    * ```printf(“hello, %s”, name);```
    * Don’t forget to use ```#include``` the stdio.h and cs50.h Linking libraries. When compiling use ```-lcs50```
    * ```make``` comes with linked libraries included 
* Compiling: Getting from source code to machine code
    * Preprocessing: #include <stdio.h> tells the computer to find something else
    * Compiler: Makes assembly code, closer to what computers understand
    * Assembling
        * Takes assembly code to machine code
        * Also needs to take the preprocessing code to become machine code
    * Joins together and allows the machine code to work
* Comments are useful because they explain what the program does. Or explain code you’ve already written so you don’t have to re-read and comprehend code you’ve already written. 
* For errors and style changes: start at the top and do one or few at a time, because sometimes the errors are dependent on each other. 
* In C, variables are only valid in their scope, inside the {}
* Placing a for loop inside a for loop can make several different layers 
* ```eprintf``` allows you to see what should happen above the code. 
* Debugger - debug50 ./filename
    * Add breakpoints to allow you to go step by step through the program and see what variable values actually are and what that is making your program do. 
* Other functions
    * ```get_char```
    * ```get_double```
    * ```get_float```
    * ```get_int```
    * ```get_long```
    * ```get_long_long```
    * ```get_string```
    * ```[]``` can iterate over each character. 
    * ```strlen```: can deal with the string length
    * ```\0``` is always at the end of the string. Null terminator.  
    * Manual  ```man get_function``` will allow you to read about it. 
    * Also reference.cs50.net has a user-friendly explanation. 


* You have to choose a data types 
* Array: continuous set of memory back to back to back 
    * ```int main(void)``` specifically means that main takes no arguments on its own, you must provide them with “get_int” or the like
    * ```int main(int argc, string argv[])``` means
        * ```int``` : total number of words
        * ```argc```: argument count
        * ```argv```: array of words that the user has typed
            * The brackets mean an array. 
        * Allows us to add input just past the ./program name 
* Cryptography
    * Cryptography is basically just the same input/output there is just an added key. 
    * Plain text → Cipher Text, you just need a key to decode the cipher text.

### Shorts
#### Debugging
* ```help50```: virtual teaching fellow, helps nudge you in the right direction. Helps when you aren’t sure why your program can’t be compiled or some other issue
* ```eprintf```: just using printf doesn’t actually give you the line of code you need. ```eprintf``` gives you a line marker and statement about what is happening. Tells you where in your program whatever you’ve prompted is happening.
* ```check50```
* ```debug50```: GUI platform. Allows you to walk through the program line by line seeing variable changes, and other program issues
    * Set a break point so that the debugger will stop.
    * Stepping over will execute the line
    * Step into will allow you to see a specific line of code execute
    * Step over, gets out of a line of code you’ve stepped into
* Functions
    * So far all the programs we’ve been writing have been inside of main()
    * However as the programs we write grow in size they will start to become unwieldy.
    * C and nearly all languages developed since allow us to write functions, sometimes known also as procedures, methods, or subroutines. 
    * A function is a seires of inputs 0+ and one output
    ```mult(a * b)```
    * It’s called a “black box” because we don’t care necessarily what happens inside the box, as long as the output is obvious
    * Why functions?
        * *Organization:* Functions help break up a complicated problem into more manageable subparts
        * *Simplification* Smaller components tend to be easier to design, implement, and debug
        * *Reusability* Functions can be recycled; you only need to write them once, but can use them as often as you need!
    * Function declarations
        * The first step is to create a function is to declare it. This gives the compiler a heads up. 
        * Function declarations should always go atop your code, before you begin writing main. 
        * Function definition can be below code
        * There is a standard form that every function declaration follows
            * Function declarations: what you want to call your function
            * return-type name(argument-list); The argument-list is the comma-separated set of inputs to your function, each of which has a type and a name.
            * return-type is what kind of variable the function will output
        * Function definition: Looks almost identical to a function declaration, with a small change.
            * return-type name(argument-list);
            * return-type name(argument-list)
                ``` c
                {
                    return output of the black box;
                }
                ```
        * Function calls: Time to use it!
            * Pass the function appropriate arguments, assign its return value to something of the correct type.
        * Function miscellany
            *  Sometimes functions take no inputs, in that case, declare the function as having a void argument list.
            * Functions also sometimes do not have an output, in that case declare the function as having a void return type.
* Variables and Scope
    * Scope is a characteristic of a variable that defines from which functions that variable may be accessed
    * Local variables: can only be accessed within the functions in which they are created
    * Global variables: can be accessed by any function in the program
    * Be careful however because it can still be changed if the value is stored by something
    * Why does this matter?
        * Local variables receive copies of the variable, not the specific value. So if the the value is overwritten then the new variable value is passed down. 
        * This can also get tricky when working with other people, because the same variables can be used. If this occurs, make the distinction of which are local and which are global, and if there is a variable reused, think of its localization and make a note of it, or if you have the power… change it. 
* Arrays
    * Arrays are a fundamental data structure, and they are extremely useful
    * We use arrays to hold values of the same type at contiguous memory locations
    * Array is a large block of contiguous memory, which has been partitioned into small, identically-sized blocks called elements, each of which can store a certain amount of data, all of the same data type such as int or char, and which can be accessed by an index.
    * In C, the elements of an array are indexed starting from zero. 
        * Therefore, the first is located at 0 and the last will be at index n-1.
    * Array declaration: very similar to a function declaration
        ```type name[size];```
        * Type: the kind of variable
        * Name: what you want to call yoru array
        * Size: how many elements you would like your array to contain
    * If you think of a single element of an array of type data-type the same as you would any other variable of the type data-type (which, effectively, it is) then all the familiar operations make sense. 
    * You can declare and initialize an array simultaneously by putting the starting values in the size portion here are two ways to make the same array
        * *Instantiation syntax*
            ```Bool truthtable[3] = { false, true, true };```
        * *Individual element syntax*
            ``` c
            Bool truthtable[3];
            Truthtable[0] = false;
            Truthtable[1] = true;
            Truthtable[2] = true;
            ```
    * Arrays can consist of more than a single dimension. You can have as many size specifiers as you wish like: ```bool battleship[10][10];``` 
    * You can use this to think of it as a 10x10 game board, but in reality its just a 100-element one dimensional array
    * Multi-dimensional arrays are great abstractions to help visualize game boards or other complex representations
    * We can treat each individual array as variables, but we cannot treat entire arrays themselves in C. You can however do this in other languages. 
    * We can’t assign an array to another array, instead you have to use a for loop and reiterate a loop and assign it. 
    * Recall that most variables in C are passed by value in function calls
    * Arrays do not follow this rule. Rather they are passed by reference. The callee receives the actual array, NOT a copy of it. 

* Command line arguments
    * So far all our programs have begun the same way:
        ```int main(void)```...
    * Since we’ve done this you have to prompt the user for use. 
    * To collect command-line arguments from the user, declare main as:
        ``` c
        int main(int argc, string argv[])
        {``` ...
    * These allow you to get an argument and an array
        * ```argc``` (argument count): this integer type variable will store the number  of command-line arguments the user typed when the program was executed
        * ```./greedy``` | argc 1
        * ```./greedy 1050 cs50``` | argc 3
    * ```argv``` (argument vector):
        * The array of strings stores, one string per element, the actual text the user type at the command line when the program was executed.
        * The first element of argv is always found at 0
        * The last element of argv is always n-1. 
        * Everything in argv is stored as a string, so using the same example as above:
            ``` c

            argv[0] = ./greedy
            argv[1] = “1050” ← this is a STRING “1050” NOT the integer
            argv[2] = cs50
            argv[3] = \0 null value most likely, or a segmentation fault.

            ```
* Magic Numbers
    * Sometimes we’ve written weird numbers, some of them are matters of practicality. But for the most part, it’s not good to put constants into your code.
    * Even if they make sense, like say deck_size = 52; for a deck of cards, it isn’t good code, for say if you deal some of the cards out and then shuffle, or if there is another place that will change the deck size. 
    * C provides a preprocessor directive (also called a macro) for creating symbolic constants. 
		```#define NAME REPLACEMENT```
    * At the time your program is compiled, #define goes through your code and replaces NAME with REPLACEMENT. 
    * If #include is similar to copy/paste, then #define is analogous to find/replace.
    * Its not limited to numbers, but you can do it with strings and others. 
    * Lots of times they are in all-caps as convention to separate constant and variables.
    * This allows you to keep your constants nice and safe, and not accidentally assigned new values in the middle of the code. 
    * This also allows for you to change a constant once, instead of finding it a million times in the code. 


Week 2
Lecture 2 - 
Storing stuff in RAM 
“/0” NUL terminator is the ONLY way that C knows a string has ended.
Gigabyte means a billion bytes
Sequence is also known as an array
Dont trust a value unless you set it
Linear Search: 
For each element in array, 
if it is the element you are looking for 
	return true, 
Else
	Return false
Binary Search: 
Look in the middle of the sorted array, 
 if it is the element you are looking for,
	Return true
Else if element is to the left
	Search in the left half of array
Else if element is to the right
	Search in the right half of the array
Else
	Return false
Binary search should be faster in most cases
Requires a sorted array. 
How to sort an array?
Use an algorithm 
Insertion check if the current number goes before or after (like alphabetizing something)
Selection sort: find the smallest number and put it in the lowest place and move on. 
Bubble sort: 
Repeat until no swaps
	For i from 0 to n-2 // n-2 is so you don’t touch the garbage values outside your list //
		If i’th and i+1th elements out of order, 
			swap them
Merge sort: O(n log n) OR T(n) = T(n/2) + T(n/2) + O(n)
It does use twice the amount of memory of n
Algorithms have running time 
O “Big O” is a term about an “upper bound” on running time
Ω “Omega” is the “lower bound” of running time
Recursion is the act of a function calling itself which is BAD unless, you have a base case, that allows you to use recursion to take a bite out of the problem, and the base case allows 
Shorts 2
Computational Complexity
When we talk about complexity, we talk about worst-case scenario. That is referred to “Big O” or O.
Sometimes we care about best-case scenario that is called “big Omega” or Ω
Data Sets
Whatever makes the most sense in the context of what you are working on. Kbs, arrays. 
We can measure an algorithm based on how it handles these inputs. Let's call this measure f(n). 
We don’t care about what f(n) is precisely. We only care about it’s tendency. 
The tendency or “big O” is basically if you have 3 different algorithms, and they all basically take the same amount of runtime. 
Time Algorithms
O(1) = Constant Time
O(n) = Linear Alg
Sorting Algorithms
Selection Sort: find the smallest unsorted element and move it to the end of the array. This happens by searching through the array for the smallest element, and swapping it with the first unsorted part of the array. 
Basically sorts the array smallest to largest (left-to-right)
Worst and best-case:(n2)
Bubble Sort: move the higher valued elements generally toward the right and lower value elements generally toward the left. 
Basically sorts the array largest to smallest (right-to-left)
Worst case: the array is in reverse order, and you have to bubble the largest values, all the way to the right. O(n2)
Best case: its already sorted Ω(n)
Insertion Sort: consider the first element “sorted” and then take each following element, pulling it out and inserting it appropriately in the sorted list.
Worst case: array is in reverse order O(n2)
Best: already sorted Ω(n)
Linear Search: iterate across the array from left to right, searching for a specified element. 
Worst case: item is at the end or not in the array O(n)
Best case: item is first Ω(1)
Binary Search: idea is “divide and conquer” it reduces the search area by half each time. However it requires the array be sorted for it to work. This is how you look for someone by looking in the center and tearing the half that’s been eliminated from it, until all you have remaining the the name you are looking for. 
If you are looking for an element that doesn’t exist in an array, you’re start end point switch, then element doesn’t exist. 
Worst case O(log n)
Best Ω(1)
Algorithms Summary:
Algorithm Name
Basic Concept
O
Ω
Selection Sort
Find the smallest unsorted element in an array and swap with the first unsorted element of that array.
n2
n2
Bubble Sort
Swap adjacent pairs of elements if they are out of order, effectively “bubbling” larger elements to the right and smaller elements to the left.
n2
n
Insertion Sort
Proceed once through an array from left-to-right, shifting elements as necessary to insert each element into its correct place. 
n2
n
Merge Sort
Split the full array into subarrays, then merge those subarrays back together in the correct order
n log n
n log n
Linear Search
Iterate across the array from left-to-right, trying to find the target element
n
1
Binary Search
Given a sorted array, divide and conquer by systematically eliminating half of the remaining elements in the search for the target element
log n
1
Recursion
A recursive function is one that by nature invokes itself. 
Example factorials (n!):. n * (n - 1) … (n - (n + 1). e.g. (4!) = 4 * 3 * 2 * 1.
If we write a function called fact(n) it would look like this
fact(1) = 1
fact(2) = 2 * 1
fact(3) = 3 * 2 * 1
fact(4) = 4 * 3 * 2 * 1
OR we could right it like this: 
fact(1) = fact(1)
fact(2) = 2 * fact(1)
fact(3) = 3 * fact(2)
fact(4) = 4 * fact(3)
fact(n) = n * fact(n-1)
This forms the basis for a recursive definition of the factorial function.
Every recursive function has two cases that could apply given any input. 
The base case, which when triggered will terminate the recursive process (otherwise the function would continue on for eternity)
The recursive case, which is where the recursion will occur. The difference is that it will pass a function that makes the problem slightly smaller, and passes the buck of solving the problem down the line. 
int fact(int n)
{
     if (n == 1)		// base case
	return 1;
     else 		// recursive case
	return n * fact(n-1);
}
You can have multiple base cases like in the Fibonacci sequence. It is understood that 0 and 1 are the first two numbers. From then on the recursion works. 
Collatz conjecture:
collatz(n)
{
	// base case
	if (n == 1)
		return 0;
	// even numbers
	else if ((n % 2) == 0)
		return 1 + collatz(n/2);
	// odd numbers
	else
		return collatz(3*n + 1);
}
GDB
GDB (the GNU Debugger): 
To start type: gdb <program name>
From there you’ll use two major commands: 
b [function name, line number] 
This makes it so that once your program begins, it will run uninterrupted until it encounters the function with that name or hits that line number, at which point the program will pause execution and await further input. 
r [command-line arguments]
Runs the program with the command line arguments provided. If you don’t put any command-line args it will just run the program. 
Other important commands: 
n // will step forward one block of code
s // will step forward one line of code
p [variable]  // Prints out the value of the variable given
info locals // Prints out the values of all local variables
bt // Shows you what series of function calls have led to the current point in the program
q // Quits GDB


Week 3
Lecture 4 - Class Notes
Strings don’t actually exist in C. They are just multiple characters. 
Strings are actually char * which is just an array or sequence of characters. 
char means character
* means pointer 
Each character takes up a byte. 
The string s = get_string(“s: “) and you turn in “Stelios” the computer sends the address of the first letter and the computer knows the string will go until the \0 character. 
The address is pointing to the first byte of memory where the string of characters starts. 
Strcmp is actually taking two separate addresses and comparing each char in the string. If they are the same it returns an int of 0. 
malloc means memory allocation
It is a function that takes a number of bytes and finds those bytes to allocated and returns the address of the beginning of that chunk of memory. 
If you don’t initialize memory, assume it has garbage values. Because you didn’t give it. 
If you want to copy a string, you must iterate because a simple 
string s = t;  // will only copy the pointer value. Instead you need to use a For loop and iterate over each character. 
Characters has addresses and Strings have characters. 
Pointer Arithmetic
*(s + i)
* 
If you see the * and it is clearly not being used for multiplication…
AND if there is a data type to the left of the star, it is a variable declaration. Like char *s = … it is declaring a string called s. 
If there is NO data type, like in : printf(“%c\n”, *(s = i)); it isn’t saying GET a pointer, but instead GO to the pointer called “s” (in this case). 
scanf(“%i” &x) 
&x get the address of the variable. 
You can pass in an array or a name of an array. 
Stack and Heap
Heap a specific place of memory
Stack a allows for sections of memory to be allocated. 
So on an int main(void) // main receives 
And 
Functions do not have access to each other’s memories. They can only change another functions memories, if you give it a map or pointer to find the value. 
Get me the address of something with &
Go to the address of something with *
Three Pointer Rules
Pointer and Pointee are separate – don’t forget to set up the pointee
Dereference a pointer to access its pointee
Assignment (=) between pointers makes them point to the same pointee. Sometimes they call this “sharing”
Hexadecimal (15): 0,1,2,3,4,5,6,7,8,9,a,b,c,d,e,f. 
File structure: at the end of the day every file is just 0s and 1s, but they all have a structure that allows us to know what makes a file type different than another. 
typedef struct // typedef and struct when used together allow you to declare your own data structures. 
{
	String name;
	String dorm:
}
Student;
Metadata: 24-bit BMP file example
Contains other information like the height and width of the image. It is stored at the beginning of the file in the form of two data structures generally referred to as “headers” not like C-lang headers (#include)
Shorts
Call Stacks: more in-depth info about how recursion works. 
When you call a function, the system sets aside space in memory for that function to do its necessary work. 
We frequently call such chunks of memory stack frames or function frames
More than one function’s stack frame may exist in memory at a given time. If main() calls move(), which then calls direction(), all three functions have open frames, but they aren’t all active frames. 
These frames are arranged in a stack. The frame for the most recently called function is always on top of the stack. 
When the function is called, a new frame is pushed onto the top of the stack and becomes the active fram. 
When a function finishes its work, its frame is popped off of the stack, and the frame immediately below it becomes the new, active, function on the top of the stack. This function picks up immediately where it left off. 
File Pointers: 
 The ability to read data from and write data to files is the primary means of storing persistent data, data that does not disappear when your program stops running. 
The abstraction of files that C provides is implemented in a data structure known as a FILE. 
Almost universally when working with files, we will be using pointers to them, FILE*. 
EOF means “End of File” can be used as a condition in a loop like != EOF 
The file manipulation functions all live in stdio.h
Some of most common file I/O functions that we’ll be working with are:
fopen(): 
Opens a file and returns a file pointer to it. 
Always check the return value to make sure you don’t get NULL. 
FILE* ptr = fopen(<filename>, operation)
Operations are normally “r” or “w” meaning read and write respectively. “a” means appending, which you’ll use if you want to append a file, and not re-write the whole file. 
fclose()
Closes the file pointed to by the given file pointer
fclose(ptr);
fgetc()
Means: “file get character”
Reads and returns the next character from the file pointed to. 
Note: that the operation of the file pointer passed in as the parameter must be “r” for read, or you will suffer an error. 
char ch = fgetc(ptr);


fputc()
Writes or appends the specified character to the pointed-to-file. 
Note: the operations of the file pointer passed in as a parameter must be “w” or “a” or you will suffer an error. 
fputc(‘A’, ptr); 
fread()
It looks intimidating, but it is the generic version of fgetc() that lets us get a specific amount. 
Reads a <qty> units of size <size> from the file pointed to and stores them in memory in a buffer (usually an array) pointed to by <buffer>.
Note: the operation of the file pointer passed in as a parameter must be “r” for read or you will suffer an error. 
fread(<buffer>, <size>, <qty>, <file pointer>);
fread() takes from the FILE and puts it in the BUFFER. 
fwrite()
Works just like fread() but instead it writes. 
fwrite() writes from the buffer to the file. 
Other functions
fgets() and fputs() // r/w a string from a file. 
fprintf() // writes a formatted string to a file.
fseek() // allows you to fast-forward or rewind within a file. 
ftell() // Tells you at what (byte) position you are within a file.
feof() // tells you whether you‘ve read to the end of the file (EOF)
ferror() // indicates whether an error has occurred in working with a file. 
Pointers 
Pointers provide an alternative way to pass data between functions. 
Up to this point we have passed all data by value, with one exception. 
When we pass data by value, all we do is pass a copy of the data. 
If we use pointers instead, we have the power to pass the actual variable itself. 
That means that a change that is made in one function can impact what happens in a different function. 
Reminder about storage: 
Every file on your computer lives on a HDD or SSD. 
Disk drives are just storage space; we can’t directly work there. Manipulation and use of data can only take place in RAM, so we have to move data there. 
Memory is basically a huge array of 8-bit (bytes) sized cells. 
We can access any part in it by simply saying which place we want in [n] notation. 
When we say store an integer “8” the computer sets aside 4 bytes in RAM to store “8”k
Data Types size
Int = 4 bytes
Char = 1 byte
Float = 4 bytes
Double = 8 bytes
Long long = 8 bytes
String = ??? 
Alias for char* created specifically for CS50 (#include cs50.h). Which ends up being 4 or 8 bytes. 
POINTERS ARE NOTHING MORE THAN ADDRESSES. They simply tell you WHERE the data lives. 
A pointer is a data item whose 
Value is a memory address.
Type describes the data located at the memory address. 
How pointers work:
The simplest pointer available in C is the NULL pointer. As you can expect, this pointer points to nothing, but it can actually come in handy. 
When you create a pointer and you don’t set its value immediately you should always set the value of the pointer to NULL. 
You can check whether a pointer is NULL using the equality operator (==). 
Another easy way to create a pointer is to extract the address of an already existing variable. exWe can do this with the address extraction operator (&). 
An arrays name, is actually just a pointer to its first element. 
The main purpose of a pointer is to allow us to modify or inspect the location to which it points
We do this by dereferencing the pointer. 
If we have a pointer-to-char called pc, then *pc is the data that lives at the memory address stored inside the variable pc. 
Used in this context, * is known as the dereference operator.
It “goes to the reference” and accesses the data at that memory location, allowing you to change it. 
If you dereference a pointer whose value is NULL, you get a segmentation fault. 
Surprisingly this is actually good behavior because it defends against actually damaging another program by accidentally dereferencing it. So it’s better for your program to crash, than to destroy or manipulate another unintended program. 
Example
int* p;
The value of p is an address
I can dereference p with the * operator
If we do, we’ll find an int at that location. 
It’s best to declare pointers on different lines. 
You can use the dereferencing operator (*) to change the value it points to.
*pk = 35; // goes to the place referenced and changes the value there. So if *pk points to k, k now equals 35. Which in essence is the same as saying k = 35; 
you can use the extraction operator (&) to change the address that pointer points to. 
Using the previous example. If we write
int m;
m = 4;
pk = &m;
Now pk which was pointing to “k” now points to “m”. 
Dynamic Memory Allocation 
We can use pointers to get access to a block of dynamically-allocated memory at runtime. 
Dynamically Allocated Memory comes from a pool of memory known as the heap. 
Prior to this point, all the memory we’ve been working with has been coming from a pool of memory known as the stack. 
As a general rule (there are a few rare exceptions). If you give a variable a name it lives in the stack, if you do not (with DAM) it lives on the heap. 
The heap and stack are not actually different pools of memory, but in the diagram from the lecture. The heap starts at the top and works its way down. And the stack starts at the bottom and works up. 
How do we get access to DAM?
We get this DAM by making a call to the C stdlib.h function called malloc() passing as its parameter the number of bytes requested. 
After obtaining memory (if it can), malloc() will return a pointer to that memory. 
If malloc() can’t give memory it will return NULL. 
Ex: Static vs Dynamic
int x; // statically obtain an integer
int *px = malloc(sizeof(int)); // dynamically obtain an integer
Memory Leaks
Here’s the problem: DAM is not automatically returned to the system for later use when the function in which it’s created finished execution. 
Failing to return memory back to the system when you’re finished with it results in a memory leak which can compromise your system’s performance. 
When you finish working with DAM, you must free() it. 
Three golden rules: 
Every block of memory that you malloc() must subsequently be free()d
Only memory that you malloc() should be free()d. 
Do not free() a block of memory more than once. 
Hexadecimal 
Most western cultures use base-10 (0-9)
Computers binary (0 and 1)
As a computer scientiist its useful to be able to express data as the computer does, but that can get quite overwhelming with tons of zeros and ones. 
The Hexadecimal system is a base-16 system, which is a much more concise way to express data on the computer’s system. 
0 1 2 3 4 5 6 7 8 9 A B C D E F 
Hexadecimal makes this mapping easy because a group of four binary digits is able to have 16 different combinations, and each of those combinations maps to a single hexadecimal digit. 
Typically they are prefixed with 0x
Each column in a column place corresponds to the 16x
256 / 162
16 / 161
160

Open File
Update the Outfiles Header Info
New BMP → new header info
What’s changing in the header?
File size
Image size
Width
Height
BITMAPINFOHEADER
biWidth // width of the image (in pixels), does NOT include padding [HINT is bi.biWidth *= n;]
biHeight // height of the image (in pixels) [HINT is bi.biHeight *= n;]
biSizeImage // total size of the image (in bytes). Includes pixels AND padding. 
bi.biSizeImage = ((sizeof(RGBTRIPLE) * bi.biWidth) + padding) * abs(bi.biHeight); 
BITMAPFILEHEADER
bfSize // total size of the file (in bytes). Includes pixels, padding, and headers. 
bf.bfSize = bi.biSizeImage + sizeof(BITMAPFILEHEADER) + sizeof(BITMAPINFOHEADER); 



Read the Infiles Scanline Pixel by Pixel
fread(data, size, number, inptr)
Data: pointer to a struct that will contain the bytes you’re reading. 
Size: size of each element to read (sizeof)
Number: number of elements to read
inptr : FILE * to read from. 
Resize Horizontally (remember padding)
For each pixel in the row, write it n times. 
fwrite(data, size, number, outptr);
Data: pointer to the struct that contains the bytes you’re reading from
Size: elements to write
Number: elements to write
Outptr: FILE * to write to. 
Padding: each pixel is 3 bytes, but the length of the scanline must be a multiple of 4. So if the number of pixels isn’t a multiple of 4, we need to add “padding” to make it a multiple of 4. Padding is just “0x00”. 
Padding equation = (4 - (bi.biWidth * sizeof(RGBTRIPLE)) % 4) % 4
The outfile and infile have different widths so the padding is different
Padding isn’t an RGBTRIPLE, we can’t fread padding. So we need to use fputc function
fputc(chr, outptr)
chr: the char to write
outptr: FILE * to write to
fputc(0x00, outptr); 
Pseudocode: 
For each row
	For each pixel in row 
		Write to the outfile n times
	Write the outfile’s padding
	Skip over infile’s padding
Try to implement horizontally stretching the image only first. THEN moving to vertically. 
Resize Vertically (7:38) in walkthrough. 
