# The Sock Drawer
## Problem
A drawer has red and black socks. Probability of 
pulling 2 red socks = 1/2.
- Find minimum total socks
- Minimum total where black socks count is even.

## Approach
Let n = total socks, r = red socks.
Set up probability equation and solve.

## Solution

### **Part 1:**
```text
P(both red) = r(r-1) / n(n-1) = 1/2

=>  2r(r-1) = n(n-1)
```
Testing values: 
```text
r=3, n=4
```
satisfies this.

**Minimum n = 4.**

---
### **Part 2:**
Need n-r to be even.

Next solution: 
```text
r=15, n=21, black=6 (even).
```
**Minimum n = 21.**

## Code
```python
for n in range(2, 100):
    for r in range(1, n):
        if 2*r*(r-1) == n*(n-1):
            black = n - r
            print(f"n={n}, r={r}, black={black}, even={black%2==0}")
```

## Key Technique
Set up equation from probability condition.

Reduces to finding integer solutions — systematic 
search confirms minimum values.
