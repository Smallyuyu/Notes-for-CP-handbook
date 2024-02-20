## Floyd–Warshall
```cpp
FloydWarshall(){
    for(int i = 0 ; i < n ; i++){
        for(int j = 0 ; j < n ; j++){
            if(i == j) dis[i][j] = 0;
            else if(adj[i][j]) dis[i][j] = adj[i][j];
            else dis[i][j] = 1e16;
        }
    }
    for(int i = 0 ; i < n ; i++){
        for(int j = 0 ; j < n ; j++){
            for(int k = 0 ; k < n ; k++){
                dis[i][j] = min(dis[i][j],dis[i][k] + dis[k][j]);
            }
        }
    }
}
```
