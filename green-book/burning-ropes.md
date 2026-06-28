# Burning Ropes

## Problem

You have two ropes.

* Each rope takes exactly **60 minutes** to burn.
* The ropes burn at an uneven rate.
* You can light either end of a rope.

Measure exactly **45 minutes**.

---

## Key Observation

Even though a rope burns unevenly, lighting **both ends** makes it burn in **half the remaining time**.

So a 60-minute rope burns out in:

```text
30 minutes
```

when both ends are lit.

---

## Step 1

### Action

At time:

```text
0 minutes
```

Light:

* Both ends of **Rope A**
* One end of **Rope B**

### Reasoning

* Rope A burns from both ends, so it finishes in **30 minutes**.
* Rope B has been burning from one end for **30 minutes**.

### Conclusion

After **30 minutes**:

```text
Rope A -> Completely burned
Rope B -> 30 minutes of burning time remaining
```

---

## Step 2

### Action

As soon as Rope A burns out, light the **other end** of Rope B.

### Reasoning

Rope B now burns from both ends.

Since it had **30 minutes** of burn time remaining, burning from both ends finishes it in:

```text
15 minutes
```

### Conclusion

Rope B burns out **15 minutes later**.

---

## Step 3

### Total Time

```text
30 + 15 = 45 minutes
```

---

## Answer

1. Light both ends of Rope A and one end of Rope B.
2. Wait until Rope A burns out (30 minutes).
3. Light the other end of Rope B.
4. Wait until Rope B burns out (15 minutes).

```text
Total time = 45 minutes
```

## Technique

**Key Observation / Invariant**

Lighting both ends halves the remaining burn time, regardless of how unevenly the rope burns.
