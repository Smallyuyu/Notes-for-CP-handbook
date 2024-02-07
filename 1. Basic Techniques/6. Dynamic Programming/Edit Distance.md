## Edit Distance
```cpp
  string s1,s2;
  cin>>s1>>s2;
  int n = s1.length();
  int m = s2.length();
  n++,m++;
  vector<vector<int>> dp(n,vector<int>(m,INT_MAX));
  for(int i = 0 ; i < n ; i++){
      dp[i][0] = i;
  }
  for(int i = 0 ; i < m ; i++){
      dp[0][i] = i;
  }
  for(int i = 1 ; i < n ; i++){
      for(int j = 1 ; j < m ; j++){
          dp[i][j] = min({dp[i][j - 1] + 1,dp[i - 1][j] + 1,dp[i - 1][j - 1] + (s1[i - 1] != s2[j - 1])});
      }
  }
  cout<<dp[n - 1][m - 1]<<'\n';
```
