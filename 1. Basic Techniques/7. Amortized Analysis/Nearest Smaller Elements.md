## Nearest Smaller Elements
```cpp
//單調棧
int n;
cin>>n;
vector<int> arr(n,0);
for(int i = 0 ; i < n ; i++){
    cin>>arr[i];
}
stack<int> st;
for(int i = 0 ; i < n ; i++){
    while(st.size() && arr[st.top()] >= arr[i]){
        st.pop();
    }
    if(!st.size()){
        cout<<0<<" ";
    }
    else{
        cout<<st.top() + 1<<" ";
    }
    st.push(i);
}
```
