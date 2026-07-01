# Card Game

## Problem

A deck contains:
```text
26 Red cards
26 Black cards
```
Cards are processed in pairs:
* RR -> you keep both cards.
* BB -> Dealer keeps both cards.
* RB or BR -> both cards are discarded.

If you end with more cards than Dealer, you win $100. 

How Much should you pay to play?
## Key Observation
Every discarded pair removes:
```text
* 1 Red card
* 1 Black card
```
So discarded cards always remove equal number of Red and Black cards.
## Step 1
### Observation
Suppose there are:
```text
x
```
mixed pairs (RB or BR).
### Reasoning
These discarded pairs remove:
```text
x Red cards
x Black cards
```
The deck originally has:
```text
26 Red cards
26 Black cards
```
So after all mixed pairs are discarded, the remaning cards still contains same number of red and black cards.
### Conclusion
Remaining Red cards = Remaining Black cards
## Step 2
### Observation
The remaning cards can only form:
```text
RR pairs
BB pairs
```
Let:
```text
r = number of RR pairs
b = number of BB pairs
```
## Reasoning
Remaining Red cards:
```text
2r
```
Remaining Black cards:
```text
2b
```
From step 1:
```text
2r = 2b
```
Therefore:
```text
r = b
```
### Conclusion
The the number of RR pairs equal the number of BB pairs.
## Step 3
### Observation
Each RR pair gives you:
```text
2 cards
```
Each BB pairs give the Dealer:
```text
2 cards
```
### Reasoning
Since:
```text
r = b
```
you receive:
```text
2r cards
```
and Dealer receives:
```text
2b cards
```
These are always equal.
### Conclusion
Your Cards = Dealer cards

## Answer
Every game ends with tie.

Since ties pay \:
```text
$0
```
the expected value of the game is:
```text
$0
```
So the maximum amount you should pay is:
```text
$0
```
## Technique
**Invariant/Symmentry**

Discarding mixed pairs always removes one red an done black card, preserving the balance between the two colors.





























