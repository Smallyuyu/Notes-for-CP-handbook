## Bit DP
```cpp
//K Products
//N Days
int total[1<<K][N];
for (int x = 0; x < k; x++) {
  total[1<<x][0] = price[x][0];
}
for (int d = 1; d < n; d++) {
  for (int s = 0; s < (1<<k); s++) {
  total[s][d] = total[s][d-1];
    for (int x = 0; x < k; x++) {
    if (s&(1<<x)) {
      total[s][d] = min(total[s][d],
      total[s^(1<<x)][d-1]+price[x][d]);
    }
  }
}
```

