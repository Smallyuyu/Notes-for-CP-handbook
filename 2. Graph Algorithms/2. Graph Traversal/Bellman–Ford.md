## Bellman–Ford(無法算負環) 
```cpp
//0到各點的最短路徑
priority_queue<pair<int,int>,vector<pair<int,int>>,greater<pair<int,int>>> pq;
pq.push({0,0});//{index,dis};
while(pq.size()){
    auto cur = pq.top();
    pq.pop();
    if(cur.first > dis[cur.second]) continue;
    for(auto s : adj[cur.second]){
        if(dis[s.first] > dis[cur.second] + s.second){
            dis[s.first] = dis[cur.second] + s.second;
            pq.push({dis[s.first],s.first});
        }
    }
}
```
