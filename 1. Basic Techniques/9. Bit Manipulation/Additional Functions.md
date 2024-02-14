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

