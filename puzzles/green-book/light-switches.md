# Light Switches
## Problem
There is one light bulb inside a room and four switches outside.

- Only one switch controls the bulb.
- All switches are initially OFF.
- You may flip the switches as many times as you like before entering the room.

How many times do you need to enter the room to determine which switch controls the bulb?

---
## Key Observation
My first thought is that simply checking whether the light is **ON** or **OFF** is not enough.

That only gives me:
```text
2 possibilities
```
But I need to distinguish between:
```text
4 switches
```
So I need another piece of information.

A light bulb also tells me whether it is:
```text
Hot
or
Cold
```
Now I have four possible states:
```text
ON & Hot
ON & Cold
OFF & Hot
OFF & Cold
```

which is enough to identify all four switches.

---
## Step 1
### Observation
I create four different bulb states before entering the room.
### Action
1. Turn **Switch 1 ON**.
2. Turn **Switch 2 ON**.
3. Wait a few minutes.
4. Turn **Switch 2 OFF**.
5. Turn **Switch 3 ON**.
6. Leave **Switch 4 OFF**.

Now enter the room exactly once.

---
## Step 2
### Observation

Check two things:

- Is the bulb **ON** or **OFF**?
- Is the bulb **HOT** or **COLD**?

### Reasoning
There are four possible outcomes.

| Bulb State | Controlling Switch |
|------------|--------------------|
| ON & Hot | Switch 1 |
| OFF & Hot | Switch 2 |
| ON & Cold | Switch 3 |
| OFF & Cold | Switch 4 |

Each switch produces a unique outcome.

---
## Answer
You only need to enter the room:
```text
1 time
```

---
## Technique
**State Encoding / Information Theory**

Use two independent observations—**light (ON/OFF)** and **temperature (HOT/COLD)**—to create four unique states, 
allowing you to identify one of four switches with a single visit.
