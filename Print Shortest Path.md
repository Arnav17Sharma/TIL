
---
Topic : [[Print Shortest Path]] [[Graphs]]
date : 28-08-2024
tags : #dsa 

---
```cpp
vector<int> shortestPath(int n, int m, vector<vector<int>>& edges) {
        
        vector<pair<int,int>> adj[n+1];
        
        for(vector<int>& edge: edges)
        {
            int fromNode = edge[0];
            int toNode = edge[1];
            int dist = edge[2];
            
            adj[fromNode].push_back({toNode, dist});
            adj[toNode].push_back({fromNode, dist});
        }
        
        vector<int> distances(n+1, 1e9);
        vector<int> parent(n+1);
        priority_queue<pair<int, int>, vector<pair<int,int>>,
								       greater<pair<int,int>>> pq;
        
        pq.push({ 0, 1 });
        distances[1] = 0;
        parent[1] = 1;
        
        while(!pq.empty()) {
            int node = pq.top().second;
            int dist = pq.top().first;
            pq.pop();
            
            for(pair<int,int>& neighbour: adj[node]) {
                int newNode = neighbour.first;
                int newDist = neighbour.second;
                
                if(dist + newDist < distances[newNode]) 
                {
                    distances[newNode] = dist + newDist;
                    parent[newNode] = node;
                    pq.push({ distances[newNode], newNode });
                }
            }
        }
        if(distances[n] == 1e9) return {-1};
        
        vector<int> path;
        int node = n;
        path.push_back(node);
        
        while(parent[node] != node) {
            path.push_back(parent[node]);
            node = parent[node];
        }
        
        reverse(path.begin(), path.end());
        return path;
    }
```

