
---
Topic : [[Graphs]]
date : 09-07-2024
tags : #dsa #toposort #kahn 

---
### **Topological Sorting** 
- It is a linear ordering of vertices such that if there is an edge `u -> v` then u appears `before` v in the ordering. 
- Can only occur in DAG (Directed Acyclic Graph) . 

#### **DFS Approach**

```cpp
    private:
    void dfs(int node, vector<int> &vis, stack<int> &st, vector<int> adj[]) {
        vis[node] = 1;
        for(auto x: adj[node]) {
            if(!vis[x]) {
                dfs(x, vis, st, adj);
            }
        }
        st.push(node);
    }
	public:
	vector<int> topoSort(int V, vector<int> adj[]) 
	{
	    stack<int> st;
	    vector<int> vis(V, 0);
	    for(int i=0; i<V; i++) {
	        if(!vis[i]) {
	            dfs(i, vis, st, adj);
	        }
	    }
	    vector<int> ans;
	    while(!st.empty()) {
	        int val = st.top();
	        ans.push_back(val);
	        st.pop();
	    }
	    return ans;

```


#### **BFS Approach (Kahn's Algorithm)**

```cpp
	vector<int> topoSort(int V, vector<int> adj[]) 
	{
	    vector<int> indegree(V);
	    for(int i=0; i<V; i++) {
	        for(auto x: adj[i])
	            indegree[x]++;
	    }
	    queue<int> q;
	    for(int i=0; i<V; i++) {
	        if(indegree[i]==0) 
	            q.push(i);
	    }
	    vector<int> ans;
	    while(!q.empty()) {
	        int node = q.front();
	        q.pop();
	        ans.push_back(node);
	        for(auto x: adj[node]) {
	            indegree[x]--;
	            if(indegree[x] == 0) 
	                q.push(x);
	        }
	    }
	    return ans;
	}
```


#### Questions 
- [[Cycle Detection in Directed Graph (BFS)]]
-  [[Course Schedule I]]
- [[Course Schedule II]]
- 