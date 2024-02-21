## Tree traversal
```cpp
void dfs(int s, int prev) {
  // process node s
  for (auto u : adj[s]) {
    if (u != prev) dfs(u, s);
  }
}
```
