A Carry-Based Analysis of Reverse-and-Add Dynamics

Digit-Sum Identities, Modular Invariants and Decimal Symmetry

Author: Subharambha Lamsal
Research status: Exploratory mathematical investigation

⸻

Abstract

The reverse-and-add process is a simple arithmetic transformation in which a positive integer is added to the number obtained by reversing its decimal digits. Despite its elementary definition, the process produces complicated sequences whose eventual behaviour remains unresolved for certain starting values.

This paper investigates the arithmetic structure of reverse-and-add transformations through three perspectives: decimal digit sums, carry propagation and modular arithmetic.

First, a carry-based identity is established that relates the digit sum of the resulting integer to the total number of carry-outs. Second, a parity-dependent congruence for decimal digit reversal modulo 11 is proved. Finally, these results are applied to the trajectory beginning with 196.

The results provide exact arithmetic properties of the transformation. They do not establish that 196 never reaches a palindrome.

⸻

1. Introduction

Let a positive integer be written in decimal notation. Reverse its digits and add the resulting integer to the original number.

For example,

$$
196+691=887.
$$

Repeating the transformation gives

$$
887+788=1675.
$$

The process can be repeated indefinitely.

A number that eventually produces a palindrome is said to reach a palindromic value under reverse-and-add iteration.

The number 196 is a famous example for which no palindrome has been found despite extensive computational investigation.

The purpose of this paper is not to claim a solution to the 196 problem. Instead, it examines structural properties of the transformation that may help explain its behaviour.

The central idea is to study the interaction between decimal digit symmetry and carry propagation.

⸻

2. Definitions and Notation

Let (n) be a positive integer.

Definition 2.1: Digit reversal

Let (R(n)) denote the integer obtained by reversing the decimal digits of (n).

For example,

$$
R(196)=691.
$$

Leading zeros created by reversal are discarded when interpreting the result as an integer.

Definition 2.2: Reverse-and-add transformation

Define

$$
T(n)=n+R(n).
$$

Definition 2.3: Reverse-and-add sequence

Starting from (n_0), define the sequence recursively by

$$
n_{t+1}=T(n_t).
$$

Equivalently,

$$
\boxed{n_{t+1}=n_t+R(n_t)}.
$$

Definition 2.4: Decimal digit sum

Let (S(n)) denote the sum of the decimal digits of (n).

For example,

$$
S(196)=1+9+6=16.
$$

Definition 2.5: Palindrome

A positive integer is a decimal palindrome if its decimal representation reads identically from left to right and right to left.

For example, 121 and 1331 are palindromes.

⸻

3. The Carry-Based Digit-Sum Identity

This section establishes the first principal result.

3.1 Decimal digit representation

Suppose (n) has (L) decimal digits.

Write

$$
n=\sum_{i=0}^{L-1}a_i10^i,
$$

where (a_0) is the units digit and (a_{L-1}) is the most significant digit.

The reversed integer is

$$
R(n)=\sum_{i=0}^{L-1}a_{L-1-i}10^i.
$$

Therefore,

$$
T(n)=
\sum_{i=0}^{L-1}
(a_i+a_{L-1-i})10^i.
$$

Define the mirrored digit-pair sum

$$
p_i=a_i+a_{L-1-i}.
$$

The addition can consequently be represented through the sequence of pair sums

$$
p_0,p_1,\ldots,p_{L-1}.
$$

3.2 Carry recurrence

Let (c_i) represent the carry entering decimal column (i).

Initially,

$$
c_0=0.
$$

For each column, define the output digit (e_i) and the next carry (c_{i+1}) by

$$
e_i=p_i+c_i-10c_{i+1},
$$

where

$$
c_{i+1}=
\left\lfloor
\frac{p_i+c_i}{10}
\right\rfloor.
$$

The final carry (c_L) becomes the leading digit if it is nonzero.

Define the total carry count as

$$
C(n)=\sum_{i=1}^{L}c_i.
$$

Each carry is either zero or one.

3.3 Main Theorem: Carry-Based Digit-Sum Identity

Theorem 1.

For every positive integer (n),

$$
\boxed{
S(T(n))=2S(n)-9C(n)
}
$$

where (C(n)) is the total number of carry-outs during the addition of (n) and (R(n)).

Proof

By the definition of the mirrored digit-pair sums,

$$
p_i=a_i+a_{L-1-i}.
$$

Summing over all columns gives

$$
\sum_{i=0}^{L-1}p_i

\sum_{i=0}^{L-1}
(a_i+a_{L-1-i}).
$$

Every digit of (n) appears exactly twice in this sum.

Hence,

$$
\sum_{i=0}^{L-1}p_i=2S(n).
$$

From the carry recurrence,

$$
e_i=p_i+c_i-10c_{i+1}.
$$

Summing over all columns,

$$
\sum_{i=0}^{L-1}e_i

\sum_{i=0}^{L-1}p_i
+
\sum_{i=0}^{L-1}c_i

10\sum_{i=1}^{L}c_i.
$$

Since (c_0=0),

$$
\sum_{i=0}^{L-1}c_i

\sum_{i=1}^{L-1}c_i.
$$

The final carry (c_L) must also be included as a leading digit when calculating the digit sum.

Therefore,

$$
S(T(n))

\sum_{i=0}^{L-1}e_i+c_L.
$$

Substituting the previous expression,

$$
S(T(n))

2S(n)
+
\sum_{i=1}^{L-1}c_i

10\sum_{i=1}^{L}c_i
+c_L.
$$

Collecting the carry terms gives

$$
S(T(n))

2S(n)-9\sum_{i=1}^{L}c_i.
$$

By the definition of (C(n)),

$$
\boxed{
S(T(n))=2S(n)-9C(n).
}
$$

This completes the proof.

⸻

4. Modular Arithmetic and Digit Reversal

The second principal result concerns congruences modulo 11.

4.1 Representation modulo 11

Recall that

$$
10\equiv-1\pmod{11}.
$$

Suppose

$$
n=\sum_{i=0}^{L-1}a_i10^i.
$$

Then

$$
n\equiv
\sum_{i=0}^{L-1}a_i(-1)^i
\pmod{11}.
$$

For the reversed integer,

$$
R(n)=
\sum_{i=0}^{L-1}a_{L-1-i}10^i.
$$

Therefore,

$$
R(n)\equiv
\sum_{i=0}^{L-1}a_{L-1-i}(-1)^i
\pmod{11}.
$$

Substituting (j=L-1-i),

$$
R(n)\equiv
\sum_{j=0}^{L-1}
a_j(-1)^{L-1-j}
\pmod{11}.
$$

Since

$$
(-1)^{L-1-j}

(-1)^{L-1}(-1)^j,
$$

we obtain

$$
R(n)\equiv
(-1)^{L-1}
\sum_{j=0}^{L-1}a_j(-1)^j
\pmod{11}.
$$

Thus,

$$
\boxed{
R(n)\equiv(-1)^{L-1}n\pmod{11}.
}
$$

4.2 Main Theorem: Parity-Dependent Modular Relation

Theorem 2.

For an integer (n) with (L) decimal digits,

$$
T(n)\equiv
\begin{cases}
2n\pmod{11}, & L\text{ is odd},\
0\pmod{11}, & L\text{ is even}.
\end{cases}
$$

Proof

By definition,

$$
T(n)=n+R(n).
$$

Using the previously established congruence,

$$
T(n)\equiv
n+(-1)^{L-1}n
\pmod{11}.
$$

If (L) is odd, then (L-1) is even, so

$$
(-1)^{L-1}=1.
$$

Consequently,

$$
T(n)\equiv2n\pmod{11}.
$$

If (L) is even, then (L-1) is odd, so

$$
(-1)^{L-1}=-1.
$$

Consequently,

$$
T(n)\equiv n-n\equiv0\pmod{11}.
$$

Therefore,

$$
\boxed{
T(n)\equiv
\begin{cases}
2n\pmod{11}, & L\text{ odd},\
0\pmod{11}, & L\text{ even}.
\end{cases}
}
$$

This completes the proof.

⸻

5. Divisibility by 11

The modular theorem produces an additional consequence.

Corollary 1.

If (11\mid n), then

$$
11\mid R(n).
$$

Proof

From Theorem 2’s underlying reversal congruence,

$$
R(n)\equiv(-1)^{L-1}n\pmod{11}.
$$

If (11\mid n), then

$$
n\equiv0\pmod{11}.
$$

Therefore,

$$
R(n)\equiv0\pmod{11}.
$$

Hence,

$$
11\mid R(n).
$$

Since

$$
T(n)=n+R(n),
$$

we also obtain

$$
\boxed{11\mid T(n).}
$$

Thus, divisibility by 11 is preserved under every subsequent reverse-and-add transformation once a sequence reaches a multiple of 11.

⸻

6. Application to the Number 196

Consider the sequence beginning with

$$
n_0=196.
$$

The first transformation is

$$
196+691=887.
$$

The second transformation is

$$
887+788=1675.
$$

The third transformation is

$$
1675+5761=7436.
$$

Thus,

$$
196\rightarrow887\rightarrow1675\rightarrow7436.
$$

Notice that

$$
7436=11\times676.
$$

Therefore,

$$
7436\equiv0\pmod{11}.
$$

By Corollary 1, every subsequent term in this sequence remains divisible by 11.

This gives a permanent modular property of the trajectory beginning with 196.

However, divisibility by 11 does not prevent a number from being a palindrome. For example,

$$
121=11\times11
$$

and 121 is a palindrome.

Consequently, the modular result does not establish that 196 never reaches a palindrome.

⸻

7. Structural Interpretation

The two principal results describe different aspects of reverse-and-add dynamics.

The carry-based identity shows how the digit sum changes according to the number of carry-outs.

The modular theorem shows how the parity of the decimal digit length influences the transformation modulo 11.

These results provide complementary descriptions:

1. The digit-sum identity describes local arithmetic behaviour during addition.
2. The modular theorem describes a global congruence property.
3. Mirrored digit-pair sums provide a structural representation of decimal reversal.

Together, these properties offer a framework for studying reverse-and-add sequences beyond direct numerical iteration.

Nevertheless, they do not yet provide a general criterion that determines whether a given sequence eventually reaches a palindrome.

⸻

8. Limitations and Open Questions

Several questions remain unresolved.

1. Can the carry-based digit-sum identity be used to derive stronger restrictions on possible trajectories?
2. Can the modular properties be combined with other congruences to obtain useful restrictions?
3. Can mirrored digit-pair sums provide a necessary or sufficient condition for palindrome formation?
4. Can any of these properties contribute to a proof concerning the number 196?

The present investigation does not answer these questions.

In particular, computational observations must not be confused with universal mathematical proofs.

⸻

9. Conclusion

This paper establishes two exact properties of reverse-and-add transformations.

The first is the carry-based digit-sum identity

$$
\boxed{S(T(n))=2S(n)-9C(n).}
$$

The second is the parity-dependent digit-reversal congruence

$$
\boxed{R(n)\equiv(-1)^{L-1}n\pmod{11}.}
$$

The application to 196 demonstrates that its trajectory reaches a multiple of 11 and remains within the multiples of 11 thereafter.

These findings provide a mathematical description of certain structural properties of reverse-and-add dynamics. They do not solve the 196 Lychrel problem.

Further investigation is required to determine whether these identities can lead to stronger results.

⸻

10. Research Status and Originality

The results in this paper are presented as mathematical derivations.

Their historical originality has not yet been established through a comprehensive review of existing mathematical literature.

Accordingly, no claim is made that these identities are historically new.

The principal purpose of this work is to present the derivations clearly, distinguish proven results from open questions and provide a foundation for further mathematical investigation.

⸻

References

A verified bibliography will be added after the relevant mathematical literature has been reviewed.
