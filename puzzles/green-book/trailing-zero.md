# Trailing Zeros
## Problem
Find the number of trailing zeros in:
```text
100!
```
---
## Key Observation
My first thought is that every trailing zero comes from a factor of:
```text
10 = 2 × 5
```
In a factorial, factors of **2** are much more common than factors of **5**. So I only need to count the number of factors of **5**.
---
## Step 1
### Observation
I first count how many numbers contribute at least one factor of **5**.
### Reasoning
The multiples of 5 are:
```text
5, 10, 15, ..., 100
```
Count:
```text
⌊100/5⌋ = 20
```
### Conclusion
```text
20 factors of 5
```
---
## Step 2
### Observation
Some numbers contribute **more than one** factor of 5.
### Reasoning
The multiples of 25 are:
```text
25, 50, 75, 100
```
Each contributes one extra factor of 5.
Count:
```text
⌊100/25⌋ = 4
```
### Conclusion
```text
4 additional factors of 5
```
---
## Step 3
### Observation
I check if any numbers contribute a third factor of 5.
### Reasoning
The next power is:
```text
5³ = 125
```
Since:
```text
125 > 100
```
there are no additional factors.
### Conclusion
```text
0 additional factors
```
---
## Total Factors of 5
```text
20 + 4 + 0 = 24
```
Since every factor of **5** pairs with a factor of **2**, the number of trailing zeros is:
```text
24
```
---
## General Formula
For any factorial:
```text
Trailing Zeros(n!) =
⌊n/5⌋ + ⌊n/25⌋ + ⌊n/125⌋ + ...
```
This is **Legendre's Formula** for counting the exponent of 5 in (n!).
---
## Answer
```text
100! has 24 trailing zeros.
```

## Technique

**Prime Factor Counting (Legendre's Formula)**
