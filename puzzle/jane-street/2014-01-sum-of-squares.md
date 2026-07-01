# Sum of Squares
  January 2014 : Puzzle

## Problem

The goal was to fill a 5×5 grid using digits from 0–9.
Each row formed a 5-digit number divisible by its row label (1–5), and each column formed a 5-digit number divisible by its column label (6–10).
Leading zeros were allowed.
The objective was to maximize the sum of all 25 digits in the grid.
A brute force solution would require checking (10^{25}) possible grids, which is impossible in practice.

---

## First Approach — Greedy Search (Score: 198)

My first approach was greedy. This was solved on pen by hands.
Since the goal was maximizing the digit sum, I tried placing larger digits first whenever possible i.e is placed 9 digit all over but here constraints not satisfied.
So accordingly i changes one by one digit where problems came like 99999 is not divisible by 2 so i replaced with sighlty smaller number 99998 and on for each rows and columns.
This produced decent solutions quickly, but it often got stuck because local choices hurt future divisibility constraints.
The algorithm did not properly account for interactions between rows and columns.
The best score achieved with this method was 198.
```text
 9 9 9 9 9
 9 9 9 9 8
 9 9 9 9 9
 9 9 9 9 6
 6 5 2 9 0
```

---

## Second Approach — Backtracking with Pruning (Score: 204)

The second version used recursive backtracking.
Instead of generating full grids blindly, rows were added one by one while checking constraints early.
I added pruning rules using divisibility properties:

* divisible by 10 → last digit must be 0
* divisible by 8 → last 3 digits divisible by 8
* divisible by 9 → digit sum divisible by 9

These checks removed large parts of the search tree immediately.
This approach improved both speed and solution quality, reaching a score of 203.

---

## Result
My solution: 204
```text
 9 9 9 9 9
 9 9 9 9 8
 9 7 8 9 9
 9 9 8 9 6
 6 9 8 9 0
```

Official optimal: 205
```text
 9 8 9 9 9
 9 9 9 9 8
 7 9 8 9 9
 9 9 8 9 6
 8 9 8 9 0
```

Status: Code finds 204 but runs indefinitely searching for better — pruning likely eliminates the 205 solution early. To investigate later.

---

## Key Insight

The biggest insight was that search order matters a lot.
Trying larger digits first made pruning dramatically more effective because good solutions appeared early.
Once a strong solution was known, upper-bound pruning eliminated most remaining branches.
Divisibility tricks also reduced the search space much more than expected.
The final solver worked because it combined mathematical constraints with intelligent search ordering.

---

## Code

```python
from itertools import product

best_sum = -1
best_grid = None

digits = range(9, -1, -1)

valid_rows = {}

for d in range(1, 6):

    rows = []

    for row in product(digits, repeat=5):

        num = int("".join(map(str, row)))

        if num % d == 0:
            rows.append(row)

    rows.sort(key=sum, reverse=True)

    valid_rows[d] = rows

print("Valid rows generated")

valid_rows[5] = [
    r for r in valid_rows[5]
    if r[4] == 0 and r[0] % 2 == 0
]

print("Row5 optimized")

def partial_check(grid):

    rows_done = len(grid)

    if rows_done == 5:

        last3 = (
            grid[2][2] * 100
            + grid[3][2] * 10
            + grid[4][2]
        )

        if last3 % 8 != 0:
            return False

    if rows_done == 5:

        s = sum(grid[i][3] for i in range(5))

        if s % 9 != 0:
            return False

    if rows_done == 5:

        if grid[4][4] != 0:
            return False

    return True

def final_check(grid):

    for col in range(5):

        num = int(
            "".join(
                str(grid[row][col])
                for row in range(5)
            )
        )

        divisor = col + 6

        if num % divisor != 0:
            return False

    return True

def backtrack(grid, row_id):

    global best_sum
    global best_grid

    if row_id == 5:

        if final_check(grid):

            total = sum(sum(r) for r in grid)

            if total > best_sum:

                best_sum = total
                best_grid = [r[:] for r in grid]

                print("\nNEW BEST =", best_sum)

                for row in best_grid:
                    print(row)

        return

    current_sum = sum(sum(r) for r in grid)

    remaining_rows = 5 - row_id

    max_possible = current_sum + remaining_rows * 5 * 9

    if max_possible <= best_sum:
        return

    for row in valid_rows[row_id + 1]:

        grid.append(row)

        if partial_check(grid):
            backtrack(grid, row_id + 1)

        grid.pop()

backtrack([], 0)

print("\n" + "=" * 60)

print("BEST SUM =", best_sum)

print("\nBEST GRID:\n")

for row in best_grid:
    print(*row)

digits_string = "".join(
    str(d)
    for row in best_grid
    for d in row
)

print("\nSubmission Answer:")
print(f"({best_sum},{digits_string})")

print("=" * 60)
```
