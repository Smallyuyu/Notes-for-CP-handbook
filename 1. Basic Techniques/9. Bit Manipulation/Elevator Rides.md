## Elevator Rides
```cpp
//位元DP
int n,x;
cin>>n>>x;
vector<int> w(n,0);
for(int i = 0 ; i < n ; i++){
    cin>>w[i];
}
vector<pair<int,int>> dp(1 << n);
dp[0] = {1,0};
for(int i = 1 ; i < (1 << n) ; i++){
    dp[i] = {n + 1, 0};
    for(int j = 0 ; j < n ; j++){
        if(i & (1 << j)){
            auto cur = dp[i ^ (1 << j)];
            if(cur.second + w[j] <= x){
                cur.second += w[j];
            }
            else{
                cur.first++;
                cur.second = w[j];
            }
            dp[i] = min(dp[i],cur);
        }
    }
}
cout<<dp[(1 << n) - 1].first<<'\n';
```
