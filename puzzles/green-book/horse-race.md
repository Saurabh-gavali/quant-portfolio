# Horse Race
## Problem
There are **25 horses**, each with a different constant speed.
* At most **5 horses** can race at a time.
* No stopwatch is available; only the finishing order is known.
Find the **3 fastest horses** using the minimum number of races.
---
## Key Observation
My first thought is that every horse must race at least once.

Since only 5 horses can race at a time, I naturally divide them into:
```text
A: 1  2  3  4  5
B: 6  7  8  9 10
C:11 12 13 14 15
D:16 17 18 19 20
E:21 22 23 24 25
```
---
## Step 1
### Action
Race each group once.

This requires:
```text
5 races
```
Assume the results are:
```text
A: 1 > 2 > 3 > 4 > 5
B: 6 > 7 > 8 > 9 > 10
C:11 >12 >13 >14 >15
D:16 >17 >18 >19 >20
E:21 >22 >23 >24 >25
```
(Here ">" means faster.)
### Conclusion
Now I know the ranking **within each group**.
---
## Step 2
### Action
Race the winners of each group:
```text
1, 6, 11, 16, 21
```
Suppose the result is:
```text
1 > 6 > 11 > 16 > 21
```
This is the **6th race**.
### Conclusion
The groups are ranked:
```text
A > B > C > D > E
```
---
## Step 3
### Observation
Now I start eliminating horses.

Since:
```text
11 < 6 < 1
```
every horse behind **11** is slower than at least three horses.

Therefore:
```text
C: 12,13,14,15
D: 16,17,18,19,20
E: 21,22,23,24,25
```
cannot be in the top three.

Similarly,
```text
4,5
```
cannot be in the top three because they are slower than:
```text
1,2,3
```
Likewise,
```text
8,9,10
```
cannot be in the top three because they are slower than:
```text
6,7
```

### Remaining Candidates
Only these horses can still finish in the overall top three:

```text
1
2
3
6
7
11
```
Since horse **1** is already the fastest overall, only two top-three positions remain.

Therefore I only need to compare:
```text
2
3
6
7
11
```
---

## Step 4
### Action
Race:

```text
2, 3, 6, 7, 11
```
This is the **7th race**.

The first two horses in this race are the **2nd** and **3rd** fastest overall.
---

## Answer
```text
Minimum races = 7
```
## Technique
**Systematic Elimination**
Use early races to eliminate horses that cannot possibly finish in the top three, leaving only the necessary candidates for the final race.
