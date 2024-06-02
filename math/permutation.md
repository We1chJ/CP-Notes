# Permutation

## Generating Permutations

### 1. Recursion

At every point, loop through all future elements and make a decision if needs to include it or not.

```cpp
void search() {
    if (permutation.size() == n) {
        // process permutation
    } else {
        for (int i = 0; i < n; i++) {
            if (chosen[i]) continue;
            chosen[i] = true;
            permutation.push_back(i);
            search();
            chosen[i] = false;
            permutation.pop_back();
        }
    }
}
```
