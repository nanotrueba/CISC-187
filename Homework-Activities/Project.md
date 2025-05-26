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
```cpp
#include <iostream>
#include <vector>
#include <climits>
using namespace std;

int maxProfit(const vector<int>& prices) {
    int minPrice = INT_MAX; // initializes minPrice at max so that any lower wins over
    int maxProfit = 0;

    for (int x : prices) {
        if (x < minPrice) { // find cheapest price to buy
            minPrice = x;
        }
        int profit = x - minPrice; //calculate profit
        if (profit > maxProfit) {
            maxProfit = profit; // update whenever profit can be maximized
        }
    }
    return maxProfit;
}

int main() {
    vector<int> stock1 = {10, 7, 5, 8, 11, 2, 6};
    cout << "Max profit: " << maxProfit(stock1);
    return 0;
}
```
### Task 4
```cpp
#include <iostream>
#include <vector>
using namespace std;

int greatestProduct(vector<int>& nums) {
    int max1 = INT_MIN, max2 = INT_MIN;
    int min1 = INT_MAX, min2 = INT_MAX;

    for (int x : nums) {
        if (x > max1) {
            max2 = max1;
            max1 = x;
        } else if (x > max2) {
            max2 = x;
        }

        if (x < min1) {
            min2 = min1;
            min1 = x;
        } else if (x < min2) {
            min2 = x;
        }
    }
    return max(max1 * max2, min1 * min2);
}

int main() {
    vector<int> nums = {5, -10, -6, 9, 4};
    cout << greatestProduct(nums) << endl;
    return 0;
}
```

### Task 5
```cpp
#include <iostream>
#include <vector>
using namespace std;

vector<float> sortTemp(vector<float>& temps) { //accepts a vector of temp floats and returns the sorted vector
    int counts[21] = {0};
    vector<float> result;

    for (float x : temps) {
        counts[int((x - 97.0) * 10)]++; //calculate the index of each temp using the formula
    }

    for (int i = 0; i < 21; i++) {
        for (int j = 0; j < counts[i]; j++) {
            result.push_back(97.0 + i * 0.1); // push actual temperature for each index to the final vector 
        }
    }
    return result;
}

int main() {
    vector<float> temps = {98.6, 98.0, 97.1, 99.0, 98.9, 97.8, 98.5, 98.2, 98.0, 97.1};
    vector<float> sorted = sortTemp(temps);

    for (float x : sorted) {
        cout << x << " ";
    }
    cout << endl;
}
```
### Task 6
