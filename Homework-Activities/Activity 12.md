### 1. Following is the 'Word Builder' algorithm. Describe its space complexity in terms of Big O.
```
function wordBuilder(array) { 
		let collection = [];
		for(let i = 0; i < array.length; i++) { 
				for(let j = 0; j < array.length; j++) {
						if (i !== j) {
								collection.push(array[i] + array[j]);
						}
				}
		}
		return collection; 
}
```
The 'Word Builder' algorithm has a space complexity of O(N^2). We see the above algorithm uses a nested loop to generate all possible pairs of an input array and stores it in "collection". Because it pushes array[i] and arra[j], this makes the resulting space complexity to O(N^2). Then there is the condition "if (i !== j)" which skips the inner loop whenever i is equal to j. This subtracts N from our N^2 terms because we skip any i that are equal to j. In final, the space complexity simplifies to O(N^2).

### 2. Following is a function that reverses an array. Describe its space complexity in terms of Big O:
```
function reverse(array) { 
		let newArray = [];
		for (let i = array.length - 1; i >= 0; i--) { 
				newArray.push(array[i]);
		}
		return newArray;
}
```
The function above has a space complexity of O(N). This is because the function begins by initializing an emtpy array called newArray and iterating through the input array once from the end to the front. During each iteration it pushes one character from the input array to the array called newArray. When each element is copied from the input array into newArray, the space required grows with the size of the input. In the end the space complexity results to O(N).

### 3. Create a new function to reverse an array that takes up just O(1) extra space.
If we want to reverse an array that takes up O(1) space, we need to reverse the array in place rather than using a new array to store our modified array. We need pointers to control the left and right pointers of the array while swapping the left and right elemtns in each iteration.
```
function reverse(array) {
// initialize pointers
    let left = 0;
    let right = array.length - 1;

    while (left < right) {
        // swapping logic below
        [array[left], array[right]] = [array[right], array[left]];

// move each pointer 
        left++;
        right--;
    }
    return array;
}
```
Now our function doesn't create a new array which keeps our space complexity at O(N).

### 4. Following are three different implementations of a function that accepts an array of numbers and returns an array containing those numbers multiplied by 2. For example, if the input is [5, 4, 3, 2, 1], the output will be [10, 8, 6, 4, 2].
```
function doubleArray1(array) { 
	let newArray = [];

	for(let i = 0; i < array.length; i++) { 
		newArray.push(array[i] * 2);
	}
	return newArray; 
}


function doubleArray2(array) {
	for(let i = 0; i < array.length; i++) {
  	array[i] *= 2;
  }
	return array; 
}


function doubleArray3(array, index=0) { 
	if (index >= array.length) { return; }
  array[index] *= 2;
  doubleArray3(array, index + 1);
	return array; 
}
```
Fill in the table that follows to describe the efficiency of these three versions in terms of both time and space:
```
 Version       Time complexity	    Space complexity
Version #1	    O(N)	          O(N)
Version #2	    O(N)	          O(1)
Version #3	    O(N)	          O(N)
```
