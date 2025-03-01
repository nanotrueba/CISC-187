## Proof that, under the average-case scenario, the insertion sort has a time complexity of O(N^2). Draw a clear figure and show all the operations clearly.
Insertion sort is an algorithm built on comparisons and shift to build a sorted array one element at a time. As the search goes on, each element is comapred to half of the elements that come before it because we are building a sorted list, reducing the need to search through the entire list each time we compare elements. This tells us that on average, the number of comparisons for each element will be roughly N/2. Now, we need to sum this operation over all the elements in the list because insertion sort performs the (N/2) operation for each element. We need to perform the summation from i=1 all the way to N. Because we are summing up to 'N", our result becomes (N^2 + N)/4. We can drop any constants and non-leading variables, so the 1/4 and N goes away and we are left with the final time complexity for the insertion sort algorithm: O(N^2).

## At the start of the insertion sort, the index of the inspected value is set to 1. Change the index of the inspected value and verify that the total number of operations equals 20. Consider the worst-case scenario. Use N=5, where N is the number of elements.


## The following function returns whether or not a capital “X” is present within a string.
function containsX(string) {
	foundX = false;
	for(let i = 0; i < string.length; i++) { 
		if (string[i] === "X") {
			foundX = true; 
		}
	}
	return foundX; 
}

## What is this function’s time complexity regarding Big O Notation?


## Then, modify the code to improve the algorithm’s efficiency for best- and average-case scenarios.
