## Number of Nodes in Subtree
```cpp
void dfs(int s, int prev) {
  count[s] = 1;
  for (auto u : adj[s]) {
    if (u == prev) continue;
    dfs(u, s);
    count[s] += count[u];
  }
}
```
