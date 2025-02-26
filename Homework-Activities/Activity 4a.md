1. Proof that, under the average-case scenario, the insertion sort has a time complexity of O(N^2). Draw a clear figure and show all the operations clearly.



3. At the start of the insertion sort, the index of the inspected value is set to 1. Change the index of the inspected value and verify that the total number of operations equals 20. Consider the worst-case scenario. Use N=5, where N is the number of elements.


4. The following function returns whether or not a capital “X” is present within a string.
function containsX(string) {
	foundX = false;
	for(let i = 0; i < string.length; i++) { 
		if (string[i] === "X") {
			foundX = true; 
		}
	}
	return foundX; 
}

(a) What is this function’s time complexity regarding Big O Notation?


(b) Then, modify the code to improve the algorithm’s efficiency for best- and average-case scenarios.
