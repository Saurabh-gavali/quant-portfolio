# Tigers and Sheep
## Problem
100 tigers and 1 sheeep are on island.
* Tigers can eat grass but prefer sheep.
* A tiger that eats the sheep becomes sheep.
* All tigers are perfectly rational and want to survive.
Will this sheep be eaten?

## Key Insight
Use backward induction.
Instead of analyzing 100 tigers directly , staret with smaller cases and build a pattern.

## Solution
### Case 1: 1 tiger
The tiger eats the sheep and survives.
```text
1 tiger -> sheep eaten.
```
### Case 2: 2 tigers
If either tiger eats the sheep, it becomes sheep and is immediately eaten by the other tiger.

So neither tiger eats.

```text
2 tigers -> sheep survives.
```

### Case 3: 3 tigers
If the tiger east the sheep and turned into new sheep. Then there 2 tigers and 1 sheep left.

From Case 2, we kno wthat resulting sheep wont survives.

Therefore a tiger will eats the sheep.

```text
3 tigers -> sheep eaten.
```

### Case 4: 4 tigers
If a tiger eats the sheep, there will be 3 tigers left.

From Case 3, the resulting sheep will be eaten.

Therefore no tiger eats sheep.

```text
4 tigers -> sheep survives.
```

### Pattern:
Odd number of tigers -> Sheep eaten.

Even number of tigers -> Sheep survives.

## Answer
Since 100 tigers is even the Sheep survives.

## Technique
Backward Induction - solve the smaller cases first and extend the pattern.
