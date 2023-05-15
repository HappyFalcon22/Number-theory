# Chapter 2 : Congruences

This chapter will focus mainly on :
+ Basic properties of congruences modulo $n$
+ Residue classes modulo $n$
+ Chinese remainder theorem
+ Euler's phi functions
+ Euler's Theorem
+ Fermat's little theorem
+ Quadratic residues
+ Summation over divisors

## Section 1 : Equivalence Relations

Let's review a bit about equivalence relations before we dive into congruences.

Let $S$ be a set. A ***binary relation*** $\sim$ on $S$ is called an ***equivalence relation*** if it is :
+ ***Reflexive*** : $a \sim a$
+ ***Symmetric*** : $a \sim b$ implies $b \sim a$
+ ***Transitive*** : $a \sim b$ and $b \sim c$ implies $a \sim c$

If $\sim$ is an equivalence relation on $S$, then for $a \in S$, we can define its ***equivalence class*** as the set 
$$ [a] = \{ x \in S : x \sim a \}$$

<ins> **Theorem 2.1** </ins>

Let $S$ be a set, $\sim$ be an equivalence relation on the set $S$, and for $a \in S$, let $[a]$ denotes its equivalence class. Then for all $a, b, c \in S$, we have :
+ $a \in [a]$
+ $a \in [b]$ implies $[a] = [b]$

This theorem implies :
+ Each equivalence classes is ***non-empty***.
+ Each element on $S$ belongs to a unique equivalence class. A member of an equivalence class is called a ***representative*** of the class.

<ins> **Easy Exercise** </ins>

**2.1** : Consider the relations $=, \leq, <$ on the set $\mathbb{R}$. Which of these relations is an equivalence relation ?

Consider the relation $=$ :
+ Reflexive : $(a, a)$ satifies because $a = a, \forall a \in \mathbb{R}$ ✅
+ Symmetric : $(a, b)$ and $(b, a)$ because $a = b \Longleftrightarrow b = a$ ✅
+ Transitive : $(a, b), (b, c), (a, c)$ because $a = b$ and $b = c$ implies $a = c$ ✅

$\Longrightarrow$ The relation $=$ is an equivalence relation

Consider the relation $\leq$ :
+ Reflexive : $(a, a)$ satifies because $a \leq a, \forall a \in \mathbb{R}$ ✅
+ Symmetric : $a \leq b$ but not always $b \leq a$ ❌
+ Transitive : $(a, b), (b, c), (a, c)$ because $a \leq b$ and $b \leq c$ implies $a \leq c$ ✅

$\Longrightarrow$ The relation $\leq$ is not an equivalence relation

Consider the relation $<$ :
+ Reflexive : $(a, a)$ not satisfies ❌
+ Symmetric : $a < b$ but not $b < a$ ❌
+ Transitive : $(a, b), (b, c), (a, c)$ because $a \lt b$ and $b < c$ implies $a < c$ ✅

$\Longrightarrow$ The relation $\lt$ is not an equivalence relation

**2.2** : Let $S:=(\mathbb{R} \times \mathbb{R})$ \ $\{(0, 0)\}$. For $(x, y), (x', y') \in S$, let us say $(x, y) \sim (x', y')$ if there exists a real number $\lambda > 0$ such that $(x, y) = (\lambda x', \lambda y')$. Prove that $\sim$ is an equivalence relation. Show that each equivalence class contains a unique representative that lies on the unit circle $x^2 + y^2 = 1$

+ Reflexive : ✅ if $\lambda = 1$
+ Symmetric : We have $(x, y) \sim (x', y')$, with $\lambda$. Then we have $(x', y') \sim (x, y)$ if $(x', y') = (\lambda'x, \lambda'y), \lambda' = \dfrac{1}{\lambda}$. ✅
+ Transitive : ✅ This is quite obvious

For the last problem, consider a relation $(a, b) \sim (na, nb)$ for a real number $n > 0$. We can establist a line that intersects these 2 points :

$$L : y = \dfrac{b}{a}x$$

We can find intersection between the line $L$ and the unit circle

$$x^2 + \left( \dfrac{b}{a}x \right)^2 = 1$$

$$x = \pm \dfrac{a}{\sqrt{a^2 + b^2}}, y = \pm \dfrac{b}{\sqrt{a^2 + b^2}} $$

So with each $[(x, y)]$, we have a unique representative $(\lambda x,\lambda y), \lambda = \dfrac{1}{\sqrt{a^2 + b^2}}$ that lies on the unit circle.

## Section 2 : Definition and Basic Properties of Congruences

Let $n$ be a positive integer, $a, b$ be integers. We say that ***a is congruent to b modulo n*** if $n \mid (a - b)$, and we write 
$$a \equiv b \pmod n$$
If $n \nmid (a - b)$ then we write :
$$a \not \equiv b \pmod n$$

$a \equiv b \pmod n$ if and only if $a = by + n$ for some $y \in \mathbb{Z}$. The relation $a \equiv b \pmod n$ is called the ***congruence relation***, or simply a ***congruence***. The integer $n$ appears in the congruence is called the ***modulus*** of the congruence.

<ins> **Theorem 2.2 (Congruences are equivalence relations)** </ins>

Let $n$ be a positive integer. For all $a, b, c \in \mathbb{Z}$, we have :
+ $a \equiv a \pmod n$
+ $a \equiv b \pmod n$ implies $b \equiv a \pmod n$
+ $a \equiv b \pmod n$ and $b \equiv c \pmod n$ implies $a \equiv c \pmod n$

This theorem simply states that ***congruences are equivalent relations***.

Another property of congruences is that they are ***"compatible"*** with addition and multiplication.

<ins> **Theorem 2.3 (Congruences with addition and multiplication)** </ins>

Let $a, b, a', b', n \in \mathbb{Z}$ with $n > 0$. If : 
$$a \equiv a' \pmod n$$$$b \equiv b' \pmod n$$ then we have :
$$a + b \equiv a' + b' \pmod n$$$$ab \equiv a'b' \pmod n$$

<ins> **Theorem 2.4** </ins>

Let $a, n \in \mathbb{Z}$ with $n > 0$. Then for every $x \in \mathbb{R}$, there exists a unique integer $z \in \left[x, x + n \right)$ such that $z \equiv a \pmod n$

As for the exercise, i will solve it in the other note.

## Section 3 : Solving linear congruences

<ins> **Objective** </ins>

In this section, we consider the general problem of solving linear congruences. More precisely, for a given positive integer $n$, and arbitrary integers $a, b$, we aim to find the set of integers $z$ that satisfy the congruence : $$az \equiv b \pmod n$$

Observe that, if the congruence has a solution $z$, and $z \equiv z' \pmod n$, then $z'$ is also a solution. However, the congruence may or may not have a solution at all, and if it does have solutions, such solutions may or may not be uniquely determined modulo $n$

<ins> **Theorem 2.5 (Set of solutions of a congruence)** </ins>

Let $a, n \in \mathbb{Z}$ with $n > 0$ and let $d := gcd(a, n)$ :
+ For every $b \in \mathbb{Z}$, the congruence $az \equiv b \pmod n$ ***has a solution*** if  $d \mid b$
+ For every $z \in \mathbb{Z}$, we have $az \equiv 0 \pmod n$ if and only if $z \equiv 0 \pmod{n/d}$
+ For all $z, z' \in \mathbb{Z}$, we have $az \equiv az' \pmod n$ if and only if $z \equiv z' \pmod{n/d}$

To recap, the congruence has a solution if $gcd(a, n)$ divides $b$, and in this case the solution is uniquely determined modulo $n/d$

<ins> **Cancellation law from Theorem 2.5** </ins>

From ***Theorem 2.5***, we can deduce a nice cancellation law for congruences : 

If $d := gcd(a, n) = 1$, and $az \equiv az' \pmod n$, then we can remove the common factor $a$ and get $z \equiv z' \pmod n$

If $d := gcd(a, n) \neq 1$, and $az \equiv az' \pmod n$, then we can remove the common factor $a$ but the modulus $n$ will be changed. Therefor, we get $z \equiv z' \pmod{n/d}$ (**more general**)

<ins> **Modular inverse** </ins>

We say that $z \in \mathbb{Z}$ is a ***multiplicative inverse of a modulo n*** if :
$$az \equiv 1 \pmod n$$

Some observation and notes about multiplicative inverse :

+ $a$ has a multiplicative inverse modulo $n$ if and only if $gcd(a, n) = 1$. If $a$ does have a multiplicative inverse, such inverse is uniquely determined modulo $n$, that is, if $z, z'$ are multiplicative inverses of $a$ modulo $n$, then $z \equiv z' \pmod n$
+ If $z$ is a multiplicative inverse of $a$ modulo $n$ then $a$ is the multiplicative inverse of $z$ modulo $n$.
+ Given $a \equiv a' \pmod n$, then $z$ is the multiplicative inverse of $a$ modulo $n$ if and only if $z'$ is the multiplicative inverse of $a'$ modulo $n$
 
We denote the multiplicative inverse of $a$ modulo $n$ simply by :
$$a^{-1}\;mod\;n$$

## Section 4 : The Chinese Remainder Theorem

The basic but power tool to solve a linear congruence. What we consider is the case where the moduli of those congruence are ***relatively prime***.

<ins> **Theorem 2.6 (Chinese Remainder Theorem)** </ins>

Let $\{n_i\}^k_{i=1}$ be a ***pairwise relatively prime family of positive integers***, and let $a_1, a_2, ..., a_k$ be arbitrary integers. Then there exists a solution $a \in \mathbb{Z}$ to the system of congruences :
$$a \equiv a_i \pmod{n_i}\;\;(i = 1, 2, 3, ..., k)$$
Moreover, any $a' \in \mathbb{Z}$ is a solution to this system of congruences if and only if 
$$a' \equiv a \pmod N$$
where $N = \prod_{i=1}^k n_i$

<ins> **Finding the solution to the system of congruences** </ins>

**Step 1** : Compute $N = n_1n_2...n_k$

**Step 2** : Compute $y_i = \dfrac{N}{n_i}\;\;\;(i = 1...k)$

**Step 3** : Comput $z_i \equiv y_i^{-1} \pmod{n_i}\;\;\;(i = 1...k)$

**Step 4** : Find the solution $$a = \sum_{i=1}^k a_iz_iy_i$$
and $a\;mod\;N$ is the solution modulo $N$.

<ins> **A little bit Python** </ins>
```Python
a = [2, 3, 5]
n = [5, 11, 17]

def chinese_remainder_theorem(a, n):
    # Find N
    N = 1
    for i in n:
        N *= i
    y = []
    for i in n:
        y.append(N // i)
    result = 0
    for i in range(len(n)):
        result += a[i]*y[i]*pow(y[i], -1, n[i])
    return result % N
```

I will use the input in the above code as the example : 

$$
\begin{cases}
    a \equiv 2 \pmod 5   \\ 
    a \equiv 3 \pmod{11} \\ 
    a \equiv 5 \pmod{17}
\end{cases}
$$

+ First we compute $N = 5.11.17 = 935$
+ We compute $y_1, y_2$ and $y_3$
    + $y_1 = 935 / 5 = 187$
    + $y_2 = 935 / 11 = 85$
    + $y_3 = 935 / 17 = 55$
+ Next, we compute $z_1, z_2$ and $z_3$
    + $z_1 \equiv y_1^{-1} \equiv 3 \pmod 5$  
    + $z_2 \equiv y_2^{-1} \equiv 7 \pmod 11$
    + $z_3 \equiv y_3^{-1} \equiv 13 \pmod 17$  
+ We are finally able to find $a$ :
$$a = \sum_{i=1}^3a_iy_iz_i = 2.187.3 + 3.85.7 + 5.55.13 = 872$$

The solution is $a = 872$

## Section 5 : Residue classes

By ***Theorem 2.2***, we learnt that the ***congruence relation*** $\cdot \equiv \cdot \pmod n$ is indeed an ***equivalence relation*** on the set $\mathbb{Z}$. As such, this relation ***partitions*** the set $\mathbb{Z}$ into equivalent classes. We denote the equivalent class that contains the integer $a$ by $[a]_n$. And when $n$ is clear from context, we simply denote $[a]$. So by definition, we have :
$$z \in [a] \Longleftrightarrow z \equiv a \pmod n \Longleftrightarrow z = a + ny\;\text{for some}\;y \in \mathbb{Z}$$, and hence :
$$[a] = a + n\mathbb{Z} = \{ a + ny : y \in \mathbb{Z} \}$$

In the pass, this class was called ***residue class modulo n***. Any member of a residue class modulo $n$ is called the ***representative*** of that class.

We denote $\mathbb{Z}_n$ as the set of ***residue classes modulo n***

<ins> **Theorem 2.7** </ins>

Let $n$ be a positive integer. Then $\mathbb{Z}_n$ consists of the $n$ distinct ***residue classes*** $[0], [1], [2], ..., [n - 1]$. Moreover, for every $x \in \mathbb{R}$, each residue class modulo $n$ contains a unique representative in the interval $\left[x, x + n\right)$

Thats all what we want to note in this section.

## Section 6 : Euler's phi functions

***Euler's phi function (Euler's totient function)*** is defined for all positive integers $n$ as :
$$\varphi(n) := |\mathbb{Z}_n^*|$$
Equivalently, $\varphi(n)$ is equal to the number of integers in the interval of $0$ and $n - 1$ that is ***relatively prime*** to $n$

The set $\mathbb{Z}_n^*$ is the set of elements in $\mathbb{Z}_n$ that ***has its multiplicative inverse***

<ins> **Example** </ins>

+ $\varphi(10) = |\{ 1, 3, 7, 9 \}| = 4$
+ $\varphi(25) = |\{ 1, 2, 3, 4, 6, 7, 8, 9, 11, 12, 13, 14, 16, 17, 18, 19, 21, 22, 23, 24 \}| = 20$
+ $\varphi(7) = |\{ 1, 2, 3, 4, 5, 6 \}| = 6$

Note that if $p$ is prime, then $\varphi(p) = p - 1$.

<ins> **Theorem 2.9 (Phi of a product)** </ins>

Let $\{n_i\}^k_{i=1}$ be a ***pairwise relatively prime family of positive integers***, and let $n = \prod_{i=1}^k n_i$, then :
$$\varphi(n) = \prod_{i=1}^k \varphi(n_i)$$

<ins> **Example** </ins>

+ $\varphi(3) = 2, \varphi(5) = 4$
+ $\varphi(15) = \varphi(3.5) = \varphi(3) \varphi(5) = 8 = |\{ 1, 2, 4, 7, 8, 11, 13, 14\}|$

<ins> **Theorem 2.10 (Phi of a prime power)** </ins>

Let $p$ be a prime and $e$ a positive integer. We have :
$$\varphi(p_e) = p^{e - 1}(p - 1)$$

<ins> **Example** </ins>

+ $\varphi(7^2) = 7.6 = 42$
+ $\varphi(2^5) = 2^4.1 = 16$

We now know how to calculate phi of ***prime, prime power*** and phi of a ***product***, let's generalize this into the one only formula.

We aim to calculate phi of $n = p_1^{e_1}p_2^{e_2}...p_r^{e_r}$

Use ***Theorem 2.9***, we have :
$$\varphi(n) = \prod_{i = 1}^r \varphi(p_i^{e_i})$$
Use ***Theorem 2.10***, we can calculate $\varphi(p_i^{e_i})$
$$\varphi(p_i^{e_i}) = p_i^{e_i - 1}(p_i - 1) = p_i^{e_i}\left( 1 - \dfrac{1}{p_i} \right)$$transforming like this will help us when we put this formula to the product.

Combine these two calculate $\varphi(n)$
$$\varphi(n) = \prod_{i=1}^r p_i^{e_i}\left( 1 - \dfrac{1}{p_i} \right) = n \prod_{i=1}^r \left( 1 - \dfrac{1}{p_i} \right)$$
This formula is exactly what ***Theorem 2.11*** states 🤓

## Section 7 : Euler's theorem and Fermat's little theorem

Let $n$ be a positive integer, and let $a \in \mathbb{Z}_n^*$, we consider the ***sequence of powers*** of $a$ :
$$a^0 (1), a^1, a^2, a^3, ... $$

Since all these elements $\in \mathbb{Z}_n^*$, and the set itself is finite, the sequence ***must repeat at some point***. Specifically, there must be a positive integer $k$ such that $a^k = a^i$ for some $i = 0,1,...,k-1$.

$k$ is called ***the multiplicative order of a*** if $k$ is the smallest positive integer such that :
$$a^k = 1$$

$k$ is called ***the multiplicative order of a modulo n*** if $k$ is the smallest positive integer such that :
$$a^k \equiv 1 \pmod n$$

<ins> **Theorem 2.12** </ins>

Let $n$ be a positive integer, and let $a$ be an element of $\mathbb{Z}_n^*$ of multiplicative order $k$. Then for every $i \in \mathbb{Z}$, we have $a^k = 1$ if and only if $k \mid i$. More generally, for all $i, j \in \mathbb{Z}$, we have $a^i = a^j$ if and only if $i \equiv j \pmod k$

<ins> **Theorem 2.13 (Euler's Theorem)** </ins>

Let $n$ be a positive integer and $a \in \mathbb{Z}_n^*$. Then $$a^{\varphi(n)} = 1$$. In particular, the multiplicative order of $a$ divides $\varphi(n)$.

<ins> **Theorem 2.14 (Fermat's Little Theorem)** </ins>

For every prime $p$, and every $a \in \mathbb{Z}_p$, we have : $$a^p = a$$

From the two theorem, we can deduce that :
+ $a^{p - 1} \equiv 1 \pmod p$
+ $a^{-1} \equiv a^{p - 2} \pmod p$

In the language of congruence, Fermat's little theorem says that for every prime $p$ and every integer $a$, we have : $$a^p \equiv a \pmod p$$

For a given positive integer $n$, we say that $a \in \mathbb{Z}$ with $gcd(a, n) = 1$ is a ***primitive root modulo n*** if the multiplicative order of $a$ modulo $n$ is equal to $\varphi(n)$. Which means that $a^i$ ranges over all elements of $\mathbb{Z}_n^*$. As we go deeper to Chapter 7, we will learn that not all positive integers have primitive roots.

<ins> **Theorem 2.15** </ins>

Suppose $a \in \mathbb{Z}_n^*$ has multiplicative order $k$. Then for every $m \in \mathbb{Z}$, the multiplicative order of $a^m$ is $\dfrac{k}{gcd(m, k)}$

## Section 8 : Quadratic residues

We begin the section with a bit general, preliminary definitions and general observations about powers in $\mathbb{Z}_n^*$. For each integer $m$, we define
$$(\mathbb{Z}_n^*)^m := \{\beta^m : \beta \in \mathbb{Z}_n^*\}$$
the set of ***mth-power*** in $\mathbb{Z}_n^*$. 
The set $(\mathbb{Z}_n^*)^m$ is ***non-empty***, as it always contains $[1]$.

<ins> **Theorem 2.16** </ins>

Let $n$ be a positive integer, let $\alpha, \beta \in \mathbb{Z}_n^*$, and let $m$ be any integer.
+ If $\alpha \in (\mathbb{Z}_n^*)^m$, then  $\alpha^{-1} \in (\mathbb{Z}_n^*)^m$
+ If $\alpha \in (\mathbb{Z}_n^*)^m$ and  $\beta \in (\mathbb{Z}_n^*)^m$, then  $\alpha \beta \in (\mathbb{Z}_n^*)^m$
+ If  $\alpha \in (\mathbb{Z}_n^*)^m$ and  $\beta \notin (\mathbb{Z}_n^*)^m$, then  $\alpha \beta \notin (\mathbb{Z}_n^*)^m$

<ins> **Theorem 2.17** </ins>

Let $n$ be a positive integer. For each $\alpha \in \mathbb{Z}_n^*$, and all $l, m \in \mathbb{Z}$ with $gcd(l, m) = 1$. If $\alpha^l \in (\mathbb{Z}_n^*)^m$, then $\alpha \in (\mathbb{Z}_n^*)^m$

In this context, we will be focusing on the power of $2$ instead of a general power. An integer $a$ is called a ***quadratic residue modulo n*** if :
+ $gcd(a, n) = 1$
+ $a \equiv b^2 \pmod n$ for some $b$

In this case, $b$ is called the ***square root of a modulo n***

### Quadratic residues modulo prime $p$

<ins> **Theorem 2.18 (Square root of 1)** </ins>

$\beta^2 \equiv 1 \pmod p$ if and only if $\beta \equiv \pm 1 \pmod p$

<ins> **Theorem 2.19** </ins>

Let $p$ be an odd prime and $\gamma, \beta \in \mathbb{Z}_p^*$. Then $\gamma^2 = \beta^2$ if and only if $\gamma = \pm \beta$

<ins> **Theorem 2.20** </ins>

Let $p$ be an odd prime. Then $|(\mathbb{Z}_p^*)^2| = \dfrac{p - 1}{2}$

Next, we look at an important theorem to determine whether an element is a quadratic residue modulo $p$ :

<ins> **Theorem 2.21 (Euler's Criterion)** </ins>

Let $p$ be an odd prime, and $\alpha \in \mathbb{Z}_p^*$ :
+ $\alpha^{(\frac{p - 1}{2})} = \pm 1$
+ If $\alpha \in (\mathbb{Z}_p^*)^2$, then $\alpha^{(\frac{p - 1}{2})} = 1$
+ If $\alpha \notin (\mathbb{Z}_p^*)^2$, then $\alpha^{(\frac{p - 1}{2})} = -1$

In the language of congruence, this theorem can be reformulated by using ***the Legendre symbol*** :
$$\left(\dfrac{\alpha}{p}\right) \equiv \alpha^{\dfrac{p - 1}{2}} \pmod p$$
+ If $\left(\dfrac{\alpha}{p}\right) \equiv 1 \pmod p$, then there exists an integer $x \in \mathbb{Z}_p^*$ such that $\alpha \equiv x^2 \pmod p$. Then $\alpha$ is a ***quadratic residue modulo p***
+ If $\left(\dfrac{\alpha}{p}\right) \equiv -1 \pmod p$, then $\alpha$ is a ***quadratic non-residue modulo p***

<ins> **Theorem 2.22 (Wilson's Theorem in the language of congruences)** </ins>

Let $p$ be an odd prime. We have :
$$(p - 1)! \equiv -1 \pmod p$$

<ins> **Theorem 2.23** </ins>

Let $p$ be an odd prime, and $\alpha, \beta \in \mathbb{Z}_p^*$. If $\alpha \notin (\mathbb{Z}_p^*)^2$ and $\beta \notin (\mathbb{Z}_p^*)^2$, then $\alpha \beta \in (\mathbb{Z}_p^*)^2$

From this theorem, we can deduce a table of multiplication for ease of understanding :

$$QR \times QR = QR$$$$QR \times QNR = QNR$$$$QNR \times QNR = QR$$
where 
+ **QR** stands for **quadratic residue**
+ **QNR** stands for **quadratic non-residue**

### Quadratic residues modulo prime power $p^e$

Let $p$ be an odd prime, $e$ be a positive integer, $\alpha, \beta, \gamma \in \mathbb{Z}_{p^e}^*$. These notes are from ***Theorem 2.24 to Theorem 2.30*** :

***2.24*** : $\beta^2 = 1$ if and only if $\beta = \pm 1$

***2.25*** : $\gamma^2 = \beta^2$ if and only if $\gamma = \pm \beta$

***2.26*** : $|(\mathbb{Z}_{p^e}^*)^2| = \dfrac{\varphi(p^e)}{2} = \dfrac{p^{e - 1}(p - 1)}{2}$

***2.27*** : 
+ $\alpha^{(\frac{\varphi(p^e)}{2})} = \pm 1$
+ If $\alpha \in (\mathbb{Z}_p^*)^2$, then $\alpha^{(\frac{\varphi(p^e)}{2})} = 1$
+ If $\alpha \notin (\mathbb{Z}_p^*)^2$, then $\alpha^{(\frac{\varphi(p^e)}{2})} = -1$

This also means that the ***Legendre symbol*** : 
$$\left(\dfrac{\alpha}{p^e}\right) \equiv \alpha^{(\dfrac{\varphi(p^e)}{2})} \pmod{p^e}$$
 
***2.28*** : $$\prod_{\beta \in \mathbb{Z}_{p^e}^*} \beta = -1$$

***2.29*** : If $\alpha \notin (\mathbb{Z}_{p^e}^*)^2$ and $\beta \notin (\mathbb{Z}_{p^e}^*)^2$, then $\alpha \beta \in (\mathbb{Z}_{p^e}^*)^2$

***2.30*** : Let $p$ be an odd prime, $e$ be a positive integer and $a$ be any integer. Then $a$ is a quadratic residue modulo $p^e$ if and only if $a$ is a quadratic residue modulo $p$

### Square root of $-1$ modulo $p$

<ins> **Theorem 2.31** </ins>

Let $p$ a an odd prime. Then $-1$ is a quadratic residue modulo $p$ if and only if $p \equiv 1 \pmod 4$

<ins> **Theorem 2.32** </ins>

Let $p$ be an odd prime with $p \equiv 1 \pmod 4$, $\gamma \in \mathbb{Z}_p^* \setminus (\mathbb{Z}_p^*)^2$, and $\beta := \gamma^{\frac{p - 1}{4}}$. Then $\beta^2 = -1$

<ins> **Theorem 2.34 (Fermat's Two Squares Theorem)** </ins>

Let $p$ be an odd prime. Then $p = r^2 + t^2$ for some $r, t \in \mathbb{Z}$ if and only if $p \equiv 1 \pmod 4$

<ins> **Theorem 2.35, 2.36** </ins>

There are infinitely many prime $p \equiv 1 \pmod 4$ and $p \equiv 3 \pmod 4$