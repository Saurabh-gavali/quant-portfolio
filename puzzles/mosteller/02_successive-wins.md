# Successive Wins
## Problem
Elmer wins a prize if he wins at least two consecutive matches in a three-match series.

He may choose between the orders Father–Champion–Father or Champion–Father–Champion,

where the champion is the stronger opponent.

## Approach
Let \(p\) be the probability of beating his father and \(q\) the probability of beating the champion, with \(p>q\).

Compute the probability of obtaining two consecutive wins (WWW, WWL, or LWW) for each schedule and compare the results.

## Solution

\[
P_{FCF} = p^2q + pq(1-p) + (1-p)pq = pq(2-p)
\]

\[
P_{CFC} = pq^2 + pq(1-q) + (1-q)pq = pq(2-q)
\]

Since \(p>q\),

\[
P_{CFC} > P_{FCF}.
\]

Therefore, Elmer should choose the **Champion–Father–Champion (CFC)** order.

## Key Insight
Placing the easier opponent in the middle allows that match to contribute to **both** possible consecutive-win pairs,
maximizing the chance of getting two wins in a row.
