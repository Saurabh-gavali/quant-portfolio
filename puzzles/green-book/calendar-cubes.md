# Calendar Cubes
## Problem
You have two cubes with six faces each.

Place one digit on each face so that you can display every date from:
```text
01 to 31
```
using two cubes.(You may swap the positions of the cubes.)

---
## Key Observation
My first thought is to look for digits that must appear on **both** cubes.

Since the calendar contains:
```text
11
22
```
both cubes must contain:
```text
1
2
```
Also, to display single-digit dates as:

```text
01
02
...
09
```
I need a **0**.

To display all single-digit dates regardless of which cube is on the left or right, it's easiest to place:
```text
0
```
on both cubes.

So far I have:

| Cube 1 | 0 | 1 | 2 | ? | ? | ? |
|--------|---|---|---|---|---|---|
| Cube 2 | 0 | 1 | 2 | ? | ? | ? |

---
## Step 1

### Observation

The remaining digits are:

```text
3 4 5 6 7 8 9
```

But I only have:

```text
6
```
empty faces left.
### Reasoning
I need to fit **7 digits into 6 spaces**, so one digit must do double duty.

---
## Step 2
### Observation
A **6** can also be used as a **9** by simply turning the cube upside down.
### Reasoning
Since a calendar never needs **6** and **9** at the same time, one face can represent both digits.

Now I only need six remaining symbols.

---
## Step 3
### One valid arrangement
| Cube 1 | Cube 2 |
|---------|---------|
| 0 | 0 |
| 1 | 1 |
| 2 | 2 |
| 3 | 6 (or 9) |
| 4 | 7 |
| 5 | 8 |

Using the 6 upside down whenever a 9 is needed allows every date from **01** to **31** to be displayed.

---
## Answer
```text
Cube 1: 0 1 2 3 4 5
Cube 2: 0 1 2 6 7 8
```
where **6** is also used as **9**.

---
## Technique
**Constraint Elimination / Thinking Outside the Box**
Identify the mandatory digits first, then realize that **6** and **9** never appear together in a valid date, allowing one face to represent both.
