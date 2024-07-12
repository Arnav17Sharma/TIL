
---
[Shortest Path in Undirected Graph](https://www.geeksforgeeks.org/problems/shortest-path-in-undirected-graph-having-unit-distance/1)
Topic: [[Graphs]]
tags: #dsa 
date: 12-07-2024-07-12

---
## Approach

- Normal BFS 

## Code 

```cpp
class Solution {
  public:
    vector<int> shortestPath(vector<vector<int>>& edges, int N,int M, int src){
        vector<vector<int>> adj(N);
        for(int i=0; i<M; i++) {
            int u = edges[i][0];
            int v = edges[i][1];
            adj[u].push_back(v);
            adj[v].push_back(u);
        }
        
        queue<int> q;
        vector<int> dis(N, 1e9);
        dis[src] = 0;
        q.push(src);
        while(!q.empty()) {
            int node = q.front();
            q.pop();
            for(auto x: adj[node]) {
                if(dis[node] + 1 < dis[x]) {
                    dis[x] = dis[node] + 1;
                    q.push(x);
                }
            }
        }
        
        for(int i=0; i<N; i++) {
            if(dis[i] == 1e9) dis[i] = -1;
        }
        return dis;
    }
};
```

---
# 🦚 राधे राधे 🦚
---
