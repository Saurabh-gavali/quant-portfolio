# Screwy Pirates

## Problem

Five pirates discover 100 gold coins and must decide how to distribute them.

The pirates are ranked by seniority:

```text
P5 > P4 > P3 > P2 > P1
```

The most senior surviving pirate proposes a distribution.

All surviving pirates then vote.

Rules:

1. A proposal passes if it receives at least 50% of the votes.
2. If the proposal fails, the proposer is thrown overboard.
3. Pirates are perfectly rational.
4. Pirates care about:

   * Staying alive first.
   * Maximizing the number of coins second.

Find the distribution proposed by P5.

---

## Key Insight

This is a backward induction problem.

Instead of starting with five pirates, start with the smallest possible game and work upward.

At each stage, determine:

* What happens if the current proposer dies.
* Which pirates can be bribed most cheaply.
* The minimum number of votes required for survival.

---

## Solution

### Case 1: One Pirate (P1)

Only P1 remains.

He keeps all 100 coins.

```text
P1: 100
```

---

### Case 2: Two Pirates (P2, P1)

A proposal passes with 50% of the votes.

P2 votes for his own proposal.

```text
1 / 2 = 50%
```

Therefore P2 already has enough votes.

He keeps everything.

```text
P2: 100
P1: 0
```

---

### Case 3: Three Pirates (P3, P2, P1)

If P3 dies, we know the outcome:

```text
P2: 100
P1: 0
```

P3 needs:

```text
2 votes out of 3
```

He already has his own vote.

Which pirate is cheapest to bribe?

* P2 gets 100 if P3 dies.
* P1 gets 0 if P3 dies.

So P1 can be bought with 1 coin.

```text
P3: 99
P2: 0
P1: 1
```

Votes:

```text
P3, P1
```

Proposal passes.

---

### Case 4: Four Pirates (P4, P3, P2, P1)

If P4 dies, outcome is:

```text
P3: 99
P2: 0
P1: 1
```

P4 needs:

```text
2 votes out of 4
```

His own vote plus one additional vote.

Cheapest pirate:

* P2 receives 0 if P4 dies.

Give P2 one coin.

```text
P4: 99
P3: 0
P2: 1
P1: 0
```

Votes:

```text
P4, P2
```

Proposal passes.

---

### Case 5: Five Pirates (P5, P4, P3, P2, P1)

If P5 dies, outcome is:

```text
P4: 99
P3: 0
P2: 1
P1: 0
```

P5 needs:

```text
3 votes out of 5
```

His own vote plus two additional votes.

Find the cheapest pirates to bribe.

If P5 dies:

| Pirate | Coins |
| ------ | ----- |
| P4     | 99    |
| P3     | 0     |
| P2     | 1     |
| P1     | 0     |

The cheapest pirates are:

```text
P3 (0 coins)
P1 (0 coins)
```

Give each one more coin than they would otherwise receive.

```text
P3 = 1
P1 = 1
```

Final proposal:

```text
P5: 98
P4: 0
P3: 1
P2: 0
P1: 1
```

Votes:

```text
P5, P3, P1
```

Proposal passes.

---

## Answer

```text
98 - 0 - 1 - 0 - 1
```

or equivalently

```text
P5: 98
P4: 0
P3: 1
P2: 0
P1: 1
```

---

## Technique Used

### Backward Induction

1. Solve the smallest game first.
2. Assume all pirates know future outcomes.
3. Work backward from fewer pirates to more pirates.
4. Bribe the minimum number of pirates needed for survival.
5. Always choose the cheapest votes.

