---
title: Notes
weight: 20
---

## Tree API

- Add Vec<Node>
- Track note at position p
- Get Merkle Path for note at position p

## Root

## Tree Data

Goal: Maintain the final edge of the tree:
- position
- commitment
- for every bit set in position, the hash of the sibling

Root:
- Starting at the bottom, hash the note commmitment with
    - its sibling if bit = 1
    - or empty root if bit = 0

## Update of the tree state

After adding 1 or more commitments. Adding 0 commitment is trivial
The update is computed from leaf to root
- Incorporate the previous state
- Include the new commitments
- Determine the new state
The new state becomes the previous state if more commitments are added
Otherwise, it serves to compute the final root

When there are no previous state, the new inserted commitments start at N = 0
Build the leaf layer by putting the commitments starting at offset = 0

If there is a previous state, then N > 0 and the position of the previous state is N-1.
Let's set M = N-1 and consider its binary representation.

## Leaf layer
- If M is odd, put new nodes starting at offset = 2
    - put previous state value at offset = 1
    - put previous state sibling at offset = 0
- If M is even, N is odd, put new nodes starting at offset = 1
    - put previous state value at offset = 0

Then combine nodes 2 to 1. The final elements are handled differently and described later.
Divide M / 2, dropping the fractional part.

## Next layer
- If M is odd, shift the nodes by 1. It is more efficient to predict that and put the result
from the previous step at the right place. Put the sibling at offset = 0

Then combine again. Repeat until we reach the root or M = 0

## Trailing part

At any level, we don't combine the last pair or partial pair.
Let's call P the position of the last inserted commitment.
We form the updated state by storing:
- the commitment for P
- P
- the siblings for every bit set in P. That means that for any layer including the leaves
    - if P is odd, store the node at P-1. Don't merge the pair
    - if P is even, don't do anything
