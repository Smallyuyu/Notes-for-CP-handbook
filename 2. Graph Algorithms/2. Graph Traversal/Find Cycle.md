## Find Cycle
```cpp
void findcircle(int x,int pre){
    p[x] = pre;
    vis[x] = 1;
    for(int u : adj[x]){
        if(u == pre) continue;
        if(vis[u]){
            vector<int> ans;
            ans.push_back(u);
            while(x^u){
                ans.push_back(x);
                x = p[x];
            }
            ans.push_back(x);
            cout<<ans.size()<<'\n';
            for(int i = ans.size() - 1; i >= 0 ; i--){
                cout<<ans[i] + 1<<" ";
            }
            exit(0);
        }
        findcircle(u,x);
    }
}
```
