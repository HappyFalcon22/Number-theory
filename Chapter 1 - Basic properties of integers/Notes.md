# Chapter 1 : Basic properties of integers

This chapter discusses some of the fundamental properties of integers, including :
+ Notions of divisibility and primality
+ Unique factorisation into primes
+ GCD (Greatest Common Divisors)
+ LCM (Least Common Multiples)

## Section 1 : Divisibility and primality

<ins> **Divisibility** </ins>

Given $a, b \in \mathbb{Z}$, we say that ***a divides b*** if $az = b$, for some $z \in \mathbb{Z}$.
There are some notations and results regarding divisibility :
+ We write $a\;\vert\;b$ to denote :
  + ***a divides b*** or ***b is divisible by a*** 
  + ***a is a divisor of b*** or ***b is a multiple of a***
+ We write $a \nmid b$ to denote the opposite case.

<ins> **Theorem 1.1** </ins>

For all $a, b, c \in \mathbb{Z}$, we have : 
+ $a \mid a$, $a \mid 0$ and $1 \mid a$
+ $0 \mid a$ if and only if $a = 0$
+ $a \mid b$ if and only if $-a \mid b$ if and only if $a \mid -b$
+ $a \mid b$ and $b \mid c$ implies $a \mid (b + c)$
+ $a \mid b$ and $b \mid c$ implies $a \mid c$

<ins> **Example** </ins>

+ $3 \mid 6$ because $3.2 = 6$.
+ $3 \mid 9$, $9 \mid 81$ then implies $3 \mid (9 + 81) = 90$
+ $7 \mid 49$, $49 \mid 98$ then implies $7 \mid 98$ ($7.14 = 98$)

<ins> **Theorem 1.2** </ins>

For all $a, b \in \mathbb{Z}$, we have $a \mid b$ and $b \mid a$ if and only if $a = \pm b$.

<ins> **Primes and composites** </ins>

Let $n$ be a positive integer. if ***only 1 and n divides n***, then $n$ is ***prime***. Otherwise, $n$ is ***composite***.

***Note*** : $1$ is ***neither prime nor composite***

<ins> **Theorem 1.3 (Fundamental theorem of arithmetic)** </ins>

Every non-zero integer can be expressed as : 

$$n = \pm p_1^{e_1}p_2^{e_2}...p_r^{e_r}$$

where $p_1, p_2, ..., p_r$ are ***distinct primes***, and $e_1, e_2, ..., e_r$ are ***positive integers***. Moreover, this expression is ***unique***, up to a reordering of the primes.

<ins> **Example** </ins>

The number $1900544$ can be expressed as :

$$1900544 = 2^{16}.29^1$$

<ins> **Theorem 1.4 (Division with remainder property)** </ins>

Let $a, b \in \mathbb{Z}, b > 0$. Then there exists unique $q, r \in \mathbb{Z}$ such that $a = bq + r$ and $0 \leq r < b$.

Following the definition then :
+ $a$ is the ***dividend***
+ $b$ is the ***divisor***
+ $q$ is the ***quotient***
+ $r$ is the ***remainder***

<ins> **Exercise takeaways** </ins>

**1.1** : Let $a, b, d \in \mathbb{Z}, d \neq 0$, then $a \mid b$ if and only if $da \mid db$

**1.2** : Let $n$ be a composite integer, there exists a prime $p$ that ***divides n*** and $p \leq \sqrt{n}$

**1.3** : 

**1.4** : Let $x \in \mathbb{R}$. Then $2\{x}$
