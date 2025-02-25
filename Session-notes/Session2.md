# Session 2 - Linear Transformations

## Definition of a linear transformation
A transformation is a set of operations that take an input vector and gives back another vector. That sounds a lot like a function, right? So why not call it a function?

It is often useful in linear algebra to think of the input vector physically moving to the output vector.

In that way, what we envision is actually that space itself is transformed such that the given input vector lands on top of the output vector. With this view, we can envision any arbitrary input vector being moved by the transformation of space in the same way to its corresponding output vector.

It's because of this notion of movement that we prefer to think about linear "transformations" rather than linear "functions".

So what makes a transformation linear?

1) All gridlines remain parallel and evenly spaced

2) The origin remains fixed


Point (1) has as a consequence that all straight lines in a space will still be straight lines after the linear transformation has been applied.

Examples of linear transformations include a rotation about the origin and X.

## Representing a linear transformation mathematically

### Basis vectors
Basis vectors are unit vectors that can span the entire vector space they occupy. In other words, any vector can be represented as a linear combination of the basis vectors in that space.

For example, in $R^2$, the basis vectors are $\widehat{\imath}$ and $\widehat{\jmath}$:

$$\widehat{\imath} = \begin{bmatrix}1 \\ 0 \\ \end{bmatrix},$$
$$\widehat{\jmath} = \begin{bmatrix}0 \\ 1 \\ \end{bmatrix}.$$

Every vector in 2-dimensions can be written as a linear combination of these two vectors.

For example: 
$$\vec{x} = \begin{bmatrix}7 \\ 3 \\\end{bmatrix}$$
$$= 7\begin{bmatrix}1 \\ 0 \\\end{bmatrix} + 3\begin{bmatrix}0 \\ 1 \\\end{bmatrix}$$
$$= 7\widehat{\imath} + 3\widehat{\jmath}\\\$$

It turns out that any linear transformation can be described simply by looking at where these basis vectors end up afterwards.

### How a transformation changes the basis vectors

Say we have a linear transformation L.

L is applied to $R^2$ and it changes space such that the unit vectors, $\widehat{\imath}$ and $\widehat{\jmath}$ now end up at:

$$new \ \widehat{\imath} = \begin{bmatrix}-1 \\ 2 \\\end{bmatrix},$$
$$new \ \widehat{\jmath} = \begin{bmatrix}3 \\ 0 \\\end{bmatrix}.$$

If we take $\vec{x}$ from the previous example and ask "where does $\vec{x}$ end up after applying L?", we can write $new \ \vec{x}$ as the same linear combination of its new basis vectors:

$$new \ \vec{x} = 7\begin{bmatrix}-1 \\ 2 \\\end{bmatrix} + 3\begin{bmatrix}3 \\ 0 \\\end{bmatrix}$$
$$=\begin{bmatrix}-7 \\ 14 \\\end{bmatrix} + \begin{bmatrix}9 \\ 0 \\\end{bmatrix}$$
$$=\begin{bmatrix}2 \\ 14 \\\end{bmatrix}.$$

Important to note:
$$\vec{x} = x_1 (\widehat{\imath}) + x_2(\widehat{\jmath})$$
$$new \ \vec{x} = x_1 (new \ \widehat{\imath}) + x_2(new \ \widehat{\jmath})$$

Generally speaking, if we take the linear transformation L:

$$L:= \begin{bmatrix}x \\ y \\\end{bmatrix} \implies x\begin{bmatrix}-1 \\ 2 \\\end{bmatrix} + y\begin{bmatrix}3 \\ 0 \\\end{bmatrix} = \begin{bmatrix}1x + 3y \\ 2x + 0y \\\end{bmatrix}$$

We can get the output vector for any given input vector.

### The basis vectors describe the transformation completely

Notice how the generic solution to the transformation above is FULLY described by only four numbers: the two coordinates of each of the new basis vectors.

Since we only need those four numbers, let's throw them together into one single structure to represent the linear transformation L.

$$\begin{bmatrix}-1 \\ 2 \\\end{bmatrix} and \begin{bmatrix}3 \\ 0 \\\end{bmatrix} \implies \begin{bmatrix}-1 & 3 \\ 2 & 0 \\\end{bmatrix}$$

Each of the columns of this structure contain the coordinates of our new basis vectors. Column 1 is new $\widehat{\imath}$, and column 2 is new $\widehat{\jmath}$.

We will call this 2x2 structure a matrix.

To determine where any input vector ends up after a linear transformation, you can multiply the first coordinate of the vector with the first column of this matrix and the second coordinate with the second column. This is equivalent to the generic solution to L above.

Even more generically, for any linear transformation performed on $\begin{bmatrix}x \\ y \\\end{bmatrix}$ with transformed basis vectors $\begin{bmatrix}a \\ c \\\end{bmatrix}$ and $\begin{bmatrix}b \\ d \\\end{bmatrix}$:

$$\begin{bmatrix} a & b \\ c & d \\\end{bmatrix}\begin{bmatrix}x \\ y \\\end{bmatrix} = x\begin{bmatrix}a \\ c \\\end{bmatrix} + y\begin{bmatrix}b \\ d \\\end{bmatrix} = \begin{bmatrix}ax + by \\ cx + dy \\\end{bmatrix}$$

Next, we leave out the middle part of the above statement (the part containing the intuitive understanding) and force students to simply memorise the formula - if we're the education department, that is.

### Conclusion

We think of a transformed vector as a linear combination of the transformed basis vectors, and the coordinates of these basis vectors are packaged together as a matrix.

So far, we've only dealt directly with matrices in 2-dimensions, but most of what we've been through also applies to higher dimensions. For example, a 3x3 matrix would represent the three coordinates of each of the three new basis vectors ($\widehat{\imath}$, $\widehat{\jmath}$ and $\widehat{k}$).

#### Example 1: $90\degree$ rotation counterclockwise.

$$\widehat{\imath} = \begin{bmatrix}1 \\ 0 \\\end{bmatrix}, \
\widehat{\jmath} = \begin{bmatrix}0 \\ 1 \\\end{bmatrix}.$$

$$new \ \widehat{\imath} = \begin{bmatrix}0 \\ 1 \\\end{bmatrix}, \
new \ \widehat{\jmath} = \begin{bmatrix}-1 \\ 0 \\\end{bmatrix}.$$

$$\begin{bmatrix}0 & -1 \\ 1 & 0 \\\end{bmatrix}\begin{bmatrix}x \\ y \\\end{bmatrix} = x\begin{bmatrix}0 \\ 1 \\\end{bmatrix} + y\begin{bmatrix}-1 \\ 0 \\\end{bmatrix} = \begin{bmatrix}-y \\ x \\\end{bmatrix}.$$

#### Example 2: Shear ($\widehat{\imath}$ is fixed, $\widehat{\jmath}$ moves).

$$\widehat{\imath} = \begin{bmatrix}1 \\ 0 \\\end{bmatrix}, \
\widehat{\jmath} = \begin{bmatrix}0 \\ 1 \\\end{bmatrix}.$$

$$new \ \widehat{\imath} = \begin{bmatrix}1 \\ 0 \\\end{bmatrix}, \
new \ \widehat{\jmath} = \begin{bmatrix}1 \\ 1 \\\end{bmatrix}.$$

$$\begin{bmatrix}1 & 1 \\ 0 & 1 \\\end{bmatrix}\begin{bmatrix}x \\ y \\\end{bmatrix} = x\begin{bmatrix}1 \\ 0 \\\end{bmatrix} + y\begin{bmatrix}1 \\ 1 \\\end{bmatrix} = \begin{bmatrix}x + y \\ y \\\end{bmatrix}.$$

This type of movement is also called "transvection".

### Matrix operations

Now that we know what a matrix is made of, we can easily derive basic operations that can be performed on matrices from what we know about vectors.

Matrix addition: Since the columns of the matrix are each a vector, matrix addition works just like adding two vectors together, but per column.

$$\begin{bmatrix}x & a \\ y & b \\\end{bmatrix} + \begin{bmatrix}v & d \\ w & e \\\end{bmatrix} = \begin{bmatrix}x + v & a + d \\ y + w & b + e \\\end{bmatrix}.$$

Or more formally, for an m x n matrix:
$$(A + B)_{i,j} = A_{i,j} + B_{i,j} \\ 1 \le i \le m,\\ 1 \le j \le n$$

Matrix subtraction: Just like vector subtraction from the previous session, we simply negate the entries of the second matrix and perform matrix addition.

$$\begin{bmatrix}x & a \\ y & b \\\end{bmatrix} - \begin{bmatrix}v & d \\ w & e \\\end{bmatrix} = \begin{bmatrix}x & a \\ y & b \\\end{bmatrix} + \begin{bmatrix}-v & -d \\ -w & -e \\\end{bmatrix} = \begin{bmatrix}x - v & a - d \\ y - w & b - e \\\end{bmatrix}.$$

Or for an m x n matrix:
$$(A - B)_{i,j} = A_{i,j} - B_{i,j} \\ 1 \le i \le m,\\ 1 \le j \le n$$

Matrix-scalar multiplication: Exactly the same as scalar-vector multiplication.

$$c\begin{bmatrix}x & a \\ y & b \\\end{bmatrix} = \begin{bmatrix}cx & ca \\ cy & cb \\\end{bmatrix}.$$

$$(\lambda \mathbf {A} )_{ij}=\lambda \left(\mathbf {A} \right)_{ij} \\ 1 \le i \le m,\\ 1 \le j \le n\$$

### Exercise:
1) $\begin{bmatrix} -1 & 2 \\ 0 & 1 \\\end{bmatrix} + \begin{bmatrix} 1 & 3 \\ -1 & 2 \\\end{bmatrix}$

2) $\begin{bmatrix} 0 & 1 & -2 \\ 1 & 2 & 3 \\\end{bmatrix} + \begin{bmatrix} 2 & 3 & -1\\ -3 & 2 & 0\\\end{bmatrix}$

3) $\begin{bmatrix} -3 & 4 \\ 5 & 2.5 \\\end{bmatrix} - \begin{bmatrix} -3 & 4 \\ 5 & 2.5 \\\end{bmatrix}$

4) For the matrices A and B:

$A = \begin{bmatrix}1 & 2 & 4 \\ -3 & 0 & -1 \\ 2 & 1 & 2 \\\end{bmatrix}$ and $B = \begin{bmatrix}2 & 0 & 0 \\ 1 & -4 & 3 \\ -1 & 3 & 2 \\\end{bmatrix}$

a) Find 3A

b) Find -B

c) Find 3A - B

## Bonus content:
If A, B and C are m x n matrices and c and d are scalars, then the following properties are true:

$$1) A + B = B + A$$
$$2) A + (B + C) = (A + B) + C$$
$$3) (cd)A = c(dA)$$
$$4) 1A = A$$
$$5) c(A + B) = cA + cB $$
$$6) (c + d)A = cA + dA $$

## Exercise Solutions:

1) $\begin{bmatrix} -1 & 2 \\ 0 & 1 \\\end{bmatrix} + \begin{bmatrix} 1 & 3 \\ -1 & 2 \\\end{bmatrix} = \begin{bmatrix} -1 + 1 & 2 + 3 \\ 0 + (-1) & 1 + 2 \\\end{bmatrix} = \begin{bmatrix} 0 & 5 \\ -1 & 3 \\\end{bmatrix}$

2) $$\begin{bmatrix} 0 & 1 & -2 \\ 1 & 2 & 3 \\\end{bmatrix} + \begin{bmatrix} 2 & 3 & -1\\ -3 & 2 & 0\\\end{bmatrix} = \begin{bmatrix} 0+2 & 1+3 & -2+(-1)\\ 1+(-3) & 2+2 & 3+0\\\end{bmatrix} = \begin{bmatrix} 2 & 4 & -3\\ -2 & 4 & 3\\\end{bmatrix}$$

3) $$\begin{bmatrix} -3 & 4 \\ 5 & 2.5 \\\end{bmatrix} - \begin{bmatrix} -3 & 4 \\ 5 & 2.5 \\\end{bmatrix} = \begin{bmatrix} -3 & 4 \\ 5 & 2.5 \\\end{bmatrix} + \begin{bmatrix} -(-3) & -4 \\ -5 & -2.5 \\\end{bmatrix} = \\ \begin{bmatrix} -3+3 & 4-4 \\ -5+5 & 2.5-2.5 \\\end{bmatrix} = \begin{bmatrix} 0 & 0 \\ 0 & 0 \\\end{bmatrix}$$

NOTE: This is the 2x2 zero matrix, often denoted as $O_{2 \times 2}$

4) 
a) $$3A = 3\begin{bmatrix}1 & 2 & 4 \\ -3 & 0 & -1 \\ 2 & 1 & 2 \\\end{bmatrix} = \begin{bmatrix} 3 & 6 & 12 \\ -9 & 0 & -3 \\ 6 & 3 & 6\\\end{bmatrix}$$ 

 b) $$-B = -1\begin{bmatrix}2 & 0 & 0 \\ 1 & -4 & 3 \\ -1 & 3 & 2 \\\end{bmatrix} = \begin{bmatrix} -1(2) & -1(0) & -1(0) \\ -1(1) & -1(-4) & -1(3) \\ -1(-1) & -1(3) & -1(2)\\\end{bmatrix} = \begin{bmatrix} -2 & 0 & 0 \\ -1 & 4 & -3 \\ 1 & -3 & -2\\\end{bmatrix}$$ 

  c) $$3A-B = \begin{bmatrix} 3 & 6 & 12 \\ -9 & 0 & -3 \\ 6 & 3 & 6\\\end{bmatrix} + \begin{bmatrix} -2 & 0 & 0 \\ -1 & 4 & -3 \\ 1 & -3 & -2\\\end{bmatrix} = \begin{bmatrix} 3 + (-2) & 6 + 0 & 12 + 0 \\ -9 + (-1) & 0 + 4 & -3 + (-3) \\ 6 + 1 & 3 + (-3) & 6 + (-2)\\\end{bmatrix} \\ = \begin{bmatrix} 1 & 6 & 12 \\ -10 & 4 & -6 \\ 7 & 0 & 4\\\end{bmatrix}$$

  # END
