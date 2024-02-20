## Bellman–Ford (可算負環) 
```cpp
//可算負邊
//效率比Dijkstra差
bool bellmanford(int s){
    fill(dis.begin(),dis.begin() + n,1e16);
    fill(vis.begin(),vis.begin() + n,0);
    fill(cnt.begin(),cnt.begin() + n,0);
    queue<int> q;
    dis[s] = 0;
    q.push(s);
    while(q.size()){
        int cur = q.front();
        q.pop();
        vis[cur] = 0;
        cnt[cur]++;
        if(cnt[cur] == n){
            return false;
        }
        for(auto s : adj[cur]){
            int v = s.first;
            int w = s.second;
            if(dis[cur] + w >= dis[v]) continue;
            dis[v] = dis[cur] + w;
            if(!vis[v]){
                vis[v] = 1;
                q.push(v);
            }
        }
    }
    return true;
}
```
