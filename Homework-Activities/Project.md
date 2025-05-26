### Task 1
```cpp
#include <iostream>
#include <vector>
#include <unordered_set>
#include <string>
using namespace std;

vector<string> findCommons(const vector<string>& basketball_players, const vector<string>& football_players) {
    unordered_set<string> common(basketball_players.begin(), basketball_players.end());
    vector<string> result;

    for (const string& name : football_players) {
        if (common.count(name)) {
            result.push_back(name);
        }
    }
    return result;
}

int main() {
    vector<string> basketball_players = {
        "Jill Huang", "Janko Barton", "Wanda Vakulskas",
        "Jill Moloney", "Luuk Watkins"
    };

    vector<string> football_players = {
        "Hanzla Radosti", "Tina Watkins", "Alex Patel",
        "Jill Huang", "Wanda Vakulskas"
    };

    vector<string> common = findCommons(basketball_players, football_players);

    for (const string& name : common) {
        cout << name << endl;
    }
    return 0;
}

```
### Task 2

```cpp
#include <iostream>
#include <vector>
using namespace std;

int findMissing(const vector<int>& nums) {
    int n = nums.size();
    int expected_sum = (n * (n + 1)) / 2; // this is a mathematical property of numbers from 0 to n
    int actual = 0;
    for (int x : nums) {
        actual += x; // update actual as each num is read
    }
    return expected_sum - actual; // returns skipped number from the set of nums
}

int main() {
    vector<int> set1 = {2, 3, 0, 6, 1, 5};
    vector<int> set2 = {8, 2, 3, 9, 4, 7, 5, 0, 6};
    cout << findMissing(set1) << endl;
    cout << findMissing(set2);

    return 0;
}
```
### Task 3

### Task 4

### Task 5

### Task 6
