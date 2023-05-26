# Chapter 4 : Euclid's Algorithms

## Section 1 : The basics of Euclidean Algorithms

This section talks about the basic Euclidean algorithm , that is the algorithm to ***calculate the greates common divisor of 2 positive integers***.

<ins> ***Euclid's Algorithm (from Theorem 4.1)*** </ins> : On input $a, b$, where $a, b$ are integers such that $a \geq b \geq 0$, we will calculate $d = gcd(a, b)$ by the following algorithm

```SCSS
r = a, r' = b
while r'!= 0 do
    r'' = r mod r'
    (r, r') = (r', r'')
d = r
```

In `Python`, the algorithm can be represented as one line :

```Python
def gcd(a,b):
    return gcd(b % a, a) if a else b
```

To demonstrate the examples, we will use the mindset from the original algorithm.

<ins> **Example 1** </ins> : Find $gcd(36, 279)$

| $i$   |  $0$  |  $1$  |  $2$  |  $3$  |  $4$  | 
|-------|-------|-------|-------|-------|-------|
| $r$   | $36$  | $279$ | $36$  | $27$  |$9 = d$|
| $r'$  | $279$ | $36$  | $27$  | $9$   | $0$   |

<ins> **Example 2** </ins> : Find $gcd(1283, 91)$

| $i$   | $0$   | $1$   | $2$   |   $3$ | 
|-------|-------|-------|-------|-------|
| $r$   | $1283$| $91$  | $9$   |$1 = d$|
| $r'$  | $91$  | $9$   | $1$   | $0$   |

<ins> **Theorem 4.2 (complexity of Euclid's algorithm)** </ins>

The Euclid's Algorithm has the time complexity of $O(len(a)len(b))$

## Section 2 : The extended Euclidean Algorithms

We know that from ***Theorem 1.8***, there exists 2 integers $s, t$ such that : $as + bt = d = gcd(a,b)$. ***The Extended Euclid Algorithm*** efficiently compute $d, s, t$.

Here's the algorithm derived from ***Theorem 4.3***

```SCSS
Input a, b

r, s, t = a, 1, 0
r', s', t' = b, 0, 1
while r' != 0 do
    q = floor(r / r'), r'' = r mod r'
    r, s, t = r', s', t'
    r', s', t' = r'', s - s'q, t - t'q
d = r

Return d, s, t
```
This algorithm is cleaner in `Python` :
```Python

def extended_gcd(a, b):
    if a == 0:
        return b, 0, 1
    else:
        g, x, y = extended_gcd(b % a, a)
        return g, y - (b // a) * x, x
```

<ins> ***Example 1*** </ins> : Find $egcd(120, 270)$

|  $i$  |  $0$  |  $1$  |  $2$  |  $3$  |
|-------|-------|-------|-------|-------|
|  $q$  |  $0$  |  $0$  |  $2$  |  $4$  |
|  $r$  |  $120$|  $270$|  $120$|  $30$ |
|  $r'$ |  $270$|  $120$|  $30$ |  $0$  |
|  $s$  |  $1$  |  $0$  |  $1$  |  $-2$ |
|  $s'$ |  $0$  |  $1$  |  $-2$ |  $9$  |
|  $t$  |  $0$  |  $1$  |  $0$  |  $1$  |
|  $t'$ |  $1$  |  $0$  |  $1$  |  $-4$ |

So we have : $(d, s, t) = (30, -2, 1)$ and $$as + bt = 120 . (-2) + 270 . 1 = 30 = d$$

<ins> ***Example 2*** </ins> : Find $egcd(71, 172)$

|  $i$  |  $0$  |  $1$  |  $2$  |  $3$  |  $4$  |  $5$  |  $6$  |  $7$  |  $8$  |
|-------|-------|-------|-------|-------|-------|-------|-------|-------|-------|
|  $q$  |  $0$  |  $0$  |  $2$  |  $2$  |  $2$  |  $1$  |  $2$  |  $1$  |  $2$  |
|  $r$  |  $71$ |  $172$|  $71$ |  $30$ |  $11$ |  $8$  |  $3$  |  $2$  |  $1$  |
|  $r'$ |  $172$|  $71$ |  $30$ |  $11$ |  $8$  |  $3$  |  $2$  |  $1$  |  $0$  |
|  $s$  |  $1$  |  $0$  |  $1$  |  $-2$ |  $5$  |  $-12$|  $17$ |  $-46$|  $63$ |
|  $s'$ |  $0$  |  $1$  |  $-2$ |  $5$  |  $-12$|  $17$ |  $-46$|  $63$ | $-172$|
|  $t$  |  $0$  |  $1$  |  $0$  |  $1$  |  $-2$ |  $5$  |  $-7$ |  $19$ |  $-26$|
|  $t'$ |  $1$  |  $0$  |  $1$  |  $-2$ |  $5$  |  $-7$ |  $19$ |  $-26$|  $71$ |

So we have : $(d, s, t) = (1, 63, -26)$ and $$as + bt = 71 . (63) + 172 . (-26) = 1 = d$$

<ins> **Theorem 4.4 (Complexity of Extended Euclid Algorithm)** </ins>

The Extended Euclid's Algorithm has the time complexity of $O(len(a)len(b))$

## Section 3 : Computing modular inverse and Chinese remaindering

<ins> ***Finding Modular Inverse*** </ins>

<ins> **Theorem 4.5** </ins>

Suppose we are given two integers $b, n$, where $0 \leq b < \lt n$, then in the time $O(len(n)^2)$, we can determine if $b$ is relative to $n$, and if so, calculate $b^{-1} \pmod n$

<ins> **Algorithm** </ins>

```SCSS
Input b, n

d, s, t = ecgd(n, b)
if d != 1 then
    Return "No solution"
else then
    if t >= 0 then
        b_inv = t
    else then
        b_inv = t + n

Return b_inv
```

In `Python`, we have build-in functions that calculates multiplicative inverse modulo $n$

```Python

a = 17
n = 91
a_inv = pow(a, -1, n)
assert a*a_inv % n == 1
```

## Section 4 : Speeding up computation via modular computation



## Section 5 : An effective version of Fermat's two squares theorem



## Section 6 : Rational reconstruction and applications



## Section 7 : The RSA cryptosystem

