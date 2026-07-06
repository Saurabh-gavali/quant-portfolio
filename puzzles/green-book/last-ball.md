# Last Ball
## Problem
A bag initially contains:
```text
20 Blue balls
14 Red balls
```
At each step:
- Remove any two balls.
- If both balls are the same color, add one **Blue** ball.
- If the balls are different colors, add one **Red** ball.

Repeat until only one ball remains.

What is the color of the last ball?

What if the bag initially contains:
```text
20 Blue balls
13 Red balls
```

---
## Key Observation
My first thought is to track something that never changes.

Instead of tracking both colors, I'll track the **parity (odd or even)** of the number of red balls.

If the parity never changes, then I can determine the last ball immediately.

---
## Step 1
### Observation
Let:
```text
(B, R)
```
represent the number of blue and red balls.

Now consider every possible move.
### Case 1
Both balls are blue.
```text
(B, R)
→
(B - 1, R)
```
The number of red balls does not change.

---
### Case 2
Both balls are red.

```text
(B, R)
→
(B + 1, R - 2)
```

The number of red balls decreases by:

```text
2
```
so its parity does not change.

---
### Case 3
One blue and one red.
```text
(B, R)
→
(B - 1, R)
```

The number of red balls remains the same.

---
## Step 2
### Observation
In every possible move, the number of red balls either:
```text
Stays the same
or
Decreases by 2
```
### Reasoning
Therefore, the **parity** of the number of red balls never changes.

If we start with:
```text
14 red balls
```
the number of red balls is always **even**.

If we start with:
```text
13 red balls
```

the number of red balls is always **odd**.

---
## Step 3
### Observation
Each move removes one ball overall.

Eventually, only one ball remains.
### Reasoning
If the final ball is:
- **Blue**, then the number of red balls is:
```text
0
```
which is **even**.

If the final ball is:
- **Red**, then the number of red balls is:
```text
1
```
which is **odd**.

Since the parity never changes, the color of the last ball is determined by the initial parity of red balls.

---
## Answer
Starting with:
```text
20 Blue
14 Red
```
the last ball is:
```text
Blue
```

Starting with:
```text
20 Blue
13 Red
```
the last ball is:

```text
Red
```

---
## Technique
**Invariant (Parity)**

Instead of tracking every move, track the **parity of the number of red balls**.
Since it never changes, it completely determines the color of the last remaining ball.
