
---
[Dijkstra's Algorithm (Using Set](https://www.geeksforgeeks.org/problems/implementing-dijkstra-set-1-adjacency-matrix/1)
Topic: [[Graphs]]
tags: #dsa 
date: 12-07-2024-07-12

---
## Approach

- Same as [[Dijkstra's Algorithm (Using Priority Queue)]] but using set as the functionality is same ONLY. 

## Code 

```cpp
vector <int> dijkstra(int V, vector<vector<int>> adj[], int S)
{
	set<pair<int,int>> st;
	vector<int> dist(V, 1e9); 
	
	st.insert({0, S}); 
	dist[S] = 0;
	
	while(!st.empty()) {
		auto it = *(st.begin()); 
		int node = it.second; 
		int dis = it.first; 
		st.erase(it); 
		for(auto it : adj[node]) {
			int adjNode = it[0]; 
			int edgW = it[1]; 
			
			if(dis + edgW < dist[adjNode]) {
				if(dist[adjNode] != 1e9) 
					st.erase({dist[adjNode], adjNode});
				dist[adjNode] = dis + edgW; 
				st.insert({dist[adjNode], adjNode}); 
			 }
		}
	}
	return dist; 
}
```

---
# 🦚 राधे राधे 🦚
---
