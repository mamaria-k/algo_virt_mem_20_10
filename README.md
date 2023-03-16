###Virtual memory
This is program for the implementation of algorithms for managing virtual memory and comparing them with each other. 


The program accepts one or several files. 

**Description of correct format of input data:**

* the file must contain the top three lines and only them
* the top line shows the number of pages in the process's address space (1 natural number)
* the second line should indicate the number of memory frames (1 natural number)
* the third line should contain a sequence of natural numbers (page references). They must be separated by spaces. 

The results of the program are displayed on the screen. 

**Description of output:**

1. The file was not in the correct format:

    * the program will fail
    * a message with error description will be displayed on the screen
    * the error description is written to the log
    
2. The file is in the correct format:

    * the result of each algorithm is displayed
        >This is the result of the algorithm ... : [...]
        * if a free frame is replaced, then the answer is the frame number with * 
        * if an already filled frame is replaced, then the answer is the frame number
        * if the page is already in memory, then the answer is +  
        
        P.s. this output is arranged for the convenience of the user.     
                                             
    * the result of the comparison is displayed
        >Algorithms sorted by the number of answers of the second type: ...
        
3. Among the calls there are inadmissible:

    * a warning is displayed before the output of the program
        >There were invalid calls in the call sequence.
         These calls will be ignored.
    * invalid calls are ignored


### Example

```
$./gradlew run --args="file.txt"

File file.txt processing result:
There were invalid calls in the call sequence. These calls will be ignored.

This is the result of the algorithm FIFO: [1*, 2*, 3*, 1, +, 2, +, 3, 1]
This is the result of the algorithm LRU: [1*, 2*, 3*, 1, +, 2, +, 1, 2]
This is the result of the algorithm OPT: [1*, 2*, 3*, 2, +, 2, +, +, 1]

Algorithms sorted by the number of answers of the second type:
OPT: 6
FIFO: 7
LRU: 7

```

#####file.txt
````
10
3
22 4 8 7 1 1 2 7 4 10
````
