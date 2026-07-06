# Quant Salary
## Problem
Eight quants want to calculate the **average salary** of the group.

However, no one wants to reveal their own salary to anyone else.

Can they compute the average salary while keeping every individual's salary private?

---
## Key Observation
My first thought is that if everyone simply announces their salary, computing the average is easy—but privacy is lost.

So I need a way to compute the **total salary** without revealing any individual's salary.

A random number can hide the first person's salary while still allowing the final total to be recovered.

---
## Step 1
### Observation

The first quant chooses a secret random number:
```text
R
```
Only the first quant knows this value.
### Action
The first quant computes:
```text
Salary1 + R
```
and passes the result to the second quant.
### Conclusion
The second quant cannot determine the first quant's salary because the random number is unknown.

---
## Step 2
### Observation
Each remaining quant repeats the same process.

### Reasoning
The second quant adds their salary and passes the result to the third quant.

The third quant adds their salary and passes it to the fourth quant.

This continues until the eighth quant.

At the end, the eighth quant sends the final value back to the first quant.

The final value is:
```text
Salary1 + Salary2 + ... + Salary8 + R
```
### Conclusion
The total salary is hidden by the random number.

---
## Step 3
### Observation
Only the first quant knows:
```text
R
```
### Reasoning
The first quant subtracts the random number:
```text
(Salary1 + ... + Salary8 + R) − R
```
to obtain the true total salary.

The average is then:
```text
Total Salary / 8
```
The first quant announces only the average.
### Conclusion
Everyone learns the average salary without learning anyone else's individual salary.

---
## Answer
1. The first quant adds a secret random number to their salary.
2. Each quant adds their own salary and passes the running total to the next person.
3. The final total is returned to the first quant.
4. The first quant removes the random number and divides by 8.
5. Only the average is announced.

---
## Technique
**Secure Aggregation / Random Masking**

Hide the running total using a secret random number. 
The random mask protects individual salaries while still allowing the true total—and therefore the average—to be recovered.
