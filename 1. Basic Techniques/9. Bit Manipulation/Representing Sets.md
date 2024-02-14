## Representing Sets
```cpp
若一個set介於32bits，則可以以int來表示該set的空間
Eg.{1,3,4,8},num = (1 << 1) + (1 << 3) + (1 << 4) + (1 << 8);
```
```cpp
//存取
int x = 0;
x |= (1<<1);
x |= (1<<3);
x |= (1<<4);
x |= (1<<8);
cout << __builtin_popcount(x) << "\n"; // 4 (回傳集合的個數)
```
```cpp
//遍歷
for (int i = 0; i < 32; i++) {
  if (x & (1 << i)) cout << i << " ";
}
// output: 1 3 4 8
```

