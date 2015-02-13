# Author Roulette!!!

A protocol for randomizing author order based on a public seed, along with a LaTeX implementation.

## Motivation

The widespread "co-first star" signals that authors intend to share credit equally.
But it can be unclear whether the order of the first two authors is intended to convey extra tie-breaking information.

We decided to make a protocol for randomization of author order with the following features:

1. Even the authors themselves can't rig the results.
2. Everyone can verify that it was really random.

## Public record and random seed

The idea is to base a random permutation of author order on a seed which is
unknowable until after an initial public submission. An imperfectly secure but
perfectly adequate seed is the paper's arXiv identifier. An ironclad option is
the [NIST randomness beacon](https://beacon.nist.gov/home) for tomorrow at noon.

## Protocol

1. Prepare a version of your paper with an arbitrary author order and a sentence
   declaring your intended seed.  For example, "The seed will be this paper's
   arXiv identifier." as a comment in the LaTeX source.
2. Submit the first version to a public forum (e.g. arXiv).
3. Obtain the now-available seed and permute the author order iff the XOR of the
   seed's 5 least significant bits is 0 (this gentle hash doesn't add
   randomness, just surprise).
4. The newly equal-but-more-equal author buys her coauthor a drink.
