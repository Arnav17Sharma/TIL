
---
Topic : [[Graphs]]
date : 09-07-2024
tags : #dsa #graphs #dfs #bfs #kahn #toposort 

---
### BFS
- Queue - int, pair, etc. 
- Visited array - 

```cpp
void bfs(vector<vector<int>> &adj, int node, int vis[], vector<int> &ans) {
	queue<int> q;
	q.push(node);
	vis[node] = 1;
	ans.push_back(node);
	
	while(!q.empty()) {
		int main = q.front(); q.pop();
		for(auto x: adj[main]) {
			if(!vis[x]) {
				q.push(x);
				vis[x] = 1;
				ans.push_back(x);
			}
		}
	}
}
void solve(vector<vector<int>> &adj) {
	int n = adj.size();
	vector<int> ans;
	int vis[n] = {0};
	bfs(adj, 0, vis, ans);
	return ans;
}
```

### DFS 
```cpp
void dfs(vector<vector<int>> &adj, int node, int vis[]){
	if(vis[node] == 1) return;
	vis[node] = 1;
	for(auto x: adj[node]) {
		if(!vis[x])
			dfs(adj, x, vis);
	}
}
```

### BFS/DFS Questions - 
- [[Rotten Oranges]]
- [[Surround Regions]]
- [[Number of Enclaves]]
- [[Word Ladder - I]]
- [[Q 01 Matrix]]
- [[Word Ladder - II]]
- [[797. All Paths From Source to Target]]
- [[200. Number of Islands]]
- [[Bipartite Graph]]
- [[Message Routes]]
- [[Building Teams]]
### Topological Sorting - [[Graphs TopoSort]]
### Shortest Path Questions - 

- [[Shortest path in Directed Acyclic Graph (USING TOPOSORT)]]
- [[Shortest Path in Undirected Graph]]
- [[Dijkstra's Algorithm (Using Priority Queue)]]
- [[Dijkstra's Algorithm (Using Set]]
- [[Print Shortest Path]]

### Bellman Ford Algorithm

![[Pasted image 20240829130621.png]]

- Since the Dijkstra Algorithm is not applicable for `NEGATIVE` cycle graphs. 
- Bellman Ford Algorithm saves us in this situation (Does not solve but detects -ve weighted cycles). 
- Works ONLY on directed graphs. 
- For undirected graphs, `convert` it to directed graphs.
- Follows DP-Strategy (Keeping a record of all edges and returning minimum.)
- Involves relaxing of all edges `n-1` times. 
- For `u---->v (costs c)` , `if(dp[u] + c < dp[v]) { dp[v] = dp[u] + c; }`.
- Code:

```cpp
vector<int> bellmanFord(int V, vector<vector<int>> &edges, int S) {
	vector<int> result(V, 1e8);
	result[S] = 0;

	for(int count = 1; count<=V-1; count++) {
		for(auto &edge: edges) {
			int u = edge[0];
			int v = edge[1];
			int wt = edge[2];
			
			if(result[u] != 1e8 && result[u] + wt < result[v]) {
				result[v] = result[u] + wt;
			}
		}
	}
	
	// check for negative cycle
	for(auto &edge: edges) {
		int u = edge[0];
		int v = edge[1];
		int wt = edge[2];
		
		if(result[u] != 1e8 && result[u] + wt < result[v]) {
			return { -1 };
		}
	}
	return result;	
}
```

### Disjoint Set Union 
- Helps to:
	- Combine 2 given sets.     ======> `UNION`
	- Tell if 2 members belong to the same set or not. ========> `FIND`
	- 