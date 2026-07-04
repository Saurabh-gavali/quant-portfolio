# Message Delivery
## Problem
You need to send a document to your colleague using an insecure messenger service.

The document is placed inside a locked box.

- If the box is **unlocked** during delivery, everything inside is stolen.
- You and your colleague each have your own padlock.
- Each padlock can only be opened by its owner's key.

How can you securely send the document?

---

## Key Observation
My first thought is that I can simply lock the box before sending it.

However, my colleague cannot open it because only I have the key.

So the challenge is to let my colleague eventually open the box **without ever leaving it unlocked during transit**.

---
## Step 1
### Observation
I place the document inside the box and lock it with **my padlock**.

Then I send the locked box to my colleague.

### Reasoning
The document is secure during delivery.

However, my colleague cannot open the box because they do not have my key.

### Conclusion
The box must be sent back.

---
## Step 2
### Observation

Before returning the box, my colleague adds **their own padlock**.

Now the box has:
```text
My padlock
+
My colleague's padlock
```
### Reasoning
The box remains locked throughout the journey.
My colleague still cannot open it, but now they have added a lock that only they can remove.
### Conclusion
The box is sent back to me with two locks attached.

---
## Step 3
### Observation
When I receive the box, I remove **my padlock**.

The box is now locked only with my colleague's padlock.

I send it back one final time.
### Reasoning
Since only my colleague's lock remains, they can unlock the box using their own key.
### Conclusion
My colleague opens the box and retrieves the document.

---
## Answer
1. Lock the box with your padlock and send it.
2. Your colleague adds their padlock and sends it back.
3. Remove your padlock and send it again.
4. Your colleague removes their padlock and opens the box.

At no point is the box unlocked while it is being transported.

---
## Technique
**Sequential Locking / Protocol Design**
Ensure the box is always protected during transit by transferring control through a sequence of locks instead of sharing keys.
