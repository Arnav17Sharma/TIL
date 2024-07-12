
---
[01 Knapsack](https://www.geeksforgeeks.org/problems/0-1-knapsack-problem0945/1)
Topic: [[Dynamic Programming]]
tags: #dsa #dp 
date: 10-07-2024-07-10

---
### Recursive Code 

```cpp
int knapSack(int W, int wt[], int val[], int n) 
{
	if(n == 0 || W == 0) 
		return 0;
	if(wt[n-1] <= W) {
		return max(
			val[n-1] + knapSack(W-wt[n-1], wt, val, n-1),
			knapSack(W, wt, val, n-1)
			);
	}
	return knapSack(W, wt, val, n-1);
}
```

### Memoization

```cpp
int knapSackR(int W, int wt[], int val[], int n, vector<vector<int>> &dp) 
{
	if(n == 0 || W == 0) 
		return 0;
	if(dp[n][W] != -1) 
		return dp[n][W];
	if(wt[n-1] <= W) {
		dp[n][W] = max(
			val[n-1] + knapSackR(W-wt[n-1], wt, val, n-1, dp),
			knapSackR(W, wt, val, n-1, dp)
			);
		return dp[n][W];
	}
	dp[n][W] = knapSackR(W, wt, val, n-1, dp);
	return dp[n][W];
}
int knapSack(int W, int wt[], int val[], int n) 
{
	vector<vector<int>> dp(1002, vector<int>(1002, -1));
	return knapSackR(W, wt, val, n, dp);
}
```

### Top Down Approach

```cpp
int knapSack(int W, int wt[], int val[], int n) 
{ 
   int dp[n+1][W+1];
   for(int i=0;i<n+1;i++)
   {
	   dp[i][0]=0;
   }
   
	for(int j=0;j<W+1;j++)
   {
	   dp[0][j]=0;
   }
   
   for(int i=1;i<n+1;i++)
   {
	   for(int j=1;j<W+1;j++)
	   {
		   if(wt[i-1]<=j)
		   {
				dp[i][j]=max(val[i-1]+dp[i-1][j-wt[i-1]],dp[i-1][j]);
		   }
		   else
				dp[i][j]= dp[i-1][j];
	   }
   }
   return dp[n][W];
}
```


---
# 🦚 राधे राधे 🦚
---
