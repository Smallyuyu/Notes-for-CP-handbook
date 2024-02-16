## Graph Terminology
```cpp
Connected: Graph中的所有node皆可互相抵達
Components: Graph中具Connected的子圖
Tree: n nodes,n - 1 edges的Graph
```
```cpp
Neighbors: 相鄰於該node的點
Degrees: 該node具有的Neighbors數量
*圖中所有nodes的degrees的總和必為2 * m, m為edges的數量
```
```cpp
Regular Graph: 所有nodes的degrees皆相同
Complete Graph: 所有nodes的degrees皆為n - 1, n為nodes的數量 
```
```cpp
Indegree: 有向圖中指向該nodes的數量
Outdegree: 有向圖中指離該nodes數量
```
```cpp
Bipartite Graph: 該圖中所含的Cycle皆不為奇數edges
Simple Graph: 兩個nodes間最多只有一個edge, 且沒有同時指向又指離同一node的edge
```
