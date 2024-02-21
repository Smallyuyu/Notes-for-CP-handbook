## Diameter
```cpp
//the maximum length of a path between two nodes
void find_diameter(int cur, int prev) {
    dis[cur] = dis[prev] + 1;
    if(dis[cur] > dis[maxdis]) maxdis = cur;
    for(auto s : adj[cur]) {
        if(s == prev) continue;
        find_diameter(s, cur);
    }
}
```
