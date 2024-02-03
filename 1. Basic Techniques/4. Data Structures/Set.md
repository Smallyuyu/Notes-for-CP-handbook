## Set
```cpp
//遍歷
for (auto it = s.begin(); it != s.end(); it++) {
  cout << *it << "\n";
}
//找x
auto it = s.find(x);
if (it == s.end()) {
  // x is not found
}
//找最接近x的數
auto it = s.lower_bound(x);
if (it == s.begin()) {
  cout << *it << "\n";
}
else if (it == s.end()) {
  it--;
  cout << *it << "\n";
}
else {
  int a = *it; it--;
  int b = *it;
  if (x-b < a-x) cout << b << "\n";
  else cout << a << "\n";
}
```

