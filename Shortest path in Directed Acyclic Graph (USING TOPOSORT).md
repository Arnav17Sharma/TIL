
---
[Shortest path in Directed Acyclic Graph](https://www.geeksforgeeks.org/problems/shortest-path-in-undirected-graph/1)
Topic: [[Graphs]] 
tags: #dsa 
date: 12-07-2024-07-12

---
## Approach

- Do Toposort
- Distance calculation from toposort stack

## Code 

```cpp
class Solution {
  private:
    void dfs(int i, vector<vector<pair<int, int>>> &adj, vector<int> &vis, stack<int> &st) {
        vis[i] = 1;
        for(auto x: adj[i]) {
            int end = x.first;
            int dist = x.second;
            if(!vis[end])
                dfs(end, adj, vis, st);
        }
        st.push(i);
    }
  public:
     vector<int> shortestPath(int N,int M, vector<vector<int>>& edges){
        vector<vector<pair<int, int>>> adj(N);
        for(int i=0; i<edges.size(); i++) {
            int u = edges[i][0];
            int v = edges[i][1];
            int wt = edges[i][2];
            adj[u].push_back({v, wt});
        }
        
        vector<int> vis(N, 0);
        stack<int> st;
        for(int i=0; i<N; i++) {
            if(!vis[i]) {
                dfs(i, adj, vis, st);
            }
        }
        
        vector<int> dist(N, 1e9);
        dist[0] = 0;
        while(!st.empty()) {
            int node = st.top();
            st.pop();
            for(auto x: adj[node]) {
                int next = x.first;
                int wt = x.second;
                if(dist[node] + wt < dist[next]) {
                    dist[next] = dist[node] + wt;
                }
            }
        }
        for (int i = 0; i < N; i++) {
            if (dist[i] == 1e9) dist[i] = -1;
        }
        return dist;
    }
};
```

---
# 🦚 राधे राधे 🦚
---
