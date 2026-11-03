Mathematical Definitions and Notation

1. Purpose

This document establishes the mathematical definitions, symbols and conventions used in the investigation of reverse-and-add dynamics.

The purpose is to maintain consistency throughout the research paper and its accompanying proofs.

⸻

2. Basic Definitions

Definition 2.1: Positive Integer

Let (n) be a positive integer:

$$
n\in\mathbb{Z}^{+}.
$$

All reverse-and-add transformations in this investigation begin with positive integers.

Definition 2.2: Decimal Digit Representation

Suppose (n) has exactly (L) decimal digits.

It can be represented as

$$
n=\sum_{i=0}^{L-1}a_i10^i,
$$

where:

* (L) is the number of decimal digits.
* (a_i) is the digit in decimal position (i).
* (a_0) is the units digit.
* (a_{L-1}) is the most significant digit.

Each digit satisfies

$$
a_i\in{0,1,2,\ldots,9}.
$$

The most significant digit is nonzero.

Definition 2.3: Digit Reversal

The digit reversal function (R(n)) returns the integer obtained by reversing the decimal digits of (n).

Formally,

$$
R(n)=\sum_{i=0}^{L-1}a_{L-1-i}10^i.
$$

For example,

$$
R(196)=691.
$$

Any leading zeros produced by reversal are discarded when interpreting the result as an integer.

Definition 2.4: Reverse-and-Add Transformation

The reverse-and-add transformation is defined as

$$
\boxed{T(n)=n+R(n).}
$$

For example,

$$
T(196)=196+691=887.
$$

Definition 2.5: Reverse-and-Add Sequence

Given an initial positive integer (n_0), define the sequence recursively by

$$
\boxed{n_{t+1}=T(n_t).}
$$

Equivalently,

$$
n_{t+1}=n_t+R(n_t).
$$

Here, (t) represents the iteration number, beginning at zero.

⸻

3. Decimal Digit Properties

Definition 3.1: Digit Sum

The decimal digit sum (S(n)) is the sum of all decimal digits of (n).

If

$$
n=\sum_{i=0}^{L-1}a_i10^i,
$$

then

$$
\boxed{S(n)=\sum_{i=0}^{L-1}a_i.}
$$

For example,

$$
S(196)=1+9+6=16.
$$

Definition 3.2: Decimal Palindrome

A positive integer is a decimal palindrome if its decimal representation remains unchanged when read in reverse.

In other words,

$$
R(n)=n.
$$

Examples include

$$
121,\quad 1331,\quad 12321.
$$

Definition 3.3: Palindrome Formation

A reverse-and-add sequence beginning at (n_0) reaches a palindrome if there exists a nonnegative integer (t) such that

$$
R(n_t)=n_t.
$$

If no such iteration has been established, palindrome formation remains unresolved.

⸻

4. Mirrored Digit-Pair Sums

Definition 4.1: Mirrored Digit-Pair Sum

For a number with (L) decimal digits, define the mirrored digit-pair sum at position (i) as

$$
\boxed{p_i=a_i+a_{L-1-i}.}
$$

The sequence of pair sums is

$$
p_0,p_1,\ldots,p_{L-1}.
$$

Each pair consists of digits occupying symmetric positions in the original decimal representation.

For example, consider

$$
n=196.
$$

Its digits, from least significant to most significant, are

$$
(a_0,a_1,a_2)=(6,9,1).
$$

The mirrored pair sums are

$$
p_0=6+1=7,
$$

$$
p_1=9+9=18,
$$

$$
p_2=1+6=7.
$$

Therefore,

$$
(p_0,p_1,p_2)=(7,18,7).
$$

⸻

5. Carry Propagation

Definition 5.1: Incoming Carry

Let (c_i) denote the carry entering decimal column (i).

The initial carry is

$$
\boxed{c_0=0.}
$$

Definition 5.2: Outgoing Carry

The outgoing carry from column (i) is defined by

$$
\boxed{
c_{i+1}=
\left\lfloor
\frac{p_i+c_i}{10}
\right\rfloor.
}
$$

Here, (\lfloor x\rfloor) denotes the greatest integer less than or equal to (x).

Definition 5.3: Resulting Decimal Digit

The resulting digit in column (i) is

$$
\boxed{
e_i=p_i+c_i-10c_{i+1}.
}
$$

Each resulting digit satisfies

$$
0\leq e_i\leq9.
$$

Definition 5.4: Total Carry Count

The total carry count is defined as

$$
\boxed{
C(n)=\sum_{i=1}^{L}c_i.
}
$$

The final carry (c_L), if nonzero, represents an additional leading digit in the resulting integer.

This definition is used in the carry-based digit-sum identity:

$$
\boxed{
S(T(n))=2S(n)-9C(n).
}
$$

⸻

6. Modular Arithmetic

Definition 6.1: Congruence

Two integers (a) and (b) are congruent modulo a positive integer (m) if (m) divides their difference.

This is written as

$$
a\equiv b\pmod m.
$$

Equivalently,

$$
m\mid(a-b).
$$

Definition 6.2: Divisibility by 11

An integer (n) is divisible by 11 if there exists an integer (k) such that

$$
n=11k.
$$

Equivalently,

$$
n\equiv0\pmod{11}.
$$

Definition 6.3: Digit-Length Parity

The parity of the decimal digit length is determined by whether (L) is odd or even.

For odd (L),

$$
(-1)^{L-1}=1.
$$

For even (L),

$$
(-1)^{L-1}=-1.
$$

This distinction is relevant to the modular digit-reversal identity:

$$
\boxed{
R(n)\equiv(-1)^{L-1}n\pmod{11}.
}
$$

⸻

7. Research Terminology

Definition 7.1: Lychrel Candidate

A Lychrel candidate is a positive integer for which repeated reverse-and-add iteration has not produced a palindrome within the computational range investigated.

This terminology does not establish that the sequence will never produce a palindrome.

Definition 7.2: Computational Observation

A computational observation is a result obtained through numerical calculation or computer-assisted experimentation.

Such an observation applies to the tested cases and ranges. It is not automatically a universal mathematical proof.

Definition 7.3: Mathematical Proof

A mathematical proof is a logically complete argument establishing that a statement follows from accepted definitions, assumptions and previously established results.

⸻

8. Notation Reference

Symbol	Meaning
(n)	Positive integer
(n_0)	Initial sequence value
(n_t)	Value at iteration (t)
(R(n))	Decimal digit reversal
(T(n))	Reverse-and-add transformation
(S(n))	Decimal digit sum
(L)	Number of decimal digits
(a_i)	Original decimal digit
(p_i)	Mirrored digit-pair sum
(c_i)	Incoming carry at column (i)
(e_i)	Resulting decimal digit
(C(n))	Total carry count
(m)	Positive modulus
(t)	Iteration index

⸻

9. Consistency Statement

All mathematical notation in the research paper should follow the definitions established in this document.

In particular:

1. Digit positions are indexed from zero, beginning with the units digit.
2. The number of decimal digits is denoted by (L).
3. The reverse-and-add transformation is denoted by (T(n)).
4. The digit reversal function is denoted by (R(n)).
5. The total carry count includes the final outgoing carry.
6. Computational observations are distinguished from proven mathematical statements.

These conventions are intended to ensure clarity and consistency throughout the investigation.
