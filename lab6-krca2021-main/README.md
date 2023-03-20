# Lab: Timing Sorting Algorithms

## Objectives

In this lab, we'll be playing with some of the sorting algorithms we've been discussing in class. In addition, you'll get some familiarity with the `merge` method of `MergeSort`, which you will be implementing an on-disk version of for the next assignment.

This is an individual lab. I encourage you to discuss with your classmates, but you should implement your own code. 

Note: this lab assumes you've kept up with the reading for the class! In particular, we'll be looking at selectionsort, insertionsort, quicksort, and mergesort but we'll also encounter bubblesort and heapsort.

## Getting Started

After you've setup your project, spend 5 minutes looking at the different classes to orient yourself.

* Look at the interface `Sorter`.
* Look at how the `Quicksort` and `Mergesort` classes implement the interface.
* Look at how the `main` method of the `SortTimer` class is able to print out data for an arbitrary number of `Sorter` classes. (This is the benefit of using an interface!)
* Notice that the `SortTimer` class does a check for correctness after sorting. If you make a mistake in implementing your `merge` method, you will get an error here.

## Finish `MergeSort`

You've been given all of the code for this lab except the `merge` method, which you should now implement based on the TODO suggestions. Please note that this is a slight variation of the merge method we have seen in class. Give it a good effort, but if you get stuck, ask a mentor or Professor for help.

Once this is done, you should be able to run the `SortTimer` class.

## Play with the Timing

Notice that we have sent the `printTimes` method twice to the `SortTimer` object. Run the `SortTimer` class. What explains the very different answers obtained in the two runs for small values of size? Does the data obtained from the second run look like you would expect? Which one is faster?

Inside the `printTimes` method, we generate random data for the initial Arraylist to sort. Look at the TODOs here and see if you can figure out how to set up the experiment to accurately compare the sorting algorithms with random data.

The data generated should give you some confidence that `Quicksort`'s average case works as we expect. As an additional test, change the `printTimes` method to generate sorted data instead of random data. For example, have it fill the array with numbers from 1 to `size`. How does this change your timing data? Is this what you expected?

## Play with the Sorting Algorithms

In the IDE, navigate to the `coinSort` package and click on the file `CoinSorter.java`. Now click on the green run button in the top toolbar.

You will see a window similar to the one for the Silver Dollar Game, except that all the squares are filled, and the coins have different sizes. Use the keystrokes below to shuffle and sort the coins. Experiment with several of the sorting algorithms.

# 

* `c`: sort the coins using a randomly-selected algorithm
* `b`: sort the coins using bubble sort
* `i`: sort the coins using insertion sort
* `q`: sort the coins using quicksort
* `h`: sort the coins using heapsort
* `s`: sort the coins using selection sort
* `r`: rearrange the coins into a random order
* `x`: exit the program

The program you are using has a few additional features. Typing `f` (for "freeze") stops the sorting; typing `t` (for "thaw") resumes the sorting. Typing `f` when the sorting is frozen advances the algorithm by one step. You can continue to type `f` to proceed step-by-step, or `t` to resume normal execution.

Typing `c` selects one of the sorting algorithms at random and executes it. Practice with the `c` command to develop your skill in identifying the algorithm from the pattern of comparisons and swaps.

The yellow coins are the coins being compared, and green coins show exchanges between 2 locations.

The insertion sort is using a different implementation than the one presented in class. It compares the element to be inserted with elements in the sorted subarray from left to right instead of right to left.

The selection sort is also a different implementation than the one presented in class. This one starts from the right side and finds the biggest element and exchanges with the rightmost element of the unsorted subarray. For the quicksort, the pivot is chosen as the rightmost element with the highest index.


## Analysis

Discuss with your classmates:

   1. the motivation for ten-runs-per <sort,size> pair, and (quantitatively) what the range of
      values you got tells you about the reliability of *these* results.
   2. for each algorithm, the time as a function of the number of items to sort.
   3. why each algorithm has that performance.

## More Practice with Sorting

   1. Modify insertion sort to compare from left to right
   2. Modify selection sort to start from left side to find the smallest element and exchange with leftmost element of unsorted subarray
   3. Modify quicksort such that the pivot chosen is the leftmost element with the lowest index
   4. Read the code for heapsort and see if you can get a sense of what the algorithm is doing. Is the restoreHeap method is the same as swim or sink? 

