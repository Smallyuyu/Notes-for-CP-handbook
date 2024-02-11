## Binary Indexed Tree(FenWick Tree)
```cpp
template <typename T>
struct BitT {
    int n;
    std::vector<T> tree;
    
    BitT(int n_ = 0) {
        init(n_);
    }
    
    void init(int n_) {
        n = n_;
        tree.assign(n, T{});
    }
    
    void add(int x, const T &v) {
        for (int i = x; i <= n; i += i & -i) {
            tree[i - 1] = tree[i - 1] + v;
        }
    }
    
    void rangeAdd(int l,int r,int x){
        add(l,x);
        add(r + 1,-x);
    }
    
    void update(int x,const T &v){
        T diff = v - rangeSum(x,x);
        for (int i = x; i <= n; i += i & -i) {
            tree[i - 1] = tree[i - 1] + diff;
        }
    }

    T sum(int x) {
        T ans{};
        for (int i = x; i > 0; i -= i & -i) {
            ans = ans + tree[i - 1];
        }
        return ans;
    }
    
    T rangeSum(int l, int r) {
        return sum(r) - sum(l - 1);
    }
};
```

