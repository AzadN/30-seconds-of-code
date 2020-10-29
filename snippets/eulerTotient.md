---
title: eulerTotient
tags: math,advanced
---

Computes the Euler's Totient Function, also known as phi-function ϕ(n) which counts the number of integers between 1 and n inclusive, which are coprime to n. This has wide applications in Cryptography e.g. RSA Algorithm.

- Makes use of the relation ϕ(n) = n * (1 - 1/p1) * (1 - 1/p2) * ...... * (1 - 1/pk) where p1, p2, ...., pk are the prime factors of n.
- Starting from 2 and going till sqrt(n) using the condition check of for loop, we check for prime factors.
- We keep on dividing num by current prime factor and move on to finding the next factor only upon exhausting the power of current factor in number.
- For every ith prime factor, the term (1 - 1/pi) is computed and multiplied cumulatively and the function terminates once all the prime factors are exhausted.
- The time complexity is O(sqrt(n)).

```js
const phi = (num) => {
  let result = num;
  for (i = 2; i * i <= num; ++i)
    if (num % i == 0) {
      while (num % i == 0)
      	num /= i;
      result -= result / i;
    }
	if (num > 1)
	  result -= result / num;
	return result;
};
```

```js
phi(78); // 24
```
