# River Crossing
## Problem
Four people must cross a bridge at night.

Crossing time:
```text
A = 10 min
B = 5 min
C = 2 min
D = 1 min
```
Rules:
* At most 2 people may cross at once.
* One torch is required.
* A pair moves at the slower person's speed.

Find the minimum total crossing time.

## Key Insight
The 10 min and 5 min people should cross together.

The fastest people should be used to shuttle the torch.

## Solution
Optimal sequnece:
```text
CD -> 2
D <- 1
AB -> 10
C <- 2
CD -> 2
```
Total Time:
```text
2 + 1 + 10 + 2 + 2 = 17
```

## Answer
Minimum time = 17 mins

## Technique
Use the fastest people as torch carrier and minimize the crosssing involving the slowest person.
