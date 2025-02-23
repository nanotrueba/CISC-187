```cpp
#include <iostream>
using namespace std;

//linear search
//we will implement a search algorithm that searches each element incrementally, checking to see if the index stores our element
int linear(int arr[], int sizeofArray, int target, int &numSteps) {
    for (int i = 0; i < sizeofArray; i++) {
        numSteps++;
        if (arr[i] == target) {
            return i;
        }
    }   return -1;
}

//binary search
//implement a search algo that cuts the search length in half each step
//by using 'middle' we will see if our target is higher or lower than middle and go to the next 'middle and repeat until found
int binary(int arr[], int sizeofArray, int target, int &numSteps) {
    int left = 0, right = sizeofArray - 1; //left begins at index 0 while right begins at the last element of the array
    while (left <= right) {
        numSteps++;
        int mid = (left + right) / 2;
        if (arr[mid] == target)
            return mid; //target found
        else if (arr[mid] < target)
            left = mid + 1;
        else right = mid -1;
        }
    return -1;
    }

int main() {

    int array1[7] = {2, 4, 6, 8, 10, 12, 13};
    int size = 7;
    int target = 8;

    //steps are initialized
    int linearSteps = 0, binarySteps = 0;

    int linearAnswer = linear(array1, size, target, linearSteps);
    cout << "The linear search method found the target in " << linearSteps << " steps at position " << linearAnswer << endl;

    int binaryAnswer = binary(array1, size, target, binarySteps);
    cout << "The binary search method found the target in " << binarySteps << " steps at position " << binaryAnswer << endl;

    return 0;
}
```
