# Birthday Problem
## Problem
Possible birthdays:

| Month | Days |
|-------|-------|
| March | 4, 7, 8 |
| June | 4, 7 |
| September | 1, 5 |
| December | 1, 2, 8 |

The boss tells:

* You only the month.
* Your colleague(C) only the day.

Then the following coversation happens:


**You**: " I don't know the birthday, and i am sure C doesn't know it either."

**C**: "I didn't know before, but now i know."

**You**: "Now I know it too."

Find the birthday.

## Key Observation

Each statement gives new information.

After every statement, remove the dates that are no loger possible.

## Step 1
### Statement
You say:

> "I don't know the birthday, and I'm sure that C doesn't know it either."

### Reasoning

C knows only the day.

If C's day were:
```text
2 -> Dec 2

7 -> Jun 7
```
C would know the birthday immediatley beacause those days appear onbly once. 

Since you are certain C does not know, the month cannot be **June** or **December**.


### Conclusion

The birthday must be in:

March or September

### Remaning Dates
```text
Mar 4
Mar 5
Mar 8
Sep 1
Sep 5
```

## Step 2
### Statement
C says:
> "I don't know before, but now i know"
### Reasoning
After step 1, c knows the month is either **March** or **September**.

If C's day were:
5

there would still be two possibilities:
```text
Mar 5
Sep 5
```
So C still would not know the birthday.

Therefore C's day cannot be 5.
### Conclusion
Remove all dates with day 5.
### Remaning dates
```text
Mar 4
Mar 8
Sep 1
```

## Step 3
### Statement
You say:
> "Now i know it too."
### Reasoning
You know the month.

If your month were:
```text
March
```
you still have two choices:
```text
Mar 4
Mar 8
```
So you still would not know the birthday.

Therefore your month cannot be March.
### Conclusion
The month must be September.
## Remaining date
Sep 1

## Answer
```text
September 1
```
## Technique
**Logical Elimination(Epistemic Reasoning)**
Use each statement to remove impossible dates until only one poossibility remains.


































