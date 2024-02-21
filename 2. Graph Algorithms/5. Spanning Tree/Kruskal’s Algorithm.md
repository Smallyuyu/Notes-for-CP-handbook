## Kruskal’s Algorithm
```cpp
//找最小生成樹
struct DSU {
    vector<int> f;
    vector<int> s;
    
    DSU() {}
    DSU(int n) {
        init(n);
    }
    
    void init(int n) {
        f.resize(n);
        iota(f.begin(), f.end(), 0); //0,1,2,3...
        s.assign(n, 1);
    }
    
    int find(int x) {
        while (x != f[x]) {
            x = f[x] = f[f[x]];
        }
        return x;
    }
    
    bool same(int x, int y) {
        return find(x) == find(y);
    }
    
    bool merge(int x, int y) {
        x = find(x);
        y = find(y);
        if (x == y) return false;
        s[x] += s[y];
        f[y] = x;
        return true;
    }
    
    int size(int x) {
        return s[find(x)];
    }
};
struct Edge {
    int u, v, w;
    bool operator<(const Edge& edge)const {
        return w < edge.w;
    }
};
vector<Edge> edge;
int Kruskal(){
    DSU dsu;
    dsu.init(n);
    int sum = 0;
    for(int i = 0; i < n; ++i) {
        if(dsu.merge(edge[i].u, edge[i].v)){
            sum += edge[i].w;
        }
    }
    return sum;
}
//參考自Jiangly、purinliang
```
