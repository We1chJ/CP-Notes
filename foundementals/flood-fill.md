# Flood Fill

## Definition

Flood Fill is a graph algorithm that works well on the grid (but not limited to) to find information about different components of a graph. E.g., find how many connected components are in a grid given walls scattering all over.

It can be easily implemented using recursive approach by making up, down, left, right, four recursive calls. Flood Fill essentially is a [DFS ](../advanced/graph-theory/bfs.md#dfs-depth-first-search)algorithm.

Example:

```cpp
void ff(int x, int y){
    if(x < 0 || x >= n || y < 0 || y >=  m || arr[x][y] != 1)
        return ;
    
    arr[x][y] = 2;
    ff(x+1, y);
    ff(x-1, y);
    ff(x, y+1);
    ff(x, y-1);

}
```

Note that Flood Fill can take up a lot of stack memories or lead to StackOverflow if the grid size is too large.&#x20;

The time complexity is usually the size of the grid $$O(NM)$$
