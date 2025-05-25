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

### Task 3

### Task 4

### Task 5

### Task 6
