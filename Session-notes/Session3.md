
# Session 3 - Matrix Multiplication and Composition

## Recap of matrix definition

A linear transformation is essentially a function that takes a vector as input and gives a vector as output.

Geometrically, a transformation is called "linear" if it 
1) Keeps grid lines parallel and evenly spaced
2) Keeps the origin fixed

We could fully describe a linear transformation using only four numbers: the coordinates of our basis vectors (in higher dimensions, it would be more than four numbers, but the concept remains the same).

So we defined a matrix as a collection of the coordinates of the basis vectors in a space. Then, we can find the coordinates of a vector after undergoing a linear transformation by multiplying that vector by the matrix representing the linear transformation.

Since we know that a matrix is nothing but the coordinates of vectors, it made the idea of matrix-vector multiplication much more intuitive.

$$\begin{bmatrix} a & b \\\ c & d \\\ \end{bmatrix}\begin{bmatrix}x \\\ y \\\ \end{bmatrix} = x\begin{bmatrix}a \\\ c \\\ \end{bmatrix} + y\begin{bmatrix}b \\\ d \\\ \end{bmatrix} = \begin{bmatrix}ax + by \\\ cx + dy \\\ \end{bmatrix}$$

## Composition of Linear Transformations

Sometimes, we want to track where the basis vectors end up after applying TWO linear transformations one after the other.
The net result of these two transformations is the same as one distinct linear transformation that is called the "composition" of the two smaller transformations.

Example: Consider the transformations $L_1$ and $L_2$.
$L_1$ is a stretch of the x-axis and $L_2$ is a shear.

$$L_1 = \begin{bmatrix} 3 & 0 \\\ 0 & 1 \\\ \end{bmatrix}.$$
$$L_2 = \begin{bmatrix} 1 & 1 \\\ 0 & 1 \\\ \end{bmatrix}.$$

$$Applying \ L_1 \ and \ then \ L_2 \ to \ a \ vector \vec{v} = \begin{bmatrix} x \\\ y \\\ \end{bmatrix}:$$

$$\begin{bmatrix} 1 & 1 \\\ 0 & 1 \\\ \end{bmatrix}\Bigg(\begin{bmatrix} 3 & 0 \\\ 0 & 1 \\\ \end{bmatrix}\begin{bmatrix} x \\\ y \\\ \end{bmatrix}\Bigg)$$

$$The \ composition \ of \ L_1 \ and \ L_2 \ can \ be \ defined \ by \ the \ matrix:$$
$$\begin{bmatrix} 3 & 1 \\\ 0 & 1 \\\ \end{bmatrix}.$$

$$\begin{bmatrix} 1 && 1 \\\ 0 & 1 \\\ \end{bmatrix}\Bigg(\begin{bmatrix} 3 & 0 \\\ 0 & 1 \\\ \end{bmatrix}\begin{bmatrix} x \\\ y \\\ \end{bmatrix}\Bigg) \\ = \\ \begin{bmatrix} 3 & 1 \\\ 0 & 1 \\\ \end{bmatrix}\begin{bmatrix} x \\\ y \\\ \end{bmatrix}.$$

It follows that 

$$\underbrace{\begin{bmatrix} 1 & 1 \\\ 0 & 1 \\\ \end{bmatrix}}_{\text{shear}}\underbrace{\begin{bmatrix} 3 & 0 \\\ 0 & 1 \\\ \end{bmatrix}}_{\text{stretch}} \\ = \\ \underbrace{\begin{bmatrix} 3 & 1 \\\ 0 & 1 \\\ \end{bmatrix}}_{\text{composition}}.$$

Therefore, we can actually define matrix multiplication.

## Matrix-Matrix Multiplication

Matrix multiplication is really just applying the linear transformations described by each of the matrices to a space one after another.

The order of the transformations simply read right-to-left algebraically. This is not a big surprise, considering that linear transformations are very much like functions, and functions are also read right-to-left.

$$\underleftarrow{f(g(h(x)))}$$

Fortunately, we're developers, so we're used to this way of reading function calls.

$$Computationally, \ looking \ at \ \begin{bmatrix} 1 & 1 \\\ 0 & 1 \\\ \end{bmatrix}\begin{bmatrix} 3 & 0 \\\ 0 & 1 \\\ \end{bmatrix}, \
we \ consider \ the \ matrix \ on \ the \ right \ as \ the \ basis \ vectors \ that \ they \ represent.$$

$$new \ \widehat{i} = \begin{bmatrix} 3 \\\ 0 \\\ \end{bmatrix}, \ \widehat{j} = \begin{bmatrix} 0 \\\ 1 \\\ \end{bmatrix}.$$

Applying the transformation on the left to these two vectors:

$$\begin{rcases}\begin{bmatrix} 1 & 1 \\\ 0 & 1 \\\ \end{bmatrix}\begin{bmatrix}3 \\\ 0 \\\ \end{bmatrix} = 3\begin{bmatrix} 1 \\\ 0 \\\ \end{bmatrix} + 0\begin{bmatrix}1 \\\ 1 \\\ \end{bmatrix} = \begin{bmatrix} 3 \\\ 0 \\\ \end{bmatrix}, \\\\
\begin{bmatrix} 1 & 1 \\\ 0 & 1 \\\ \end{bmatrix}\begin{bmatrix}0 \\\ 1 \\\ \end{bmatrix} = 0\begin{bmatrix} 1 \\\ 0 \\\ \end{bmatrix} + 1\begin{bmatrix}1 \\\ 1 \\\ \end{bmatrix} = \begin{bmatrix} 1 \\\ 1 \\\ \end{bmatrix}.\end{rcases} ⇒ \begin{bmatrix} 3 & 1 \\\ 0 & 1 \\\ \end{bmatrix}$$

Putting those two resultant vectors into one structure, just like we did before, gives us the matrix that's equivalent to the composition of the two linear transformations.

Generically, 

$$\begin{bmatrix} a & b \\\ c & d \\\ \end{bmatrix}\begin{bmatrix} e & f \\\ g & h \\\ \end{bmatrix} = $$

$$\begin{rcases}\begin{bmatrix} a & b \\\ c & d \\\ \end{bmatrix}\begin{bmatrix}e \\\ g \\\ \end{bmatrix} = e\begin{bmatrix} a \\\ c \\\ \end{bmatrix} + g\begin{bmatrix}b \\\ d \\\ \end{bmatrix} = \begin{bmatrix} ae + bg \\\ ce + dg \\\ \end{bmatrix}, \\\\
\begin{bmatrix} a & b \\\ c & d \\\ \end{bmatrix}\begin{bmatrix}f \\\ h \\\ \end{bmatrix} = f\begin{bmatrix} a \\\ c \\\ \end{bmatrix} + h\begin{bmatrix}b \\\ d \\\ \end{bmatrix} = \begin{bmatrix} af + bh \\\ cf + dh \\\ \end{bmatrix}.\end{rcases} ⇒ \begin{bmatrix} ae + bg & af + bh \\\ ce + dg & cf + dh \\\ \end{bmatrix}.$$

Yet again, this is usually taught as something that should just be memorised.

But we've been able to derive it using the intuition we've built up about vectors and matrices.

Question: Does the order of matrix multiplication matter? In other words, is $M_1M_2 = M_2M_1$?

Another way to think about this question: can we think of two linear transformations that, after applying one after another, DOESN'T end up at the send spot?

Example: Let's consider a shear, then a 90 degree rotation.

$$Shear: \begin{bmatrix} 1 & 1 \\\ 0 & 1 \\\ \end{bmatrix}, \\\\ \ Rotation: \begin{bmatrix} 0 & -1 \\\ 1 & 0 \\\ \end{bmatrix}.$$

### First shear, then rotate

Note that we read the order of the linear transformations from right to left, so the shear will be on the right.

$$\begin{bmatrix} 0 & -1 \\\ 1 & 0 \\\ \end{bmatrix} \begin{bmatrix} 1 & 1 \\\ 0 & 1 \\\ \end{bmatrix} = \begin{bmatrix} 0(1) + -1(0) & 0(1) + -1(1) \\\ 1(1) + 0(0) & 1(1) + 0(1) \\\ \end{bmatrix} = \begin{bmatrix} 0 & -1 \\\ 1 & 1 \\\ \end{bmatrix}.$$

### First rotate, then shear

$$\begin{bmatrix} 1 & 1 \\\ 0 & 1 \\\ \end{bmatrix}\begin{bmatrix} 0 & -1 \\\ 1 & 0 \\\ \end{bmatrix}  = \begin{bmatrix} 1(0) + 1(1) & 1(-1) + 1(0) \\\ 0(0) + 1(1) & 0(-1) + 1(0) \\\ \end{bmatrix} = \begin{bmatrix} 1 & -1 \\\ 1 & 0 \\\ \end{bmatrix}.$$

$$\begin{bmatrix} 0 & -1 \\\ 1 & 1 \\\ \end{bmatrix} \ne \begin{bmatrix} 1 & -1 \\\ 1 & 0 \\\ \end{bmatrix}.$$

So $M_1M_2 \ne M_2M_1$. 

### Example

$$Let \ A \ = \ \begin{bmatrix} 2 & 3 \\\ 1 & 0 \\\ \end{bmatrix} \ and \ B = \begin{bmatrix} 1 & 2 \\\ 0 & 1 \\\ \end{bmatrix}.$$ 

Find AB.

$$\begin{bmatrix} 2 & 3 \\\ 1 & 0 \\\ \end{bmatrix}\begin{bmatrix} 1 & 2 \\\ 0 & 1 \\\ \end{bmatrix} = \begin{bmatrix} 2(1) + 3(0) & 2(2) + 3(1) \\\ 1(1) + 0(0) & 1(2) + 0(1) \\\ \end{bmatrix} = \begin{bmatrix} 2 & 7 \\\ 1 & 2 \\\ \end{bmatrix}.$$

### Excercise

$$1) \ Let \ A = \begin{bmatrix} 3 & 4 \\\ -2 & 5 \\\ \end{bmatrix}, B = \begin{bmatrix} 1 & 0 \\\ 0 & 1 \\\ \end{bmatrix}. \ Find \ AB.$$

$$2) \ Let \ A = \begin{bmatrix} 2 & 3 & 4 \\\ 0 & 1 & -1 \\\ 2 & 0 & 1 \\\ \end{bmatrix}, B = \begin{bmatrix} 0 & 6 & 2 \\\ 4 & 1 & 0 \\\ -1 & 2 & 4 \\\ \end{bmatrix}.$$           
$$A) \ Find \ AB. $$
$$B) \ Find \ BA.$$          

### Excercise Solutions

$$1) \ AB = \begin{bmatrix} 3 & 4 \\\ -2 & 5 \\\ \end{bmatrix}.$$

$$2A) \ AB = \begin{bmatrix} 8 & 23 & 29 \\\ 5 & -1 & -4 \\\ -1 & 14 & 8 \\\ \end{bmatrix}.$$

$$2B) \ BA = \begin{bmatrix} 4 & 6 & -4 \\\ 8 & 13 & 15 \\\ 6 & -1 & -2 \\\ \end{bmatrix}.$$
