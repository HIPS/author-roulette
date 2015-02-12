# Author Roulette!!!
---------------

A protocol for randomizing author order based on a public seed, along with a LaTeX implementation.

## Motivation

Co-starred first authorship can be used to signal that the authors intend to share credit equally.
But it's often ambiguous as to whether the order of the first two authors is supposed to convery extra tie-breaking information.

We decided to implement a protocol for author order randomization with the following features:

1. Even the authors themselves can't rig the results.
2. Everyone can verify that it was really random.


## Protocol

1. Before submitting to arXiv, include somewhere in your document source a sentence declaring your intention to randomize author order.
For example, "The seed will be the arXiv ID number following the period" as a comment in the LaTeX source.
Be sure to be unambiguous about what you'll use for a random seed.
2. Submit your paper to arXiv the first time, with an arbitrary author order.
3. When your paper is published by the arXiv, copy the seed (for example, the last 4 digits of the arXiv identifier).
4. Permute the order of the authors if the XOR of the last N significant bits is 0.
5. Resubmit to arXiv, updating author order meta-data if necessary.



