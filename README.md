# QAP Assignment

Calculate QAP step by step for the given equation. Fill in the values in this markdown to complete the assignment

$$
x^2-x-42 == 0
$$

## Gates

- $x * x = sym_1$
- $x + 42 = sym_2$
- $(sym_2)(-1) = sym_3$
- $sym_1 + sym_3 = out$


## Symbols

symbols = [~one, x, out, $sym_1$, $sym_2$, $sym_3$]

## Solution Vector

$\vec{s}$ = [1, 7, 0, 49, 49, -49]

## R1CS

### Gate #1

$$ \vec{a} = [0, 1, 0, 0, 0, 0] $$

$$ \vec{b} = [0, 1, 0, 0, 0, 0] $$

$$ \vec{c} = [0, 0, 0, 1, 0, 0] $$


### Gate #2

$$ \vec{a} = [42, 1, 0, 0, 0, 0] $$

$$ \vec{b} = [1, 0, 0, 0, 0, 0] $$

$$ \vec{c} = [0, 0, 0, 0, 1, 0] $$


### Gate #3

$$ \vec{a} = [0, 0, 0, 0, 1, 0] $$

$$ \vec{b} = [-1, 0, 0, 0, 0, 0] $$

$$ \vec{c} = [0, 0, 0, 0, 0, 1] $$


### Gate #4

$$ \vec{a} = [0, 0, 0, 1, 0, 1] $$

$$ \vec{b} = [1, 0, 0, 0, 0, 0] $$

$$ \vec{c} = [0, 0, 1, 0, 0, 0] $$


## Constraint Matrices

$$
A = \begin{bmatrix}
0 & 1 & 0 & 0 & 0 & 0 \\
42 & 1 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1 & 0 & 1 \\
\end{bmatrix}
$$

$$
B = \begin{bmatrix}
0 & 1 & 0 & 0 & 0 & 0 \\
1 & 0 & 0 & 0 & 0 & 0 \\
-1 & 0 & 0 & 0 & 0 & 0 \\
1 & 0 & 0 & 0 & 0 & 0 \\
\end{bmatrix}
$$

$$
C = \begin{bmatrix}
0 & 0 & 0 & 1 & 0 & 0 \\
0 & 0 & 0 & 0 & 1 & 0 \\
0 & 0 & 0 & 0 & 0 & 1 \\
0 & 0 & 1 & 0 & 0 & 0 \\
\end{bmatrix}
$$

## QAP

$$
A(x) = \begin{bmatrix}
21x^3 -168x^2 + 399x - 252 
\\
\\
\frac{1}{3}x^3 - \frac{5}{2}x^2 + \frac{31}{6}x - 2 
\\ 
\\
0  
\\ 
\\
\frac{1}{6}x^3 - x^2 + \frac{11}{6}x - 1 
\\
\\
\frac{-1}{2}x^3 + \frac{7}{2}x^2 - 7x + 4  
\\
\\
\frac{1}{6}x^3 - x^2 + \frac{11}{6}x - 1  
\\
\\
\end{bmatrix}
$$

$$
B(x) = \begin{bmatrix}
\frac{7}{6}x^3 -\frac{17}{2}x^2 + \frac{55}{3}x - 11 
\\
\\
\frac{-1}{6}x^3 + \frac{3}{2}x^2 - \frac{13}{3}x + 4 
\\ 
\\
0  
\\ 
\\
0
\\
\\
0
\\
\\
0
\\
\\
\end{bmatrix}
$$

$$
C(x) = \begin{bmatrix}
0
\\
\\
0
\\ 
\\
\frac{1}{6}x^3 - x^2 + \frac{11}{6}x - 1 
\\ 
\\
\frac{-1}{6}x^3 + \frac{3}{2}x^2 - \frac{13}{3}x + 4 
\\
\\
\frac{1}{2}x^3 -4x^2 + \frac{19}{2}x - 6 
\\
\\
\frac{-1}{2}x^3 + \frac{7}{2}x^2 - 7x + 4
\\
\\
\end{bmatrix}
$$



$$A(x).\vec{s} = \frac{-7}{6}x^3 -14x^2 + \frac{553}{6}x - 70$$


$$B(x).\vec{s} = 2x^2 -12x + 17$$


$$C(x).\vec{s} = \frac{245}{6}x^3 -294x^2 + \frac{3577}{6}x - 294$$

$$A(x).\vec{s} * B(x).\vec{s} - C(x).\vec{s} = \frac{7}{3}x^5 -14x^4 + \frac{875}{3}x^3 - 1190x^2 + \frac{5432}{3}x - 896$$
$$A(x).\vec{s} * B(x).\vec{s} - C(x).\vec{s} = \frac{-7}{3}(x-1)(x-2)(x-3)(x-4)(x+16)$$


Since the above polynomial is equal to $H(x).Z(x)$ it should have roots at x = 1, 2, 3, 4. Verify the same by pasting the polynomial [here](https://www.wolframalpha.com/).

## Evaluation

-   Clone this repo.

    ```
    git clone https://github.com/DappCamp-Assignments/f79ca319bd4c68503d8ccb662126d4a5f82098a05519b1585b9c11b5eca39551
    ```

-   Create a new branch with your name. You can use the following command

    ```
    git checkout -b satyajeet-sindhiyani
    ```

-  Fill in the values in this file with your solution

-   Create a pull request from your branch to the main branch of the repo

-   Since this assignment is manually evaluated we will provide feedback on your solution in form of pull request comments
