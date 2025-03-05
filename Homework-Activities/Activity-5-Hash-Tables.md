## 1. Assume you have a simple single-dimensional array. array = [200, 400, 100, 50, 350]; Linear search will take O(N). Write a code in C++/Python to improve the search operation efficiency from O(N)to O(1).
```python
# 'fromkeys' creates a dictionary in which the elements in array
# are the keys. Pass 'array' as a parameter to assign our array
# to the keys of the hash map.
hashed = dict.fromkeys(array)

# The following line will return True for any
# number that is in 'array'

print(200 in hashed)
# True
```

## 2. Use C++ to generate the hash value of your name
```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string myName = "Nathaniel";
    unsigned long hash = 0;

// iterates over the string myName and multiplies the character by a prime number for the hash function
// and adds the  ASCII value to the hash to update the value for each character.
    for (char c : myName) hash = hash * 31 + c;

    // Result line
    cout << hash << endl;
    return 0;
}
```
Result is 69300245310556.

## 3. With the help of a figure, explain the problem that occured due to introducing a tombstone to mark the deleted cell.
A tombstone takes the place in a hash table where there was a key-value pair before. When too many tombstones begin to fill the hash table, it can negatively affect the performance of the hash table.
Hash table: E-empty T-tombstone I-in use
E E I I E E I E I
If I were to delete the first in-use space, the hash table would look like this:
E E T I E E I E I
Now, instead of being empty, the previously 'in-use' space is now filled by a Tombstone. If we delete another,
E E T I E E I E T
Now there are 2 Tombstones. If a hash table becomes too filled with Tombstones, it will negatively affect the hash table's performance
because there aren't Empty slots, the Tombstones sact differently and can complicate the hashing function. Such complications could be 
false positives, incomplete searches and other slowing of performance.
