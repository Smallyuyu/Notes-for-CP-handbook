## Additional Functions
```cpp
__builtin_clz(x): 回傳左邊第一個1的位置
__builtin_ctz(x): 回傳右邊第一個1的位置
__builtin_popcount(x): 回傳1的個數
__builtin_parity(x): 回傳1的個數是否為奇數
```
```cpp
int x = 5328; // 00000000000000000001010011010000
cout << __builtin_clz(x) << "\n"; // 19
cout << __builtin_ctz(x) << "\n"; // 4
cout << __builtin_popcount(x) << "\n"; // 5
cout << __builtin_parity(x) << "\n"; // 1
```
## Hamming Distances
```cpp
//計算兩個Bit不同處的個數
int hamming(string a, string b) {
  int d = 0;
  for (int i = 0; i < k; i++) {
    if (a[i] != b[i]) d++;
  }
  return d;
}
//快上面的三十倍
int hamming(int a, int b) {
  return __builtin_popcount(a^b);
}
```
```cpp
int n,k;
cin>>n>>k;
vector<string> s(n);
vector<int> arr(n,0);
for(int i = 0 ; i < n ; i++){
    cin>>s[i];
}
int ans = INT_MAX;
for(int i = 0 ; i < n ; i++){
    arr[i] = stoi(s[i], nullptr, 2);
}
for(int i = 0 ; i < n ; i++){
    for(int j = i + 1 ; j < n ; j++){
        ans = min(ans,__builtin_popcount(arr[i] ^ arr[j]));
    }
}
cout<<ans<<'\n';
```
