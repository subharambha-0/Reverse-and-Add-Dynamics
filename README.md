Reverse-and-Add Dynamics

A Carry-Based Analysis of Reverse-and-Add Sequences

Author: Subharambha Lamsal
Research status: Exploratory mathematical investigation
Primary example: The number 196

⸻

Abstract

This project investigates the arithmetic structure of reverse-and-add sequences, with particular attention to decimal digit symmetry, carry propagation, digit sums and modular arithmetic.

Rather than treating reverse-and-add sequences solely as computational processes, this investigation studies their underlying arithmetic properties.

The central results include a carry-based digit-sum identity and a parity-dependent modular relation modulo 11.

The number 196 is used as a principal example. However, the results presented here do not prove that 196 never reaches a palindrome.

⸻

1. Introduction

The reverse-and-add process consists of reversing the decimal digits of a positive integer and adding the reversed number to the original number.

For example,

$$
196+691=887.
$$

The resulting number is 887.

Applying the same operation again,

$$
887+788=1675.
$$

This process can be repeated indefinitely.

Some starting numbers eventually produce palindromes, while others are known as Lychrel candidates because no palindrome has been found within the computational searches performed.

The number 196 is one of the most extensively investigated examples.

This project explores the mathematical structure underlying this process.

⸻

2. Principal Mathematical Results

The investigation develops the following results.

2.1 Carry-Based Digit-Sum Identity

For a positive integer (n), define:

* (S(n)) as the sum of its decimal digits.
* (T(n)) as the result of adding (n) to its digit reversal.
* (C(n)) as the total number of carry-outs during the addition.

The following identity holds:

$$
\boxed{S(T(n))=2S(n)-9C(n)}
$$

This identity connects the digit sum of the resulting number with the carry propagation occurring during reverse-and-add addition.

2.2 Modular Arithmetic

Let (R(n)) denote the decimal digit reversal of (n), and let (L) denote the number of decimal digits of (n).

The following congruence holds:

$$
\boxed{R(n)\equiv(-1)^{L-1}n\pmod{11}}
$$

Consequently,

$$
T(n)\equiv
\begin{cases}
2n\pmod{11}, & L\text{ odd},\
0\pmod{11}, & L\text{ even}.
\end{cases}
$$

This establishes a parity-dependent modular relationship.

An important consequence is that if a term is divisible by 11, every subsequent term in its reverse-and-add sequence is also divisible by 11.

2.3 Decimal Structural Analysis

The investigation also represents reverse-and-add transformations through mirrored digit-pair sums and carry propagation.

This provides a structural way to study how decimal symmetry changes during the addition.

It does not, by itself, establish that a palindrome can never occur.

⸻

3. Application to 196

Consider the initial reverse-and-add sequence:

$$
196+691=887
$$

$$
887+788=1675
$$

$$
1675+5761=7436
$$

Notice that:

$$
7436=11\times676
$$

Therefore, the sequence reaches a number divisible by 11.

By the modular result established above, all subsequent terms remain divisible by 11.

This is a proven property of the trajectory, but it does not prove that 196 is a Lychrel number.

⸻

4. Research Objectives

The main objectives of this investigation are:

1. To derive exact arithmetic identities for reverse-and-add transformations.
2. To investigate the relationship between decimal digit sums and carry propagation.
3. To establish modular properties of digit reversal.
4. To study the structural role of mirrored digit pairs.
5. To investigate whether these properties can contribute to a deeper understanding of Lychrel candidates.

⸻

5. Research Limitations

The results presented in this repository have important limitations.

* The digit-sum identity describes carry behaviour but does not independently determine whether a palindrome will occur.
* The modulo 11 result establishes a divisibility property but does not exclude palindromes.
* Computational searches provide evidence within tested ranges, not universal proofs.
* No proof is claimed that 196 never reaches a palindrome.

The historical originality of the results has not yet been established through a comprehensive literature review.

⸻

6. Repository Structure

The repository contains the following documents:

File	Description
README.md	Project overview and principal results
paper.md	Main mathematical investigation
definitions.md	Mathematical definitions and notation
proofs.md	Detailed proofs of established identities
computational_results.md	Computational observations and examples
novelty_review.md	Discussion of originality and prior research
references.bib	Bibliography file

⸻

7. Conclusion

Reverse-and-add sequences provide an interesting setting for studying the interaction between decimal representation and number-theoretic properties.

The carry-based digit-sum identity and the parity-dependent modular relationship offer two exact mathematical descriptions of the process.

Although these results do not solve the 196 Lychrel problem, they provide a foundation for further investigation into the arithmetic structure of reverse-and-add dynamics.

⸻

8. Research Status

Established: The carry-based digit-sum identity and the modulo 11 digit-reversal congruence.

Computationally observed: The initial trajectory of 196 and its entry into the multiples of 11.

Open: Whether 196 eventually reaches a palindrome.

Originality: Further literature review is required before any claim of historical novelty can be made.

⸻

This repository is an ongoing mathematical investigation. Results are presented with the intention of distinguishing proven statements, computational observations and unresolved conjectures.
