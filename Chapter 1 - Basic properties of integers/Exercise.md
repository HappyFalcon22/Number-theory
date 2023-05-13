# Exercise Chapter 1
## Section 1 : Divisibility and Primality
<ins> ***Exercise 1.1***</ins>

Let $a, b, d \in \mathbb{Z}, d \neq 0$, Prove that $a \mid b$ if and only if $da \mid db$

<ins> **Solve**</ins>

If $a \mid b$, then $az = b, z \in \mathbb{Z}$.

Multiply the two sides by $d$ (we can do that because $d \neq 0$), then we have : $(ad)z = (bd)$, which implies that $da \mid db$. ***(Q.E.D)***

<ins> ***Exercise 1.2***</ins>

Let $n$ be a composite integer, prove that there exists a prime $p$ that ***divides n*** and $p \leq \sqrt{n}$

<ins> **Solve**</ins>

I think of proving this using contradiction. Let's ***assume that there are no prime factors that divides n and larger than the square root of n***.

Using ***Theorem 1.3***, we can express $n$ as :

$$n = \pm p_1^{e_1}p_2^{e_2}...p_r^{e_r}$$

Let's assume that ***$e_i = 1$***, then :

$$n = \pm p_1p_2...p_r$$

Since all $p_i > \sqrt{n}$, $p_1p_2 > \sqrt{n}\sqrt{n} = n$. This contradicts with the expression of $n$ derived from ***Theorem 1.3***. ***(Q.E.D)***

<ins> ***Exercise 1.3***</ins>

<ins> **Solve**</ins>

<ins> ***Exercise 1.4***</ins>

Let $x \in \mathbb{R}$. Prove that $2\lfloor x \rfloor \leq \lfloor 2x \rfloor \leq 2 \lfloor x \rfloor + 1$

<ins> **Solve**</ins>

Let's use the ***flooring operator*** to each of these term :
+ $2 \lfloor x \rfloor$
  + $a \leq x < a + 1$ 
  + $2a \leq 2x < 2a + 2$