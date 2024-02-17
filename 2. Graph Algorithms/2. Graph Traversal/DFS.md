## DFS
```cpp
void dfs(int cur){
    if(vis[cur]) return;
    vis[cur] = 1;
    for(auto s : adj[cur]){
        dfs(s);
    }
}
```
