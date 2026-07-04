# Door to Offer
## Problem
You are standing in front of two doors.

- One door leads to your **job offer**.
- The other leads to the **exit**.

Each door has one guard.

- One guard always tells the truth.
- The other always lies.

You may ask **only one yes/no question** to one guard.

How can you guarantee choosing the correct door?

---
## Key Observation
My first thought is that asking a guard directly:
```text
"Does your door lead to the job offer?"
```
doesn't help.

If I happen to ask the liar, I'll get the wrong answer.

So I need a question that works **regardless of which guard I ask**.

---
## Step 1
### Observation
I involve **both guards** in the same question.

Ask either guard:
> **"Would the other guard say that you are guarding the door to the job offer?"**
### Reasoning
There are two possible scenarios.
#### Scenario 1
- Truth teller guards the **job offer**.
- Liar guards the **exit**.

If I ask the **truth teller**:

- The liar would say **No**.
- So the truth teller answers **No**.

If I ask the **liar**:

- The truth teller would say **Yes**.
- The liar lies and answers **No**.

Both guards answer:
```text
No
```

---
#### Scenario 2
- Truth teller guards the **exit**.
- Liar guards the **job offer**.

If I ask the **truth teller**:

- The liar would say **Yes**.
- So the truth teller answers **Yes**.

If I ask the **liar**:

- The truth teller would say **No**.
- The liar lies and answers **Yes**.

Both guards answer:
```text
Yes
```

---
## Step 2
### Conclusion
If the answer is:
```text
No
```
choose **the door that guard is standing in front of**.

If the answer is:
```text
Yes
```
choose **the other door**.

This works regardless of which guard you ask.

---
## Answer
Ask either guard:
> **"Would the other guard say that you are guarding the door to the job offer?"**

- **Yes → Choose the other door.**
- **No → Choose this guard's door.**

---
## Technique
**Case Analysis / Logical Reasoning**
Construct a question that forces both the truth teller and the liar to produce the same response.
This removes the uncertainty about which guard you are speaking to.
