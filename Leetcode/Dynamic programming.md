# Dynamic programming notes
Dynamic programming is an important topic in basic algorithms. It solves problems by combining the solutions to sub-problems. DP applies when the subproblems overlap - that is , when subproblems share sub-subproblems.

When developing DP, we basically follow a sequence of four steps:

 - Characterize the structure of an optimal solution
 - Recursively define the value of an optimal solution
 - Compute the value of an optimal solution, typically in a bottom-up fashion
 - Construct an optimal solution from computed information
 
 The key of DP is to find the structure of optimal solution.

*************************************************
## 64 Minimum Path Sum
Given a  _m_  x  _n_  grid filled with non-negative numbers, find a path from top left to bottom right which  _minimizes_  the sum of all numbers along its path.

    **Note:**  You can only move either down or right at any point in time.

	**Example:**

	**Input:**
	[
	  [1,3,1],
	  [1,5,1],
	  [4,2,1]
	]
	**Output:** 7
	**Explanation:** Because the path 1→3→1→1→1 minimizes the sum.





<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwMDQxODIxMzAsNzEzNzIwMTIzLC0yMD
c1OTA1OTkwXX0=
-->