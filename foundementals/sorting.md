---
description: >-
  Sorting in arrays, vectors, and other STL, as well as how to use auto
  comparators
---

# Sorting

## Sorting

Default ways to sort in C++:&#x20;

`sort(v.begin(), v.end());` on vectors

`sort(arr, arr + n);`on arrays

**By default, the sort() function sorts the elements in ascending order.**

**To sort in descending order:**

`sort(arr, arr + n, greater<int>());`

The time complexity of most sorting is O(NlogN)

## Custom Comparator

One often needs to apply certain types of sorting that are not provided by default by C++.&#x20;

This would apply to using other C++ STLs such as set, map, priority\_queue, etc, as well as custom classes.

```cpp
bool cmp(const Edge &x, const Edge &y) { return x.w < y.w; }
sort(begin(v), end(v), cmp);
```

Or written in lambda expression:

```cpp
sort(begin(v), end(v), [](const Edge &x, const Edge &y) { return x.w < y.w; });
```

Comparators usually compare two objects in the following way, in ascending order:

* If object $$xxx$$ is less than object $$yyy$$, return `true`
* If object $$xxx$$ is greater than **or equal** to object $$yyy$$, return `false`
