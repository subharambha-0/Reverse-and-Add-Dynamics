
Computational Results: Reverse-and-Add Dynamics

Author: Subharambha Lamsal
Project: Reverse-and-Add Dynamics
Primary test case: 196

⸻

1. Purpose

This document records computational observations concerning reverse-and-add sequences.

The experiments focus on:

1. The initial trajectory of 196.
2. Decimal digit reversal.
3. Carry propagation.
4. Verification of the digit-sum identity.
5. Modular behaviour modulo 11.

The purpose is to provide reproducible numerical evidence supporting the mathematical investigation.

Computational observations are not treated as universal mathematical proofs.

⸻

2. Initial Trajectory of 196

Starting with

$$
n_0=196,
$$

apply the reverse-and-add transformation

$$
n_{t+1}=n_t+R(n_t).
$$

The first three iterations are:

Iteration 1

$$
196+691=887.
$$

Therefore,

$$
n_1=887.
$$

Iteration 2

$$
887+788=1675.
$$

Therefore,

$$
n_2=1675.
$$

Iteration 3

$$
1675+5761=7436.
$$

Therefore,

$$
n_3=7436.
$$

Summary

Iteration	Original number	Reversed number	Result
0	196	691	887
1	887	788	1675
2	1675	5761	7436

Thus, the observed trajectory is

$$
\boxed{196\rightarrow887\rightarrow1675\rightarrow7436.}
$$

⸻

3. Modular Computation

Consider the first four terms:

$$
196,\quad887,\quad1675,\quad7436.
$$

Their residues modulo 11 are:

Number	Division by 11	Remainder
196	(11(17)+9)	9
887	(11(80)+7)	7
1675	(11(152)+3)	3
7436	(11(676)+0)	0

Therefore,

$$
196\equiv9\pmod{11},
$$

$$
887\equiv7\pmod{11},
$$

$$
1675\equiv3\pmod{11},
$$

and

$$
7436\equiv0\pmod{11}.
$$

The third transformation produces a multiple of 11.

Since divisibility by 11 is preserved under reverse-and-add transformations, every subsequent term remains divisible by 11.

This is also established mathematically in proofs.md.

⸻

4. Carry Propagation Experiment

Consider the first transformation:

$$
196+691=887.
$$

The original digits, written from least significant to most significant, are

$$
(6,9,1).
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

The carry calculations are:

Column	Pair sum	Incoming carry	Result digit	Outgoing carry
0	7	0	7	0
1	18	0	8	1
2	7	1	8	0

The resulting number is

$$
887.
$$

The total carry count is

$$
C(196)=0+1+0=1.
$$

⸻

5. Computational Verification of the Digit-Sum Identity

The identity investigated in this project is

$$
S(T(n))=2S(n)-9C(n).
$$

For the number 196,

$$
S(196)=1+9+6=16.
$$

The total carry count is

$$
C(196)=1.
$$

Substituting,

$$
S(T(196))=2(16)-9(1).
$$

Therefore,

$$
S(T(196))=23.
$$

Direct calculation gives

$$
S(887)=8+8+7=23.
$$

Hence, the computational result agrees with the identity:

$$
\boxed{23=23.}
$$

This example verifies the calculation for one input. The general identity is established by the proof in proofs.md.

⸻

6. Reproducible Python Experiment

The following Python program reproduces the initial trajectory and checks the digit-sum identity for a finite collection of positive integers.

def reverse_number(n):
    return int(str(n)[::-1])
def digit_sum(n):
    return sum(int(digit) for digit in str(n))
def carry_count(n):
    digits = [int(d) for d in str(n)[::-1]]
    length = len(digits)
    carry = 0
    total_carries = 0
    for i in range(length):
        pair_sum = digits[i] + digits[length - 1 - i]
        carry = (pair_sum + carry) // 10
        total_carries += carry
    return total_carries
def reverse_add(n):
    return n + reverse_number(n)
# Display the initial trajectory of 196
n = 196
for step in range(4):
    print(step, n)
    if step < 3:
        n = reverse_add(n)
# Verify the digit-sum identity on a finite test range
for n in range(1, 10001):
    result = reverse_add(n)
    left_side = digit_sum(result)
    right_side = 2 * digit_sum(n) - 9 * carry_count(n)
    assert left_side == right_side
print("All tested cases satisfy the identity.")

Interpretation

The program performs two experiments:

1. It calculates the first three reverse-and-add transformations beginning with 196.
2. It checks the digit-sum identity for every integer from 1 through 10,000.

If the program completes without an assertion error, all tested cases satisfy the identity.

This finite verification is supplementary evidence. It does not replace the general mathematical proof.

⸻

7. Observations

The experiments establish the following computational observations:

1. The initial trajectory of 196 reaches 7436 after three transformations.
2. The number 7436 is divisible by 11.
3. The carry calculation for (196+691) produces exactly one carry.
4. The digit-sum identity agrees with the direct calculation for this example.
5. The provided program checks the identity over a finite range of 10,000 positive integers.

The modular preservation result is stronger than the finite computation because it follows from a general mathematical proof.

⸻

8. Limitations

The experiments in this document have several limitations.

* A finite computational search cannot establish the behaviour of infinitely many iterations.
* Checking 10,000 inputs does not independently prove a universal identity.
* Divisibility by 11 does not prevent palindrome formation.
* The calculations do not establish that 196 never reaches a palindrome.
* No claim is made that the computational observations are historically novel.

⸻

9. Conclusion

The computational experiments provide reproducible examples of reverse-and-add dynamics.

They demonstrate the initial behaviour of 196, illustrate carry propagation and verify the digit-sum identity over a finite test range.

The results complement the mathematical proofs in proofs.md.

The central unresolved question remains whether the sequence beginning with 196 ever reaches a palindrome.

No solution to that question is claimed in this document.
