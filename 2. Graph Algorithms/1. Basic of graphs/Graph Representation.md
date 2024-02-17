## Graph Representation(Nodes)
```cpp
//有向圖 u指向v
vector<int> adj[n];
for(int i = 0 ; i < n ; i++){
    int u,v;
    cin>>u>>v;
    adj[u].push_back(v);
}
```
```cpp
//權重有向圖 u指向v,權重為w
cin>>n;
vector<pair<int,int>> adj[n];
for(int i = 0 ; i < n ; i++){
    int u,v,w;
    cin>>u>>v>>w;
    adj[u].push_back({v,w});
}
```
```cpp
//權重有向圖 u指向v,權重為w
//可快速查edge是否存在，但較佔空間
int adj[n][n];
for(int i = 0 ; i < n ; i++){
    int u,v,w;
    cin>>u>>v>>w;
    adj[u][v] = w;
}
```
## Graph Representation(Edges)
```cpp
//從u到v的edge
vector<pair<int,int>> edges;
for(int i = 0 ; i < n ; i++){
    int u,v;
    cin>>u>>v;
    edges.push_back({u,v});
}
```
```cpp
//從u到v的edge,權重為w
vector<tuple<int,int,int>> edges;
for(int i = 0 ; i < n ; i++){
    int u,v,w;
    cin>>u>>v>>w;
    edges.push_back({u,v,w});
}
```
