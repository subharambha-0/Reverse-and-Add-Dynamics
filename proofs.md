Mathematical Proofs: Reverse-and-Add Dynamics

Author: Subharambha Lamsal
Research: Reverse-and-Add Dynamics

⸻

1. Introduction

This document presents the formal mathematical proofs of the principal results developed in this investigation.

The proofs concern:

1. The carry-based digit-sum identity.
2. The modular relationship between a number and its decimal reversal.
3. The parity-dependent modular behaviour of reverse-and-add transformations.
4. The preservation of divisibility by 11.

All decimal digit positions are indexed from zero, beginning with the units position.

⸻

2. Preliminary Definitions

Let (n) be a positive integer with exactly (L) decimal digits.

Write

$$
n=\sum_{i=0}^{L-1}a_i10^i,
$$

where

$$
a_i\in{0,1,\ldots,9}.
$$

Define its decimal reversal by

$$
R(n)=\sum_{i=0}^{L-1}a_{L-1-i}10^i.
$$

The reverse-and-add transformation is

$$
T(n)=n+R(n).
$$

The decimal digit sum is denoted by (S(n)).

Define the mirrored digit-pair sums:

$$
p_i=a_i+a_{L-1-i}.
$$

During addition, let (c_i) denote the carry entering column (i), with

$$
c_0=0.
$$

The outgoing carry and resulting digit are

$$
c_{i+1}

\left\lfloor
\frac{p_i+c_i}{10}
\right\rfloor
$$

and

$$
e_i=p_i+c_i-10c_{i+1}.
$$

Finally, define the total carry count:

$$
C(n)=\sum_{i=1}^{L}c_i.
$$

⸻

3. Theorem 1: Carry-Based Digit-Sum Identity

Statement

For every positive integer (n),

$$
\boxed{
S(T(n))=2S(n)-9C(n).
}
$$

Here, (C(n)) is the total number of carry-outs during the addition of (n) and (R(n)).

Proof

From the decimal representations of (n) and (R(n)),

$$
T(n)

\sum_{i=0}^{L-1}
(a_i+a_{L-1-i})10^i.
$$

Using the definition of (p_i),

$$
T(n)=\sum_{i=0}^{L-1}p_i10^i.
$$

The sum of all mirrored pair sums is

$$
\sum_{i=0}^{L-1}p_i

\sum_{i=0}^{L-1}
(a_i+a_{L-1-i}).
$$

The first part contributes every digit of (n) exactly once:

$$
\sum_{i=0}^{L-1}a_i=S(n).
$$

The second part also contributes every digit exactly once:

$$
\sum_{i=0}^{L-1}a_{L-1-i}=S(n).
$$

Therefore,

$$
\boxed{
\sum_{i=0}^{L-1}p_i=2S(n).
}
$$

Now consider the carry recurrence:

$$
e_i=p_i+c_i-10c_{i+1}.
$$

Summing over all (L) columns gives

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

The final carry (c_L), when nonzero, is the leading digit of the resulting integer.

Thus,

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

Collecting the carry terms,

$$
S(T(n))

2S(n)

9\sum_{i=1}^{L}c_i.
$$

By the definition of (C(n)),

$$
\boxed{
S(T(n))=2S(n)-9C(n).
}
$$

This completes the proof. (\square)

⸻

4. Theorem 2: Modular Digit-Reversal Identity

Statement

If (n) has (L) decimal digits, then

$$
\boxed{
R(n)\equiv(-1)^{L-1}n\pmod{11}.
}
$$

Proof

The decimal representation of (n) is

$$
n=\sum_{i=0}^{L-1}a_i10^i.
$$

Since

$$
10\equiv-1\pmod{11},
$$

we have

$$
10^i\equiv(-1)^i\pmod{11}.
$$

Therefore,

$$
n\equiv
\sum_{i=0}^{L-1}a_i(-1)^i
\pmod{11}.
$$

The reversed integer is

$$
R(n)=
\sum_{i=0}^{L-1}a_{L-1-i}10^i.
$$

Consequently,

$$
R(n)\equiv
\sum_{i=0}^{L-1}
a_{L-1-i}(-1)^i
\pmod{11}.
$$

Introduce the substitution

$$
j=L-1-i.
$$

Then

$$
R(n)\equiv
\sum_{j=0}^{L-1}
a_j(-1)^{L-1-j}
\pmod{11}.
$$

Using

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

But the summation is congruent to (n) modulo 11.

Therefore,

$$
\boxed{
R(n)\equiv(-1)^{L-1}n\pmod{11}.
}
$$

This completes the proof. (\square)

⸻

5. Theorem 3: Parity-Dependent Reverse-and-Add Congruence

Statement

For a positive integer (n) with (L) decimal digits,

$$
\boxed{
T(n)\equiv
\begin{cases}
2n\pmod{11}, & L\text{ odd},\
0\pmod{11}, & L\text{ even}.
\end{cases}
}
$$

Proof

By definition,

$$
T(n)=n+R(n).
$$

Applying Theorem 2,

$$
T(n)\equiv
n+(-1)^{L-1}n
\pmod{11}.
$$

There are two possible cases.

Case 1: (L) is odd.

Then (L-1) is even, so

$$
(-1)^{L-1}=1.
$$

Thus,

$$
T(n)\equiv n+n\pmod{11}.
$$

Hence,

$$
\boxed{T(n)\equiv2n\pmod{11}.}
$$

Case 2: (L) is even.

Then (L-1) is odd, so

$$
(-1)^{L-1}=-1.
$$

Thus,

$$
T(n)\equiv n-n\pmod{11}.
$$

Hence,

$$
\boxed{T(n)\equiv0\pmod{11}.}
$$

Combining both cases proves the theorem. (\square)

⸻

6. Corollary 1: Preservation of Divisibility by 11

Statement

If a positive integer (n) is divisible by 11, then its reverse-and-add transformation is also divisible by 11.

That is,

$$
11\mid n
\quad\Longrightarrow\quad
11\mid T(n).
$$

Proof

Suppose

$$
11\mid n.
$$

Then

$$
n\equiv0\pmod{11}.
$$

By Theorem 2,

$$
R(n)\equiv(-1)^{L-1}n\pmod{11}.
$$

Therefore,

$$
R(n)\equiv0\pmod{11}.
$$

Since

$$
T(n)=n+R(n),
$$

we obtain

$$
T(n)\equiv0+0\pmod{11}.
$$

Consequently,

$$
\boxed{11\mid T(n).}
$$

This completes the proof. (\square)

Consequence for Iterated Sequences

Suppose a reverse-and-add sequence contains a term (n_k) such that

$$
11\mid n_k.
$$

By Corollary 1,

$$
11\mid n_{k+1}.
$$

Applying the same result repeatedly gives

$$
\boxed{
11\mid n_t
\quad\text{for every }t\geq k.
}
$$

Thus, divisibility by 11 is preserved for all subsequent iterations.

⸻

7. Example: Carry Calculation for 196

Consider

$$
n=196.
$$

Its reversal is

$$
R(196)=691.
$$

The mirrored digit-pair sums are

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

The initial carry is

$$
c_0=0.
$$

For the first column,

$$
c_1=
\left\lfloor\frac{7+0}{10}\right\rfloor=0,
$$

$$
e_0=7.
$$

For the second column,

$$
c_2=
\left\lfloor\frac{18+0}{10}\right\rfloor=1,
$$

$$
e_1=18-10=8.
$$

For the third column,

$$
c_3=
\left\lfloor\frac{7+1}{10}\right\rfloor=0,
$$

$$
e_2=7+1=8.
$$

The resulting number is

$$
T(196)=887.
$$

The total carry count is

$$
C(196)=c_1+c_2+c_3=1.
$$

Since

$$
S(196)=16,
$$

Theorem 1 gives

$$
S(887)=2(16)-9(1).
$$

Therefore,

$$
\boxed{S(887)=23.}
$$

Direct verification gives

$$
8+8+7=23.
$$

The identity is verified for this example.

⸻

8. Application of the Modular Result to 196

The initial reverse-and-add iterations are

$$
196+691=887,
$$

$$
887+788=1675,
$$

$$
1675+5761=7436.
$$

Now,

$$
7436=11\times676.
$$

Therefore,

$$
7436\equiv0\pmod{11}.
$$

By Corollary 1, every subsequent term remains divisible by 11.

This establishes a permanent divisibility property of the sequence beginning with 196.

It does not establish that the sequence can never reach a palindrome.

For example,

$$
121=11\times11
$$

is itself a palindrome.

Thus, divisibility by 11 alone cannot rule out palindrome formation.

⸻

9. Logical Boundaries of the Results

The preceding proofs establish exact arithmetic properties. Their implications must be interpreted carefully.

The carry-based identity determines the digit sum after an individual transformation when the total carry count is known.

The modular theorem determines the relationship between a number and its reversal modulo 11.

The divisibility corollary establishes that once a sequence reaches a multiple of 11, all subsequent terms remain multiples of 11.

However, none of these results establishes that:

1. Every reverse-and-add sequence must eventually reach a palindrome.
2. Every reverse-and-add sequence must avoid palindromes.
3. The number 196 never reaches a palindrome.
4. Divisibility by 11 is incompatible with palindrome formation.

These statements remain unproved by the arguments in this document.

⸻

10. Conclusion

The investigation establishes three principal mathematical results:

Result 1:

$$
S(T(n))=2S(n)-9C(n).
$$

Result 2:

$$
R(n)\equiv(-1)^{L-1}n\pmod{11}.
$$

Result 3:

$$
11\mid n
\quad\Longrightarrow\quad
11\mid T(n).
$$

Together, these results describe aspects of carry propagation, decimal digit reversal and modular behaviour in reverse-and-add dynamics.

They provide a foundation for further investigation but do not resolve the 196 Lychrel problem.

⸻

Research Status

Mathematical statement	Status
Carry-based digit-sum identity	Proven
Modular digit-reversal identity	Proven
Parity-dependent congruence	Proven
Preservation of divisibility by 11	Proven
196 never reaches a palindrome	Unproved
Historical originality of the identities	Not yet established

All proofs are presented as mathematical derivations. Historical novelty requires a separate literature review.
