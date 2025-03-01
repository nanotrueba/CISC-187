```
## Proof that, under the average-case scenario, the insertion sort has a time complexity of O(N^2). Draw a clear figure and show all the operations clearly.
Insertion sort is an algorithm built on comparisons and shift to build a sorted array one element at a time. As the search goes on, each element is comapred to half of the elements that come before it because we are building a sorted list, reducing the need to search through the entire list each time we compare elements. This tells us that on average, the number of comparisons for each element will be roughly N/2. Now, we need to sum this operation over all the elements in the list because insertion sort performs the (N/2) operation for each element. We need to perform the summation from i=1 all the way to N. Because we are summing up to 'N", our result becomes (N^2 + N)/4. We can drop any constants and non-leading variables, so the 1/4 and N goes away and we are left with the final time complexity for the insertion sort algorithm: O(N^2).

## At the start of the insertion sort, the index of the inspected value is set to 1. Change the index of the inspected value and verify that the total number of operations equals 20. Consider the worst-case scenario. Use N=5, where N is the number of elements.
Considering the worst-case scenario for N=5 (a perfectly reverse sorted list), we will change our inspected value to 1. Now, we have to change the index of the inspected value and verify that total number of operations is equal to 20. This means, we have to inspect from element 1 to N-1 (entire list). Because we are considering 'worst-case' conditions, each element needs to be compared to each element before it and we will need to perform a comparison and swap at each element (1, 2, 3, 4). For each of these elements, they will have an increasing number of comparisons. Index 1 will have 1 comparison, Comparison 2 will have 2, and so on which gives us 1 + 2 + 3 + 4 + 5. This is equal to 15. We also need to perform a shift for each element of the list which means 5 shifts total. 15 + 5 = 20 total operation performed for the worse-case scenario list. 

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
This function contains 2 main opertations: a 'for loop' that iterates through the entire string and an 'if statement' that checks to see if any portion of the string contains a capital X. When the capital X is found, it will update the value of 'foundX' to true and return True. The for loop will take O(N) time as it will iterate through the entire list which is of size N. The if statement within the loop will take O(1) time which does not affect the leading coefficient of the function. Because of this, we can drop it when considering the time complexity which means the final time complexity is O(N).

## Then, modify the code to improve the algorithm’s efficiency for best- and average-case scenarios.
To improve the efficiency of the code, it would be smart to exit the loop as soon as we found "X" within our string. This is because if we had a very long string, the function would iterate through the entire string even if there is only one "X" at the beginning of the string. We can save time here by implementing a return statement where the 'foundX' variable is currently being updated. "foundX = true;" will become "return true;" If this was a counter function that returns how many times "X" is seen in the string, then it would be necesary to iterate through the whole list. But in this case, we only want to know if the string contains "X" once, we can exit our loop as soon as we find our target, earning us some extra efficiency. We will need to include a "return false;" statement where the "return foundX;" currently is in case we finish the loop and still don't find the target "X" within our string. This modification doesn't change our 'worst-case' scenario, but offers a big upgrade to our "best-case" scenario.

```
