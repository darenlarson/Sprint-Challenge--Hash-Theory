# Theory of Computation Sprint Challenge

## Computation

Fill out truth tables for the following expressions:

1. `(A ∨ ¬B)`   (alternate: `(A || !B)`)
```
A     B     result
-------------------
0     0       True
0     1       False
1     0       True
1     1       True
```

2. `(¬A ∨ B) ∧ ¬(A ∧ ¬B)`   (alternate: `(!A || B) && !(A && !B)`)
```
A     B     result
-------------------
0     0       True
0     1       True
1     0       False
1     1       True
```

3. `¬(A ∨ B) ∨ ( (A ∨ C) ∧ ¬(B ∨ ¬C) )`   (alternate: `!(A || B) || ( (A || C) && !(B || !C) )`)
  * (Hint: Is it possible to calculate this using code?)
```
A     B     C     result
-------------------------
0     0     0       True
0     0     1       True
0     1     0       False
0     1     1       False
1     0     0       False
1     0     1       True
1     1     0       False
1     1     1       False
```

## STRETCH GOAL

The sum of two binary digits can be represented with the following truth table:

* A + B
```
A     B     CARRY   SUM
------------------------
0     0       0      0
0     1       0      1
1     0       0      1
1     1       1      0
```
This can be represented with boolean algebra like so:

* `SUM = A ⊕ B`  (alternate: `A ^ B` or `A xor B`)
* `CARRY = A ∧ B`  (alternate: `A && B`)


How can you represent the SUM and CARRY of adding THREE digits with a truth table and in boolean algebra?

* A + B + C
```
A     B     C      carry   sum
--------------------------------
0     0     0        0      0
0     0     1        0      1
0     1     0        0      1
0     1     1        1      0
1     0     0        0      1
1     0     1        1      0
1     1     0        1      0
1     1     1        1      1
```
* SUM = is 0 if A,B,C are all 0, or if two of them are are 1; is 1 if one of A,B,C are 1, or if all them are 1
* CARRY = is 0 if A,B,C are all 0, or if only one of them are 1; is 1 if more than one of A,B,C are 1. This is bc we are adding with base 2, so we need to "carry over" if we hit 2 in the sum column.
