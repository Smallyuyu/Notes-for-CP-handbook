## BFS  
```cpp
queue<int> q;
while(q.size()){
    int cur = q.front();
    q.pop();
    for(auto s : adj[cur]){
        if(vis[s]) continue;
        dis[s] = dis[cur] + 1;
        vis[s] = 1;
        q.push(s);
    }
}
```
