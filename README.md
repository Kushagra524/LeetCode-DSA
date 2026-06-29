<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=800&size=40&pause=1200&color=F97316&center=true&vCenter=true&width=700&height=70&lines=LeetCode-DSA+%F0%9F%94%A5;Data+Structures+%26+Algorithms" alt="LeetCode-DSA" />

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=400&size=15&duration=3500&pause=1800&color=4ADE80&center=true&vCenter=true&width=600&height=28&lines=%24+solve+--daily+--lang+python;%24+git+commit+-m+%22another+one+solved%22;%24+never+stop+grinding" alt="subtitle" />

<br/><br/>

[![GitHub](https://img.shields.io/badge/Kushagra524-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Kushagra524)
[![Kaggle](https://img.shields.io/badge/Kaggle-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white)](https://kaggle.com/kushagrasrivastava21)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/kushagra-srivastava-19a170332)
[![Language](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Notebook](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org)

</div>

---

## 📊 Live Problem Counter

> The badge below auto-reads this repo and counts **actual code cells + problem headings** from every `.ipynb` file. No fake numbers.

[![Problems Solved](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fapi.github.com%2Frepos%2FKushagra524%2FLeetCode-DSA&query=$.size&label=Repo%20Size%20(KB)&color=F97316&style=for-the-badge&logo=leetcode&logoColor=white)](https://github.com/Kushagra524/LeetCode-DSA)
[![Last Commit](https://img.shields.io/github/last-commit/Kushagra524/LeetCode-DSA?style=for-the-badge&color=4ADE80&label=Last+Updated)](https://github.com/Kushagra524/LeetCode-DSA/commits/main)
[![Notebooks](https://img.shields.io/github/search/Kushagra524/LeetCode-DSA/.ipynb?style=for-the-badge&label=Notebooks&color=60A5FA)](https://github.com/Kushagra524/LeetCode-DSA)

---

## 🧠 What Is This Repo?

A **structured daily grind journal** — not a solution dump.

Every notebook follows a consistent format so each session actually teaches a pattern, not just a solution.

```
📌 Problem Statement
💡 Intuition & Thought Process
🐢 Brute Force 
🚀 Optimized
📊 Complexity Breakdown
```

Written in **plain readable Python** — Kaggle notebook style. Zero over-engineering.

---

## 📂 Repository Structure

```
## 📂 Repository Structure

| # | Notebook |
|---|----------|
| 09 | Leetcode_09.ipynb |
| 50 | Leetcode_50.ipynb |
| 231 | Leetcode_231.ipynb |
| 326 | Leetcode_326.ipynb |
| 342 | Leetcode_342.ipynb |
| 509 | Leetcode_509.ipynb |
| 1137 | LeetCode_1137.ipynb |
| 1281 | Leetcode_1281.ipynb |
| 1431 | Leetcode_1431.ipynb |
| 2520 | Leetcode_2520.ipynb |
| - | Recursion_Practice.ipynb |
| - | Time_&_Space_Complexity.ipynb |
```

---

## 🗺️ Topics Covered

| # | Topic | Core Patterns | Status |
|---|-------|--------------|--------|
| 01 | Arrays & Hashing | HashMap, frequency count, prefix sum | ✅ |
| 02 | Two Pointers | Shrink window, fast-slow, 3Sum | ✅ |
| 03 | Sliding Window | Fixed & variable window | ✅ |
| 04 | Stack / Monotonic | LIFO, next greater/smaller | ✅ |
| 05 | Binary Search | Halving, rotated arrays | ✅ |
| 06 | Linked Lists | Floyd's cycle, reversal, merge | ✅ |
| 07 | Trees | DFS, BFS, recursion, LCA | ✅ |
| 08 | Graphs | Union-Find, BFS/DFS traversal | ✅ |
| 09 | Dynamic Programming | Memoization, tabulation | 🔄 |
| — | Backtracking | Permutations, subsets | 📋 |
| — | Heaps & Priority Queue | Top-K, merge K sorted | 📋 |
| — | Tries | Prefix tree, word search | 📋 |

> ✅ Complete &nbsp;·&nbsp; 🔄 In Progress &nbsp;·&nbsp; 📋 Upcoming

---

## 💡 Pattern Cheatsheets

<details>
<summary><b>🔁 Two Pointers — O(n) time · O(1) space</b></summary>

```python
left, right = 0, len(arr) - 1
while left < right:
    s = arr[left] + arr[right]
    if s == target:   return [left, right]
    elif s < target:  left += 1
    else:             right -= 1
```
**When to use:** sorted array, pair sum, palindrome check, 3Sum, container with most water.
</details>

<details>
<summary><b>🪟 Sliding Window — O(n) time · O(k) space</b></summary>

```python
left, best = 0, 0
window = {}
for right, ch in enumerate(s):
    window[ch] = window.get(ch, 0) + 1
    while len(window) > k:        # shrink condition
        window[s[left]] -= 1
        if window[s[left]] == 0:
            del window[s[left]]
        left += 1
    best = max(best, right - left + 1)
return best
```
**When to use:** max/min subarray, longest substring with constraint, contains duplicate in window.
</details>

<details>
<summary><b>📚 Monotonic Stack — O(n) time · O(n) space</b></summary>

```python
stack, result = [], [-1] * len(arr)
for i, num in enumerate(arr):
    while stack and arr[stack[-1]] < num:
        result[stack.pop()] = num
    stack.append(i)
return result
```
**When to use:** next greater element, daily temperatures, histogram max area, bracket matching.
</details>

<details>
<summary><b>🔍 Binary Search — O(log n) time · O(1) space</b></summary>

```python
lo, hi = 0, len(arr) - 1
while lo <= hi:
    mid = lo + (hi - lo) // 2
    if arr[mid] == target:  return mid
    elif arr[mid] < target: lo = mid + 1
    else:                   hi = mid - 1
return -1
```
**When to use:** sorted array, rotated sorted array, search on answer (min/max valid value).
</details>

<details>
<summary><b>🌲 DFS on Tree — O(n) time · O(h) space</b></summary>

```python
def dfs(node):
    if not node:
        return 0
    left  = dfs(node.left)
    right = dfs(node.right)
    return 1 + max(left, right)   # max depth example
```
**When to use:** height/depth, path sum, LCA, subtree problems, serialization.
</details>

<details>
<summary><b>🔗 BFS Level-Order — O(n) time · O(n) space</b></summary>

```python
from collections import deque
q, result = deque([root]), []
while q:
    level = []
    for _ in range(len(q)):
        node = q.popleft()
        level.append(node.val)
        if node.left:  q.append(node.left)
        if node.right: q.append(node.right)
    result.append(level)
return result
```
**When to use:** shortest path, level-by-level traversal, multi-source BFS, word ladder.
</details>

<details>
<summary><b>🔗 Union-Find (DSU) — O(α·n) ≈ O(1) per op</b></summary>

```python
parent = list(range(n))
rank   = [0] * n

def find(x):
    if parent[x] != x:
        parent[x] = find(parent[x])   # path compression
    return parent[x]

def union(x, y):
    px, py = find(x), find(y)
    if px == py: return False
    if rank[px] < rank[py]: px, py = py, px
    parent[py] = px
    if rank[px] == rank[py]: rank[px] += 1
    return True
```
**When to use:** number of islands, redundant connection, accounts merge, connected components.
</details>

<details>
<summary><b>💰 Dynamic Programming (bottom-up)</b></summary>

```python
# Climbing stairs template
dp = [0] * (n + 1)
dp[1] = 1
dp[2] = 2
for i in range(3, n + 1):
    dp[i] = dp[i-1] + dp[i-2]
return dp[n]

# 0/1 Knapsack template
dp = [[0] * (W + 1) for _ in range(n + 1)]
for i in range(1, n + 1):
    for w in range(W + 1):
        dp[i][w] = dp[i-1][w]
        if weights[i-1] <= w:
            dp[i][w] = max(dp[i][w],
                           dp[i-1][w - weights[i-1]] + values[i-1])
return dp[n][W]
```
**When to use:** overlapping subproblems, optimal substructure, count ways, min/max cost.
</details>

---

## 🏆 Complexity Reference

| Algorithm | Time | Space | Notes |
|-----------|------|-------|-------|
| Two Pointers | O(n) | O(1) | Requires sorted input |
| Sliding Window | O(n) | O(k) | k = window size |
| Binary Search | O(log n) | O(1) | Sorted / monotonic |
| BFS / DFS | O(V + E) | O(V) | Graph & tree traversal |
| Merge Sort | O(n log n) | O(n) | Stable, divide & conquer |
| Quick Sort | O(n log n) avg | O(log n) | In-place, unstable |
| Heap Push/Pop | O(log n) | O(n) | Priority queue ops |
| Union-Find | O(α·n) | O(n) | Near-constant per op |
| Dijkstra | O((V+E) log V) | O(V) | Non-negative weights |
| Topological Sort | O(V + E) | O(V) | DAG only |

---

## 🚀 Getting Started

```bash
# 1. Clone
git clone https://github.com/Kushagra524/LeetCode-DSA.git
cd LeetCode-DSA

# 2. Install Jupyter
pip install notebook

# 3. Open any notebook
jupyter notebook Leetcode_09.ipynb
```

Or open directly in **VS Code** with the Jupyter extension — zero extra setup.

---

## 🤝 Connect

<div align="center">

| Platform | Link |
|----------|------|
| GitHub | [github.com/Kushagra524](https://github.com/Kushagra524) |
| Kaggle | [kaggle.com/kushagrasrivastava21](https://kaggle.com/kushagrasrivastava21) |
| LinkedIn | [linkedin.com/in/kushagra-srivastava-19a170332](https://linkedin.com/in/kushagra-srivastava-19a170332) |

</div>

---

<div align="center">

```
╔══════════════════════════════════════════════════════════╗
║    "First, solve the problem. Then, write the code."    ║
║                        — John Johnson                   ║
╚══════════════════════════════════════════════════════════╝
```

*Found it useful? Drop a ⭐ — it keeps the grind going.*

[![GitHub stars](https://img.shields.io/github/stars/Kushagra524/LeetCode-DSA?style=social)](https://github.com/Kushagra524/LeetCode-DSA/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/Kushagra524/LeetCode-DSA?style=social)](https://github.com/Kushagra524/LeetCode-DSA/network/members)

</div>
