---
description: Greatest Common Denominator
---

# GCD

How to find the greatest common denominator (gcd) of two numbers quickly?



**Euclid's method of finding GCD**

Time Complexity: $$O(log(min(a, b)))$$

Space Complexity: $$O(1)$$

```cpp
int gcd(int a, int b) {
    while (b != 0) {
        int temp = b;
        b = a % b;
        a = temp;
    }
    return a;
}
```

Euclid's algorithm works because it leverages two fundamental properties of the greatest common divisor (GCD):

* If `d`is a divisor of two numbers `a`and `b`,  for `a` >= `b`, then `d`is also a divisor of `a−kb` for any integer `k`.
  * This is true because `d` is still a factor of `a` and `b` , which can be taken out from each expression
* This implies that the GCD of `a`and `b`is the same as the GCD of `b`and $$a\mod b$$
