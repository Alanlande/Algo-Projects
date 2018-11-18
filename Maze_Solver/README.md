
 ## In this tiny project, I implemented both DFS and BFS to solve several given mazes. 



# Stack Class
- stack: the array representing the stack
- top: the index of the top element of the stack (will point directly at the top element in the stack)
- numElems: the number of elements currently in the stack 
There are 5 fully implemented member functions:

- init: the constructor which initializes an empty stack
- repr: the printing function the displays the stack’s info in a readable format
- isFull: this function will return true when the stack is full (and so requires resizing)
- isEmpty: this function will return true when the stack is empty
- resize: this function can be called to double the size of the stack in memory when you want to push a new element into a full stack
- push: this function should take in some value and push it onto the top of the stack
- pop: this function should pop the top value off the stack and return it




# Queue Class

- queue: the array representing the queue
- front: the index of the front element of the queue (will point directly at the front element), this is the next element to be popped
- rear: the index that is ONE PAST the rear element of the queue, this is the location where the next pushed value will be written
- numElems: the number of elements currently in the queue 
There are 5 fully implemented member functions:

- init: the constructor which initializes an empty queue
- repr: the printing function the displays the queue’s info in a readable format
- isFull: this function will return true when the queue is full (and so requires resizing)
- isEmpty: this function will return true when the queue is empty
- resize: this function can be called to double the size of the queue in memory when you want to push a new element into a full queue

- push: this function should take in some value and push it into the rear of the queue
- pop: this function should pop the front value from the queue and return it






# DFS/BFS Implementation
The function bdfs should take in an input Maze object and a string that is either ‘DFS’ or ‘BFS’. The implementation of this function should be able to run either DFS or BFS depending on this input string. 
The Maze class provides both an adjacency list of Vertex objects, and an adjacency matrix. The output of this bdfs is a list of vertex ranks (NOT Vertex objects) representing the path starting at the start vertex and ending at the exit vertex.
You should not call this function directly when creating your code, but should instead use the Maze class’s member function solve, i.e., to test the small open room maze with printing enabled:
- m = Maze(0, True)
- m.solve(‘DFS’)
- m.solve(‘BFS’)


The function call testMazes(True) will test all four mazes with both DFS and BFS, and print the resulting paths (you can set the verbosity input to False to suppress the printing).
