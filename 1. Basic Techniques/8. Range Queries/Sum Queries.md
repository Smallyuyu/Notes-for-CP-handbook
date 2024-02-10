## 前綴和
```cpp
int n,q;
cin>>n>>q;
vector<long long int> arr(n,0),pre(n + 1,0);
for(int i = 0 ; i < n ; i++){
    cin>>arr[i];
}
for(int i = 1 ; i <= n ; i++){
    pre[i] = pre[i - 1] + arr[i - 1];
}
int a,b;
while(q--){
    cin>>a>>b;
    cout<<pre[b] - pre[a - 1]<<'\n';
}
```

