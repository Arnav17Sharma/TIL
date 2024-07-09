
---
[Cycle Detection in Directed Graph (BFS)](https://www.geeksforgeeks.org/problems/detect-cycle-in-a-directed-graph/1)
Topic: [[Graphs TopoSort]] [[Graphs]]
tags: #dsa #graphs #toposort #bfs #kahn 
date: 09-07-2024-07-09

---
## Code 

```cpp
    bool isCyclic(int V, vector<int> adj[]) {
        vector<int> indegree(V);
        for(int i=0; i<V; i++) {
            for(auto x: adj[i]) {
                indegree[x]++;
            }
        }
        queue<int> q;
        for(int i=0; i<V; i++) {
            if(indegree[i] == 0)
                q.push(i);
        }
        vector<int> ans;
        while(!q.empty()) {
            int node = q.front();
            q.pop();
            ans.push_back(node);
            
            for(auto x: adj[node]) {
                indegree[x]--;
                if(indegree[x] == 0) {
                    q.push(x);
                }
            }
        }
        if(ans.size() != V) {
            return 1;
        }
        return 0;
    }
```

---
# 🦚 राधे राधे 🦚
---
