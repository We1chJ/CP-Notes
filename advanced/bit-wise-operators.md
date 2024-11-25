---
description: A page dedicated to the brilliant intersection between math and cp problems
---

# Bit-wise Operators

Bitwise operators include common ones: &, |, ^, etc. They act on bits representation of data such as integers.



## Cool Tricks and Properties

### AND (&)

`1 & 1 = 1` and all other cases yield 0.

### OR (|)&#x20;

Yields 1 as long as one of the two bits is 1.

### XOR (^)

XOR operator (^) is **associative**, **commutative**, and **reversible**. Whenever you face a problem involving the XOR concept, try to use these properties. They will save you a lot of time and sometimes they are the key to the solutions.

These properties mean that the order of a series of XOR operations does not matter. Most importantly, prefix sum can be applied if needed.

{% embed url="https://leetcode.com/problems/count-triplets-that-can-form-two-arrays-of-equal-xor/description/" %}

One interesting property is that XOR operation is **reversible**. To get to the pre-XORed number, just XOR again with the same number. **XORing the same number twice cancels the effects**. This property allows problems like [Single Number](https://leetcode.com/problems/single-number/description/) to be solved like magics.

### NOT (\~)

Flip every single bit to the other one.&#x20;

**Note that this is different from the ! operator, which is used in boolean expression that flips only one value.**

It is noteworthy that if \~ operator is applied to a number, its negative bit will be flipped as well.

E.g. take `10101` . If we do `~10101` -> `1 01010`

Notice that there is an extra hidden bit in front. This bit is always there to in the computer system to represent the negative bits. If it is 0 nothing happens, which is why it's usually not shown. But if it is 1, it has a value of - 2^5, which essentially turns everything into negative numbers even if all other bits are 1.

So let's say we want to find the complement of a number in bits, we will want to flip all bits but not the last one. What we can do is flip them all including the last bit, and then add the last bit back to cancel the effect.

## Sums

`a+b =(a & b) + (a | b)`

It is also equal to: 2⋅(a\&b)+a⊕b

Knowing this, when only the AND and OR are known, we can still compute the sum of two numbers.
