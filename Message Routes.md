
---
[Message Routes](lhttps://cses.fi/problemset/task/1667)
Topic: [[Graphs]]
tags: #dsa #graphs #bfs 
date: 23-06-2024-06-23

---
## Approach

Input:
5 3
1 2
1 3
4 5

Output:
1 2 2 1 2

## Code 

```cpp
void solve()

{
    int n, m;
    cin >> n >> m;
    vector<vector<int>> adj(n+1);
    
    for(int i=0; i<m; i++) {
        int temp1, temp2;
        cin >> temp1 >> temp2;
        adj[temp1].push_back(temp2);
        adj[temp2].push_back(temp1);
    }
    queue<int> q;
    vi vis(n+1), prev(n+1);
    vi path;

    q.push(1);
    vis[1] = 1;
    while(!q.empty()) {
        int node = q.front(); q.pop();
        for(auto i: adj[node]) {
            if(vis[i]) continue;
            vis[i] = vis[node] + 1;
            prev[i] = node;
            q.push(i);
        }
    }
    if(!vis[n]) {cout << "IMPOSSIBLE\n" ; return ;}
    int end = n;
    while(end != 1) {
        path.push_back(end);
        end = prev[end];
    }
    path.push_back(1);
    reverse(all(path));
    cout << path.size() << endl;
    for(auto x: path) cout << x << " ";
    cout << endl;
}
```

---
# 🦚 राधे राधे 🦚
---
