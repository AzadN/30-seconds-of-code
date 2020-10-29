---
title: queryBitPos
tags: math,logic,beginner
---

Checks whether the ith bit of a number is set(equal to 1) or not. Here i ranges from 1 to b where b is the number of bits in the number. Returns a boolean.

- Generate the bitmask by left shifting 1 by bit_pos places.
- Bitwise AND the number with bitmask.
- The ANDing gives a non-zero output i.e. 2 ^ bit_pos if the bit is set else gives 0 which is then compared with 0 to give the final boolean output, true if the bit is set else false.

```js
const queryBitPos = (num, bit_pos) => (num & (1 << (bit_pos - 1))) != 0;
```

```js
queryBitPos(8, 4); // true
```
