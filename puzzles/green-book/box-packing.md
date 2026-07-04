# Box Packing
## Problem
Can you pack **53 bricks** of dimensions:
```text
1 × 1 × 4
```
into a
```text
6 × 6 × 6
```
box?
---
## Key Observation
My first thought is to compare the total volume.

The box has volume:
```text
6 × 6 × 6 = 216
```
The 53 bricks have volume:
```text
53 × (1 × 1 × 4) = 212
```
Since:
```text
212 < 216
```
volume alone does **not** prove whether packing is possible.

So I need another argument.
---

## Step 1
### Observation
Divide the box into:
```text
2 × 2 × 2
```
small cubes.

Since:

```text
6 = 3 × 2
```
the box contains:
```text
3 × 3 × 3 = 27
```
small cubes.

---
## Step 2
### Observation
Color the small cubes like a 3D chessboard.

This gives:
```text
14 black cubes
13 white cubes
```
### Reasoning
Each brick has dimensions:
```text
1 × 1 × 4
```
A brick always passes through **two adjacent 2×2×2 cubes**.

Because adjacent cubes have opposite colors, each brick occupies:
```text
1 black cube
1 white cube
```
---
## Step 3
### Observation
Each:
```text
2 × 2 × 2
```
cube has volume:
```text
8
```
A brick has volume:
```text
4
```
### Reasoning
Therefore, each cube can contain at most:
```text
2 half-bricks
```
or equivalently,
```text
2 × (1×1×4)/2
= 1 full brick
```
Since each brick occupies one black cube and one white cube, each colored cube can contribute to at most:
```text
2 half-bricks
= 1 full brick
```
Across all cubes of one color:
```text
13 cubes × 2 half-bricks
= 26 half-bricks
= 52 half-bricks
= 52 × (1×1×4)
```
Equivalently, the 13 cubes of one color can accommodate **at most 52 brick-halves**, which corresponds to **52 complete bricks** when paired with the opposite color.

The 53rd brick would require another half-brick in a color class that has no remaining capacity.
### Conclusion
A maximum of:
```text
52 bricks
```
can be packed.
---
## Answer
```text
No
```
It is impossible to pack **53 bricks** of dimensions **1×1×4** into a **6×6×6** box.

---

## Technique

**Coloring Argument / Invariant**

Transform the 3D packing problem into a coloring problem. Every brick connects one black cube and one white cube, 
and the imbalance between the two color classes limits the maximum number of bricks that can be packed.
