## Bit Operation
```cpp
int x = (1<<1)|(1<<3)|(1<<4)|(1<<8);
int y = (1<<3)|(1<<6)|(1<<8)|(1<<9);
int a = x & y; //交集
int b = x | y; //合集
int c = ~x; //補集
int d = x & (-b) //差集

cout << __builtin_popcount(b) << "\n"; // 6 (集合個數)
```
## 特殊條件遍歷
```cpp
for (int b = 0; b < (1<<n); b++) {
  if (__builtin_popcount(b) == k) {
    // process subset b
  }
}
```

