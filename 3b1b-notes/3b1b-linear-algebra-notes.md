# 3B1B Linear Algebra Notes

## Essence of linear algebra Chapter 1: Vectors

In physics what defines a given vector is it's length and it's direction, you can move it's location and it's still the same vector. 
In computer science vectors are ordered lists of numbers, a fancy word for lists.
In mathematics, they try to combine both views and attempt to define the vector equations and operations, saved for later video.
Geometric focus to this video, think of an arrow, and one in a graphical location rooted at the origin, then translate that visual over to the list of numbers.
Focussing on 2D we have x and y with origin at (0, 0), with each incrememnt as 1.
The coordinates of a vector are instructions for how to get from the tail to the tip. The vector always go through the original, and the coordinates are the points associated with the tip.
In 3D, we still use the origin tails, but have a triplet defining the tip for [x, y, and z]
Vector addition is defined as taking two vectors, both starting from  origin and ending at some tip. The sum of the two is equivalent to taking the tail of one vector and move it to the tip of the other. The resulting vector from the origin to the new tip of the second vector is the sum result.
In list format we basically sum the matching terms inside of each vector, leading to x1 + x2, y1 + y2, etc.
Multiplying a vector by a single term can produce results such as doubling it's length with 2, or reversing it's direction with -1, or reversing and shrinking it with -0.7, and so on.
These single value multipliers that shrink, extend, and reverse the vector are called Scalars, and the process scaling.
For lists we factor each vector component by the scalar, which obviously has the same result [3, 1] x 2 becomes [6, 2], which on the graphical representation becomes a double length vector.

## Essence of linear algebra Chapter 2: Linear combinations, span, and basis Vectors

Further breaking down the concept of vector coordinates we can think of each element of the coordinate pair as a scalar for the standard unit of measure in both the x and y direction.
these single unit measures $$\hat{\imath} + \hat{\jmath}$$ as an addition of the scaled single unit vector along the x axis plus the scaled unit vector along the y axis, describes the vector coordinates as well.
Any time we are combining two vectors, this is called a linear combination of those two vectors. Again, the concept can be broken down to combinations of single unit measures to create one vector, or two sets of these added makes another linear combination etc.
In theory any combination of two vectors can reach any space on the 2D plane. However, if both vectors are zero, or exist upon the same line, this is no longer true, with zeroes you are stuck, and along the same line means you can only reach places along that line.
The set of all possible vectors you can reach with any linear combination of a pair of vectors is called the "span" of those two vectors.
Often vectors are simplified down to just a point in space, and this aids in visualisation, but we should still imagine that for a vector described in this way, it's tail is on the origin and it extends to the point.
This also extends to vectors with a span of a line, we can just draw the line itself to represent the span.
For most linear combinations, we can instead imagine the entire 2D plane, a flat sheet of 2D space where all combinations could reach as the span.
In 3D space, if we have two vectors, we can imagine their span as a flat sheet within the 3D space. The addition of a third vector is required to have a span which covers all of 3D space.
If the third addition exists on the span of the first two (similar to the line example) then the span is still a flat plane. But, if the third vector happens to exist outside of the plane of the first two, then we can access the entirety of 3D space.
For the examples of two vectors existing on the same line, or the same 2D plane in 3D, we have terminology to describe these. They are called "linearly dependent" vectors. Where you can remove a vector without impacting the span. Where one vector is a linear combination possibility of the others.
Similarly, if this is not the case then the vectors are "linearly independent".
The basis of a vector space is a set of linearly independent vectors that span the full space.

## Essence of linear algebra Chapter 3: Linear transformations and matrices

Supposedly the topic which helps the rest of linear algebra click. The relationship between linear transformations and matrix multiplication.
A way to think about why matrix multiplication works the way it does, rather than just memorise it.
By transformation we essentially mean a function, but the better way to understand them is to think of them moving.
So transformation implies we are shifting space through the operations we are performing.
Linear algebra restricts itself to linear transformations:
- all lines remain lines without being malformed into curves
- the origin remains fixed throughout the transformation

In general we can think of linear transformations as keeping lines parallel and evenly spaced.
So how do we describe these numerically?
It turns out you only need the basis vectors (i hat and j hat)) to understand where any vector would end up.
the output of v (where it lands) is a linear combination of the scaled version of i hat and j hat (scaled by their resulting positions)
[x, y] = x[where i hat lands] + y[where j hat lands]
A linear transformation is completely described by these four numbers (coordinates of i hat landing and coordinates of j hat landing)
this is where we end up with the linear transformation function shown in school [x, y] * [[a, c][b, d]] = [ax + by, cx + dy]]
Where the transformed versions of i hat and j hat are linearly dependent, we end up seeing a single line (in 3D the flat plane span of that transform), and so all vector part of that transformation converge onto that line.

## Essence of linear algebra Chapter 4: Matrix multiplication as composition

Sometimes we may wish to describe the effect of applying multiple transformations, first one then another.
In the example a rotation, then shear is applied, how do we describe the effect of doing these two tranformations?
If both of these transformations are linear transformations then the resulting space of those two transformations is another linear tranformation in and of itself.
This is referred to and the "composition" of the two tranformations applied.
The composition matrix that describes the composition transform is the product of the matrix that describes the rotation and the matrix that describes the shear.
