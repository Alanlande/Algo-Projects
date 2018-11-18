# Sorting algorithm toy project

The file sorting_algo.py has a number of pre-defined **sorting functions** listed below:
- InsertionSort(A): this will contain your implementation for Insertion Sort.
- SelectionSort(A): this will contain your implementation for Selection Sort.
- BubbleSort(A): this will contain your implementation for Bubble Sort.
- MergeSort(A): this will contain your implementation for Merge Sort.
- QuickSort(A,i,j): this will contain your implementation for Quick Sort.

## Helper functions

- isSorted(unA, sA): this function returns True if the array sA is the sorted version of
the array unA, and False otherwise.
testingSuite(alg): this function runs a number of tests on the algorithm in question. This is not an exhaustive list of tests by any means, but covers the edge cases for your sorting algorithms. The valid inputs to this testing function are the strings:
– ‘SelectionSort’ – ‘InsertionSort’ – ‘BubbleSort’
– ‘MergeSort’
– ‘QuickSort’

- measureTime(sortedFlag = False, numTrials = 30): this function runs your algo- rithms on a number of randomized inputs of varying sizes while tracking the runtimes. It will plot the runtime versus n for each algorithm and save these as .png files to the current directory. It also creates a log-log plot of the runtime for several of the algorithms, and will print some info about those plots. This function will be discussed in further detail later.


## How to analyze


- Runtime Comparisons
In the provided code is the function measureTime(sortedFlag = False, numTrials = 30). This function can be used to time your implementations and obtain plots of the runtime versus input size. There are several ways this function can be called:
- The call measureTime() will use randomly generated test arrays, and for each input size n considered, will average the runtime over 30 separate trials.
- The call measureTime(False,x) will use randomly generated test arrays, and for each input size n considered, will average the runtime over x separate trials, where x is an integer.
- The call measureTime(True) will use already sorted test arrays, and for each input size n considered, will average the runtime over 30 separate trials.
- The call measureTime(True,x) will use already sorted test arrays, and for each input size n considered, will average the runtime over x separate trials, where x is an integer.




- Log-Log Runtime
The function measureTime will also generate a log-log plot of runtime versus input size for Selection Sort, Insertion Sort, and Bubble Sort. It then attempts to fit a line to these log- log plots and will output the fitted slope. It first attempts this fit using all of the runtime data (including even very small values of n) and will report those slopes. It then attempts the fitting using only larger values of n. One of the questions you must answer is which attempted fit gives more accurate results, and why you think that is the case.
Looking at log-log plots of the runtime versus the input size is a very common method used to interpret the runtime of a polynomial time algorithm. To understand why we do this, consider the following hypothetical:
Let’s assume that we have an algorithm that runs in O(nk) time, where k is some positive integer. Once we have implemented this algorithm, how can we determine if it really has obtained the promised runtime complexity?
The claim that the runtime is O(nk) means that T(n) ∼ nk.
Now take the log of both sides of this equation. This gives us logT =log(nk).
But, by a property of logarithms, we can write this as logT =klogn.
So if we plot log T versus log n, we should see a straight line! Moreover the slope of that line should be the value of k.This means that if you want to verify that an algorithm runs in O(n2) time, you should plot the runtime versus the input size on a log-log scale. If you fit the resulting log-log plot to a straight line, the slope should be 2.