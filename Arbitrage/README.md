
 ## In this tiny project, I implemented Bellman-Ford to detect arbitrage opportunities given a set of exchange rates between currencies. 



# Vertex Class
- rank: the rank (label) of the given vertex
- neigh: the list of the neighboring vertices
- dist: the distance from the start vertex
- prev： the previous vertex in the path

There are 3 fully implemented member functions:

- init: this is the constructor function for the Vertex class. It requires an input rank for the vertex, and sets all of the attributes to have reasonable starting values. You will create a new Vertex with a call: v = Vertex(rank).
- repr: this function is called whenever a Vertex is printed, i.e. when the call print(v) is made. It simply prints the rank of the vertex.
- isEqual: this takes in a second Vertex as an input, and compares the rank of the two vertices, returning True if they are equal rank (i.e., if they had the same label). This function can be called using: v.isEqual(u).




# Currencies Class

- rates: a 2D array representing the exchange rates
- currs: a list of the currency names as strings
- adjList: the adjacency list of Vertex objects
- adjMat: the adjacency matrix (stored as a 2D list)
- negCyc: what will ultimately contain the negative cost cycle, stored as a list of ranks (not a list of vertices)

There are 6 fully implemented member functions:

- init: this is the constructor for the Currencies class. It has one optional input: the exchangeNum which selects which set of exchange rates to use (options: 0,1,2,3 - default: 0). This initialization function correctly creates the adjacency list. The negCyc attribute is initialized as an empty list. A new Currencies object can be created with the call c = Currencies(exchangeNum).
NOTE: the adjacency matrix is created using the rates2mat function. You will have to correctly implement this function (described later).

- repr: this function is called when a Currencies object is printed. It will simply print all of the exchange rates.
- printList: this function can be used to aid with debugging. It prints the adjacency list in a more readable format.
- printMat: this function can be used to aid with debugging. It prints the adjacency matrix in a more readable format.
- printArb: this function is used to print the currencies listed in the negative cycle stored in negCyc.

- arbitrage: this function calls the function detectArbitrage on the Currencies to obtain the potential negative cost cycle. You will be responsible for implementing the detectArbitrage function (described later). It will then check to ensure that the reported arbitrage (if one was reported) was successful: that it was a cycle where arbitrage occurred. If the arbitrage was successful, it will report the monetary gain per unit input.







# detectArbitrage Implementation
It will output a single list of vertex ranks corresponding to the negative cost cycle. This list needs to start and end at the same rank. This function will take 2 inputs:
- currencies: the Currencies object for the exchange rates.
- tol: this is a value that is set at 1e-15 as default, and should not be altered. (tolerance value, tol=1e-15)
- detectArbitrage and detectArbitrage_: I implemented two approaches to detect arbitrage: one is pure Bellman-Ford, the other is UnionFind/Find-by-Rank

The function testRates will test all four sets of currencies using Bellman-Ford, and print the resulting arbitrage paths.









