Preliminary Novelty Review

Project: Reverse-and-Add Dynamics
Author: Subharambha Lamsal
Review status: Preliminary
Review date: 3 November 2026

⸻

1. Purpose

The purpose of this document is to examine whether the mathematical ideas developed in this investigation have already appeared in existing mathematical literature or publicly available research.

The investigation focuses on:

1. The carry-based digit-sum identity.
2. The modular digit-reversal identity modulo 11.
3. The parity-dependent behaviour of reverse-and-add transformations.
4. The use of mirrored digit-pair sums and carry propagation.
5. The application of these properties to the number 196.

The objective is to distinguish established mathematical knowledge from potentially less-explored observations.

⸻

2. Existing Research on Reverse-and-Add Dynamics

Reverse-and-add sequences have been studied for many decades.

The number 196 is a well-known example of a Lychrel candidate. Its trajectory has been investigated extensively, but no palindrome has been established.

The On-Line Encyclopedia of Integer Sequences documents the sequence beginning with 196.

Reference:

OEIS A006960: Reverse and Add sequence starting with 196

Wolfram MathWorld also documents the 196 algorithm and the terminology associated with Lychrel candidates.

Reference:

Wolfram MathWorld: Lychrel Number

Novelty assessment: The reverse-and-add process, the 196 problem and the general investigation of Lychrel candidates are established topics. They are not original contributions of this project.

⸻

3. Existing Modular Results

An important observation in this investigation is that even-length decimal numbers produce reverse-and-add results divisible by 11.

This is not a new observation.

The On-Line Encyclopedia of Integer Sequences explicitly records the property that if an integer has an even number of decimal digits, its reverse-and-add result is divisible by 11.

Reference:

OEIS A056964: Number plus its digit reversal

The project develops a more general algebraic expression:

$$
R(n)\equiv(-1)^{L-1}n\pmod{11}.
$$

This expression also explains the odd-length case.

However, the underlying result follows directly from the familiar congruence

$$
10\equiv-1\pmod{11}.
$$

Novelty assessment: The modular behaviour is mathematically valid, but its historical originality has not been established. The even-length divisibility consequence is already documented.

⸻

4. Existing Carry-Based Research

A particularly relevant discovery emerged during this review.

A publicly available 2026 GitHub project titled:

Carry Asymmetry, Palindrome Characterization, and Conditional Non-Convergence in the Reverse-and-Add Process

investigates carry asymmetry, mirrored digit-pair sums and palindrome formation in reverse-and-add transformations.

Reference:

GitHub: 196 Carry Asymmetry

The project describes structural results involving carry propagation and conditions under which a reverse-and-add transformation produces a palindrome.

This is a substantial overlap with the general direction of the present investigation.

It does not automatically establish that every identity derived here is already contained in that work. Nevertheless, it means that carry-based analysis of reverse-and-add dynamics cannot reasonably be presented as a new research direction.

Novelty assessment: The broad structural approach is already explored in publicly available research. A detailed comparison of the actual mathematical statements is still necessary.

⸻

5. Assessment of the Carry-Based Digit-Sum Identity

The present investigation establishes

$$
S(T(n))=2S(n)-9C(n).
$$

The identity follows from two elementary facts:

1. Every original digit appears twice in the sum of the mirrored digit-pair sums.
2. Every carry-out reduces the total digit sum by nine.

The identity is mathematically established in proofs.md.

A targeted search for the exact notation and wording of this identity did not establish whether an identical formula has appeared in earlier literature.

However, the absence of an exact search result is not evidence of originality.

The identity is a natural consequence of decimal addition and carry propagation. It may be known in an equivalent form even if the notation differs.

Novelty assessment: The identity is proven within this project. Its historical originality remains unverified.

⸻

6. Assessment of Mirrored Digit-Pair Analysis

The investigation defines

$$
p_i=a_i+a_{L-1-i}.
$$

These quantities represent the sums of digits occupying mirrored decimal positions.

This representation is useful because it separates the initial symmetry of the addition from the effects of carry propagation.

However, the 2026 carry-asymmetry project also studies mirrored digit-pair sums and carry structures.

Consequently, this general approach should not be claimed as an original discovery without a more detailed comparison.

Novelty assessment: The representation is useful, but its originality is not established.

⸻

7. Historical and Mathematical Limitations

This review has several limitations.

* It is not a systematic review of all mathematical publications.
* Not every relevant journal, book, thesis or unpublished manuscript has been examined.
* The exact equivalence of the carry-based identity to previously published formulas has not been determined.
* The publicly available 2026 GitHub project requires a detailed theorem-by-theorem comparison.
* No claim is made that the current investigation solves the 196 problem.

A complete originality assessment would require examining the full mathematical arguments in relevant sources, not merely comparing titles or abstracts.

⸻

8. Summary of Novelty Assessment

Research component	Current assessment
Reverse-and-add process	Established
196 Lychrel problem	Established open problem
Even-length divisibility by 11	Previously documented
General modulo 11 reversal identity	Valid derivation; historical novelty unverified
Carry-based digit-sum identity	Proven here; historical novelty unverified
Mirrored digit-pair representation	Existing related research identified
Application to 196	Established computational trajectory
Proof that 196 never reaches a palindrome	Not achieved

⸻

9. Future Research Directions

Further work should focus on mathematical depth rather than making unsupported claims of originality.

Potential directions include:

1. Compare the carry-based digit-sum identity with existing carry-analysis results.
2. Examine whether the identity can produce useful bounds on digit sums over multiple iterations.
3. Investigate relationships between carry patterns and palindrome formation.
4. Explore whether additional modular invariants provide restrictions not already known.
5. Search for a precise theorem that extends existing results rather than merely restating them.

Any proposed new result should be accompanied by a complete proof and a comparison with prior work.

⸻

10. Final Assessment

This project contains mathematically valid derivations and reproducible computational observations.

However, the available evidence does not justify describing the investigation as a historically original solution or discovery.

The carry-based digit-sum identity is a proven result within this work, but its priority and originality remain unresolved.

The modular properties are closely connected to established divisibility rules and previously documented reverse-and-add results.

The most responsible description of this project is therefore:

An independent mathematical investigation of carry propagation, digit sums and modular structure in reverse-and-add dynamics, with historical originality still under review.

This distinction between mathematical correctness and historical novelty is essential to responsible mathematical research.
