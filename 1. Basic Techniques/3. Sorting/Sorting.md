## Pair,Tuple
```cpp
vector<pair<int,int>> v;
vector<tuple<int,int,int>> v;
```
## cmp
```cpp
bool cmp(string a, string b) {
  if (a.size() != b.size()) return a.size() < b.size();
  return a < b;
}
sort(v.begin(), v.end(), cmp);
```
## 二分搜1
```cpp
int a = 0, b = n-1;
while (a <= b) {
  int k = (a + b)/2;
  if (array[k] == x) {
    return k;
  }
  if (array[k] > x) b = k - 1;
  else a = k + 1;
}
```
## 二分搜2
```cpp
int k = 0;
for (int b = n/2; b >= 1; b /= 2) {
  while (k + b < n && array[k+b] <= x) k += b;
}
if (array[k] == x) {
  return k;
}
```
## lower_bound,upper_bound,equal_range
```cpp
  //找x在array的個數
  auto a = lower_bound(array, array+n, x);
  auto b = upper_bound(array, array+n, x);
  cout << b-a << "\n";
  //等價於
  auto r = equal_range(array, array+n, x);
  cout << r.second - r.first << "\n";
```
## O(logN)找極值
f(x) < f(x+1) when x < k, and

f(x) > f(x+1) when x >= k.
```cpp
  int x = -1;
  for (int b = z; b >= 1; b /= 2) {
    while (f(x + b) < f(x + b + 1)) x += b;
  }
  int k = x + 1;
```

