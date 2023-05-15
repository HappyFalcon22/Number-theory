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



## Section 4 : The Chinese Remainder Theorem

## Section 5 : Residue classes

## Section 6 : Euler's phi functions

## Section 7 : Euler's theorem and Fermat's little theorem

## Section 8 : Quadratic residues

## Section 9 : Summation over divisors
