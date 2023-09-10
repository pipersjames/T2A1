# T2A1-B - Workbook

### Q1 Identify and explain the workings of TWO sorting algorithms and discuss and compare their performance/efficiency (i.e. Big O)

---
Sorting algorithms organise data by employing different kinds of methods that involve partitioning, merging, exchanging, selecting and/or replacing values in a data set. The selection sort is one of the simplier algorithms that acheive this process by comparing, selecting and swapping a value based on a criteria and it's position in an array. An example python3 code is presented below explaining what occurs at each step as a commmented portion.

##### The selection sort method

```
def selection_sort(array):

    # set each value from index 0 -> n as the minimum 
    for i in range(len(array)):
        min_index = i  

        #compare current set min to the rest of the list i + 1 -> n               
        for j in range(i + 1, len(array)): 
            if array[j] < array[min_index]:  
                min_index = j
        
        #swap the current value of that we are looking at with the new min value
        arrary[i], array[min_index] = array[min_index], array[i] 

    return array
```

To accomplish the search the list has to loop over itself while looping through each item. This produces a time complexity for this model consists of n * (n-1) + 1 or O(n^2). The quadratic time complexity presented by the model is ineffiecient for production cases and large datasets. You may however find this method being used in small to medium datasets and cases where space usage is a desired criteria. This is because it sorts in the same space it lives in the data giving a linear space complexity of O(1). This method is not a stable type of sorting either, meaning that in cases where the same value appears multiple times in a list, the order of these two items relative to another variable may be lost.

An alternative to the selection sort that is more widely seen in practice for larger data sets and production cases is quick sort method. Just like the quick sort method it is also not stable. It does however employ a divide and counquer strategy to split the dataset into smaller subarrays that effectively improves the potential for better time efficiency. Let's look at a python3 example.


##### The quick sort method
```
def quick_sort(array):

    # Choose a pivot element (in this case, the last element)
    pivot = array[-1]

    # group elements smaller than the pivot
    left = [x for x in array if x < pivot]  
    
    # group elements equal to the pivot
    middle = [x for x in array if x == pivot]  
    
    # group elements greater than the pivot
    right = [x for x in array if x > pivot]  

     # Recursively sort the left and right sublists
    return quick_sort(left) + middle + quick_sort(right) 

```
 The process involves selecting a pivot value and dividing the list into sublists greater or smaller or equal to the value. This process is repeated recursively to sort the items and then merge them back together at the end.

This method has a variable time complexity based on the pivot selection. In worst case scenario this produces the same result of O(n^2). In the code block presented, the worst case scenario would occur if the list was already sorted. To avoid this we can take a median of three randomly selected values or choose an i-th value that's case relevant and use that as a pivot instead. While this would not guarantee that we never encounter the worst case it would improve the odds of it occuring. By mitigating the issue with a good pivot, the good and/or average cases have an improved time complexity of n * logn or O(nlogn) for short. Note that the log base 2 n represents the splitting complexity formed from the recursion. Because we are generating subarrays for each recursion we find we will have a larger memory requirement of O(logn). 

In comparing the two methods we find that selection sort is easy to implement because it's simple and space conservative. Quick sort is better on time given the correct pivot selection with slightly worse off for space complexity. In a real-world setting where time is poor and space is abundant it is more likely to see quick sort being used as it works better in larger data sets for sorting data quickly.  



---

###	Q2 Identify and explain the workings of TWO search algorithms and discuss and compare their performance/efficiency (i.e. Big O)

---

Searching algorithms move through data in a methodical way looking to identify the search value/s index within that data set. Let's look at a comparison between 2 algorithms, the sequential search method and a binary search method.


Sequential Search also known as a linear search, occurs when the list or array is traversed from beginning to end and every element is checked against the lookup value. Below is a coding example in python3;

##### The linear search method

```
def linear_search(array, target):

    #loop through the search options
    for i in range(len(array)):

        #check to see if the option matches the target
        if target == array[i]
            return i
    return -1

```

This function has a time complexity of O(n) in the worst case. The best case could result in the target being found in the first slot producing a O(1) for complexity. However when the target of the search is for multiple values (would have to modify this code to accommodate) the time complexity spikes up to O(n^2) as we will need to loop through each value of the search list and the data set. There is no additional storage used apart from the target and the array resulting in a space capacity of O(1).

Let's compare a binary search;

Binary search is specifically designed for searching in data structures and is limited to data that is already sorted. If the data needs to be sorted then an additional time complexity will need to be added when reviewing the worst case scenario. The method works by essentially splitting the data set in half over and over again until a match is found. below is an example of this how this would look in python3 code.


##### The binary search method

```
def binary_search(array, target):

     # Define the left and right pointers
    left, right = 0, len(arr) - 1 
    
    #create loop
    while left <= right:

        # get the middle index
        mid = (left + right) // 2  
        
        #check to see the middle value matches the target
        if array[mid] == target:

            # Target found, return the index
            return mid

        #check each side for the target and shorten the array accordingly 
        elif array[mid] < target:
            left = mid + 1
        else:
            right = mid - 1
    
    # Target element not found in the list
    return -1  

```

The time complexity for this algorithm is O(logn) due to the splitting occuring at each step effectively halving total amount of iterations per stage. By retaining only the half of the array at each stage this is inherently quicker than a linear search. The space complexity is also O(1) which is the same as a linear search algorithm. At first glance this looks to be better than a linear search however there are a number of drawbacks. The data set must be sorted and use comparable values meaning that they can be sorted.

In comparison the linear search method is better for smaller data sets while larger data sets should favour the binary search method. The constraints for searching are more lax for linear search where binary searches are constrained to only searching sorted data. The amount of occupied space is the same regardless of which of the two methods is used.




---


Resources 

geeksforgeeks.org
