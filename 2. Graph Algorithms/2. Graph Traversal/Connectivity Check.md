## Connectivity Check
```cpp
bool checkconnectivity(){
    for(int i = 0 ; i < n ; i++){
        if(!vis[i]){
            return false;
        }
    }
    return true;
}
```
