---
title: setBitPositionToVal
tags: math,logic,intermediate
---

Sets the ith bit of a number to a binary value. Here i ranges from 1 to b where b is the number of bits in the number.

- Generate the bitmask by left shifting 1 by i - 1 positions and then bitwise negating it to flip all the bits except the (i - 1)th one.
- Bitwise AND the number with mask to set (i - 1)th bit to 1.
- Left shift the val to be set by (i - 1) positions.
- Finally bitwise OR the num and val to get the result i.e. set the ith bit to val.

```js
const setBitPositionToVal = (num, i, val) => {
  let mask = ~(1 << i - 1)
  num = num & mask
  val = val << i - 1
  num = num | val
  return num
};
```

```js
setBitPositionToVal(16, 4, 1); // 24
```
