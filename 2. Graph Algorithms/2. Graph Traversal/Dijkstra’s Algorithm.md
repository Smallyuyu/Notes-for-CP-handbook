## Dijkstra’s algorithm(不可算負環) 
```cpp
//以s為起點到各點的最短路徑
void Dijkstra(int s){
    fill(dis.begin(),dis.begin() + n,1e16);
    fill(vis.begin(),vis.begin() + n,0);
    priority_queue<pair<int,int>> pq;
    dis[s] = 0;
    pq.push({0,s});
    while(pq.size()){
        int cur = pq.top().second;
        pq.pop();
        if(vis[cur]) continue;
        vis[cur] = 1;
        for(auto s : adj[cur]){
            int v = s.first;
            int w = s.second;
            if(vis[v] || dis[cur] + w >= dis[v]) continue;
            dis[v] = dis[cur] + w;
            pq.push({-dis[v],v});
        }
    }
}
```
