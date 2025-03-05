## 1. Assume you have a simple single-dimensional array. array = [200, 400, 100, 50, 350]; Linear search will take O(N). Write a code in C++/Python to improve the search operation efficiency from O(N)to O(1).
```
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

## 3. With the help of a figure, explain the problem that occured due to introducing a tombstone to mark the deleted cell.
