
---
Topic : [[Binary Trees]]
date : 21-07-2024
tags : #dsa 

---
### Traversals

- In order (Recursion)
```cpp
class Solution {
public:
    vector<int> ans;
    void solve(TreeNode* root, vector<int> &ans) {
        if(root == nullptr)
            return;
        solve(root->left, ans);
        ans.push_back(root->val);
        solve(root->right, ans);
    }
    vector<int> inorderTraversal(TreeNode* root) {
        solve(root, ans);
        return ans;
    }
};
```

- In order (Iterative)

```cpp

```

- Pre order (Recursion)
```cpp
class Solution {
public:
    vector<int> ans;
    void solve(TreeNode* root, vector<int> &ans) {
        if(root == nullptr)
            return;
        ans.push_back(root->val);
        solve(root->left, ans);
        solve(root->right, ans);
    }
    vector<int> preorderTraversal(TreeNode* root) {
        solve(root, ans);
        return ans;
    }
};
```

- Pre order (Iterative)
```cpp
class Solution {
public:
    vector<int> ans;
    vector<int> preorderTraversal(TreeNode* root) {
        stack<TreeNode*> st;
        if(root == nullptr)
            return ans;
        st.push(root);
        while(!st.empty()) {
            TreeNode *node = st.top();
            ans.push_back(node->val);
            st.pop();
            if(node->right) st.push(node->right);
            if(node->left) st.push(node->left);
        }
        return ans;
    }
};
```

- Post order
```cpp
class Solution {
public:
    vector<int> ans;
    void solve(TreeNode* root, vector<int> &ans) {
        if(root == nullptr)
            return;
        solve(root->left, ans);
        solve(root->right, ans);
        ans.push_back(root->val);
    }
    
    vector<int> postorderTraversal(TreeNode* root) {
        solve(root, ans);
        return ans;
    }
};
```

- Level order 
```cpp
class Solution {
public:
    vector<vector<int>> levelOrder(TreeNode* root) {
        vector<vector<int>> ans;
        if(root == nullptr)
            return ans;
        queue<TreeNode*> q;
        q.push(root);
        while(!q.empty()) {
            int size = q.size();
            vector<int> level;
            for(int i=0; i<size; i++) {
                TreeNode *node = q.front();
                q.pop();
                if(node->left) q.push(node->left);
                if(node->right) q.push(node->right);
                level.push_back(node->val);
            }
            ans.push_back(level);
        }
        return ans;
    }
};
```

-  