
---
[Building Teams](https://cses.fi/problemset/task/1668)
Topic: [[Graphs]]
tags: #dsa #graphs #dfs 
date: 23-06-2024-06-23

---
## Approach

- DFS 
- TEAM TOGGLING FOR EVERY CONSECUTIVE FRIENDS

## Code 

```cpp
int possible;

void dfs(int current_node, int prev_node, vector<vector<int>>& adj, vector<int>& vis, vector<int>& team) {
    for(auto x: adj[current_node]) {
        if(x != prev_node) {
            if(!vis[x]) {
                vis[x] = 1;
                team[x] = !team[current_node];
                dfs(x, current_node, adj, vis, team);
            }
            else {
                if(team[x] == team[current_node]){
                    possible = 0;
                }
            }
        }
    }
}

int32_t main()

{
    fastio()

    #ifndef ONLINE_JUDGE
        freopen("Error.txt","w",stderr);
    #endif
    //Radhe Radhe
    //The comeback is always stronger than the setback.
    int n, m;
    cin >> n >> m;
    vector<vector<int>> adj(n+1);
    for(int i=0; i<m; i++) {
        int temp1, temp2;
        cin >> temp1 >> temp2;
        adj[temp1].push_back(temp2);
        adj[temp2].push_back(temp1);
    }

    vector<int> vis(n+1);
    vector<int> team(n+1, 0);
    possible = 1;
    for(int i=1; i<=n; i++) {
        if(!vis[i]) {
            vis[i] = 1;
            dfs(i, 0, adj, vis, team);
        }
    }

    if(possible == 0) {cout << "IMPOSSIBLE";}
    else {
        for(int i=1; i<=n; i++) {
            if(team[i]==0){team[i] = 2;}
            cout << team[i] << " ";}
    }
    return 0;
}
```

---
# 🦚 राधे राधे 🦚
---
