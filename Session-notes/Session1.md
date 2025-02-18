# Session 1 - Introduction to Vectors

## Interpretations of Vectors
There are three interpretations of vectors:
1) Physics view

    Vectors are simply arrows pointing in space. The length of the arrow represents the magnitude.

2) Computer Science view

    Vectors are lists of ordered numbers.

3) Mathematics view

    Tries to combine both other views to try and describe any change in a system.

For our purposes, we will focus on the Physics view first, since we often apply things in the Physics sense when it comes to games.

A vector can be decomposed into vertically listed coordinates along which to move on a cartesian plane to reach the tip of the vector.

The list of numbers coincide with the Computer Science view of vectors.

$$\vec{v} = \begin{bmatrix}1 \\\ 3 \\\ \end{bmatrix}$$

## Length / Magnitude / Norm of a vector:

$$\lVert \vec{v}\rVert = \sqrt{\smash[b]{v_1^2 + v_2^2 + ... + v_n^2}}$$

Example:

$$\lVert \vec{v}\rVert = \sqrt{\smash[b]{(1)^2 + (3)^2}}$$
$$=\sqrt{1 + 9}$$
$$=\sqrt{10}$$
$$=3.16227766... \ units$$

Exercise 1:

a) Find the norm of the vector 

$$\vec{x} = \begin{bmatrix}-2 \\\ \sqrt{5}\end{bmatrix}.$$

b) Find the norm of the vector 

$$\vec{j} = \begin{bmatrix}0 \\\ 1 \end{bmatrix}.$$

## Distance between two vectors:

$$d(\vec{v},\vec{w}) = \sqrt{(v_1 - w_1)^2 + (v_2 - w_2)^2 + ... + (v_n - w_n)^2}$$
$$=\lVert \vec{v} - \vec{w} \rVert$$

This is actually identical to the formula for the distance between two points, as the vectors can be represented by the point where the tip of the vector sits.

An observant reader would also notice that the length of a vector is simply the distance between that vector's tip and the origin. Therefore, the formula under the previous heading is really only a special application of the one given here.

Example:

$$\vec{v} = \begin{bmatrix}1 \\\ 4\end{bmatrix}, \vec{w} = \begin{bmatrix}-3 \\\ 1 \end{bmatrix}$$
$$d(\vec{v},\vec{w}) = \sqrt{(1 - (-3))^2 + (4 - 1)^2}$$
$$=\sqrt{16 + 9} = \sqrt{25} = 5\ units.$$

Exercise 2:

a) Determine the distance between the following two vectors:

$$ \vec{h} = \begin{bmatrix}-1 \\\ -4 \end{bmatrix}, \vec{i} = \begin{bmatrix}2 \\\ 3 \end{bmatrix}.$$

b) Determine the distance between the following two vectors:

$$ \vec{q} = \begin{bmatrix}3 \\\ -1 \\\ 0 \\\ -3 \end{bmatrix}, \vec{r} = \begin{bmatrix}4 \\\ 0 \\\ 1 \\\ 2 \end{bmatrix}.$$

Bonus) Try verifying the following:

$$d(\vec{v},\vec{w}) = d(\vec{w},\vec{v}).$$

## Dot Product between two vectors
The dot product of two vectors is a scalar quantity.

$$ \vec{u} \cdot \vec{v} = u_1v_1 + u_2v_2 + ... + u_nv_n.$$

Example:
The dot product of 

$$\vec{u} = \begin{bmatrix}1 \\\ 2 \end{bmatrix} \\ and \\ \vec{v} = \begin{bmatrix}3 \\\ -2 \end{bmatrix}:$$
$$ \vec{u} \cdot \vec{v} = (1)(3) + (2)(-2)$$
$$ = 3 - 4 = -1.$$

Exercise 3:

$$Let \\ \vec{u} = \begin{bmatrix}2 \\\ -2 \end{bmatrix}, \\ \vec{v} = \begin{bmatrix}5 \\\ 8 \end{bmatrix} \\ and \\ \vec{w} = \begin{bmatrix}-4 \\\ 3 \end{bmatrix}$$

a) Find 
$\vec{u} \cdot \vec{v}$.

b) Find 
$(\vec{u} \cdot \vec{v})\vec{w}$.

c) Find 
$\vec{w} \cdot \vec{w}$ and compare the result with $\lVert \vec{w} \rVert^2$.


For a graphical representation of the dot product between two vectors, imagine projecting the first vector onto the second vector and then scaling the projection by the length of the second vector.  

This representation allow us to ask some interesting questions. 

For example, what would the dot product between two orthogonal/perpendicular vectors be? Since projecting any of the vectors onto the other will result in a projection length of zero, the dot product between orthogonal vectors should be zero. Try verifying this for yourself.

## Why care?

Since the dot product between two vectors can actually tell us something about the angle between the two vectors through their projections, the dot product can be used in many cases in games.

For example, enemy vision.

Representing an enemy's facing direction as a vector and then taking the dot product with the vector connecting the player to the enemy and evaluating the result can determine whether the player is within sight of the enemy.

Evaluating a dot product could also determine whether or not a player is looking directly at a game object (think about the fact that the dot product of two perpendicular vectors is zero and the other implications it might have).

Point is: this calculation has numerous applications within the domain of game development. More will be explored as this series continues.

## Bonus content:

If $\vec{u}$, $\vec{v}$ and $\vec{w}$ are vectors in $R^n$ and $c$ is a scalar, then the following properties are true:

$$1)\ \vec{u} \cdot \vec{v} = \vec{v} \cdot \vec{u}$$
$$2)\ \vec{u} \cdot (\vec{v} + \vec{w}) = \vec{u} \cdot \vec{v} + \vec{u} \cdot \vec{w}$$
$$3)\ c(\vec{u} \cdot \vec{v}) = (c\vec{u}) \cdot \vec{v} = \vec{u} \cdot (c\vec{v})$$
$$4)\ \vec{v} \cdot \vec{v} = \lVert \vec{v} \rVert^2$$
$$5)\ \vec{v} \cdot \vec{v} \ge 0,\ and \ \vec{v} \cdot \vec{v} = 0 \ if \ and \ only \ if \vec{v} = \vec{0}$$

## Exercise Solutions:
### Exercise 1:

a) $\lVert \vec{x} \rVert = \sqrt{(-2)^2 + (\sqrt{5})^2} = \sqrt{4 + 5} = \sqrt{9} = 3\ units$. 

NOTE: Length is always positive.

b) $\lVert \vec{j} \rVert = \sqrt{(0)^2 + (1)^2} = \sqrt{1} = 1\ unit$.

NOTE: This vector is actually $\hat{j}$, a unit vector that's also one of the basis vectors in $R^2$.

### Exercise 2:

a) $d(\vec{h},\vec{i}) = \sqrt{(-1 - 2)^2 + (-4 - 3)^2}\\ = \sqrt{(-3)^2 + (-7)^2} \\\ = \sqrt{9 + 49}\\ = \sqrt{58}\ units$.

b) $d(\vec{q},\vec{r}) = \sqrt{(3 - 4)^2 + (-1 - 0)^2 + (0 - 1)^2 + (-3 - 2)^2} \\\ = \sqrt{(-1)^2 + (-1)^2 + (-1)^2 + (-5)^2}\\ = \sqrt{28}\\ = 2\sqrt{7}\ units$.

Bonus) This can be verified by picking any two vectors and performing the calculations.
As for one general proof of it:

$$d(\vec{v},\vec{w}) = \sqrt{(v_1 - w_1)^2 + (v_2 - w_2)^2} \\\ = \sqrt{(v_1^2 - 2v_1w_1 + w_1^2) + (v_2^2 - 2v_2w_2 + w_2^2)} = LHS.$$

$$Let RHS = d(\vec{w},\vec{v}) = \sqrt{(w_1 - v_1)^2 + (w_2 - v_2)^2} \\\ = \sqrt{(w_1^2 - 2v_1w_1 + v_1^2) + (w_2^2 - 2v_2w_2 + v_2^2)} \\\ = LHS. \blacksquare$$

### Exercise 3:

$$a) \vec{u} \cdot \vec{v} = 2(5) + (-2)(8) = -6.$$

$$b) From (a), \vec{u} \cdot \vec{v} = -6, so \\\ (\vec{u} \cdot \vec{v})\vec{w} = (-6) \vec{w} \\\ = \begin{bmatrix}(-6)(4) \\\ (-6)(3) \end{bmatrix} \\\ = \begin{bmatrix}24 \\\ -18 \end{bmatrix}.$$

$$c) \vec{w} \cdot \vec{w} = (-4)^2 + (3)^2 = 16 + 9 = 25. \lVert \vec{w} \rVert^2 = (\sqrt{(-4)^2 + (3)^2})^2 = (\sqrt{16 + 9})^2 = (\sqrt{25})^2 = 25.$$

NOTE: This result makes sense if you think about the geometric representation of the dot product. Projecting a vector onto itself gives its own length and multiplying by the length of the vector being projected onto simply squares the length. There are other intuitive understandings of this property as well, such as using the Pythagorean Theorem.

# END
