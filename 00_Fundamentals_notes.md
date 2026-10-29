00: Fundamentals - Notes

1: Core Concepts / Knowledge

Learning Objectives

    Understand the structure and function of neural networks
    Learn essential linear algebra concepts like matrix operations and transformations
    Understand core principles of probability and statistics, including expected value and variance
    Learn how calculus concepts (particularly differentiation) are applied in optimization tasks
    Cover some foundational information theory concepts, such as entropy and KL divergence
    Enhance Python programming skills, focusing on NumPy and PyTorch basics

3 Blue 1 Brown videos:

Essence of linear algebra Chapter 1: Vectors

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

Essence of linear algebra Chapter 2: Linear combinations, span, and basis Vectors

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

Essence of linear algebra Chapter 3: Linear transformations and matrices

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

Essence of linear algebra Chapter 4: Matrix multiplication as composition



Deep Learning Chapter 1: But what is a neural network?

Starts with the digit reading task (think it's the MNIST dataset), trivialised by the human brain, but complex when it comes to computing a solution to messier and messier versions of the problem.
Neural networks are made of layers, code is available to play with to test the digit recognition.
Neural networks are inspired by the brain, so what are the neurons and how are they connected?
In the example the neurons are the pixels of a written digit, each neuron holds an "activation" value between 0 and 1 which denotes the brightness of the pixel, or how activated the neuron is. These neurons make up the first layer of the network, one neuron per pixel, the input layer.
The final layer has 0 - 9 in increments of 1 denoting the possible answers for the single digit recognition, these neurons also have an "activation" value between 0 and 1, but this time they represent the likelihood of the provided image being that digit.
In between the input and output layers are a bunch of "hidden layers" which for now go unquestioned and will be covered later in the videos.
Number of neurons in a hidden layer is said to be somewhat arbitrary and the number of hidden layers themselves can be too, though I'm sure there are certain structures that deal better with certain problems.
Each layer performs some calculations on each of the provided neurons, and the outcomes of these calculations determines which neurons fire in the next layer, and the next, until we reach the output where the most activated neuron becomes the networks choice of answer.
The hope is essentially that the hidden layers are learning to recognise subcomponents that are the building blocks of what makes the answer. In the video loops at the top of the image are suggested to be a feature of 8's or 9's for example, and we would hope that the network learns this.
Similarly recognising a loop can be broken down into subproblems, so we are recognising the little edges that make up the loop and deeper and deeper.
This sort of thinking is not guaranteed, it's a hope for what the network will do, we don't actually know what the network will define as important for recognition, and this is what makes it a black box.
So in the example the hidden layers perhaps recognise the little edges that make up different features in the first layer, then the second layer recognises the higher level features such as the loop itself or a long vertical line, then the final output layer might be putting those components together to make a decision on which digit we are looking at.
Next we move on to understanding how each of the activations might happen. We pretend we are designing a neuron that recognises edges in a small region of the image. Each pixel feeds into this neuron and alongside the activation values we now introduce weights, the importance of values at particular pixels for determining whether an edge exists in a particular region.
The thought here is if we made the weights outside of our ROI 0, and then gave positive weights to those values within the ROI, then we end up summing only the values that exist within the region we care about.
Furthermore we can surround the ROI with negative weighted values, which would narrow down the ROI and detect an edge within the ROI (dark to bright at the edges of the ROI gives positive results).
Combinations of neurons activations, multiplied and summed together with their associated weights can return any value theoretically. So, in order to squish the values into a normalised field, we need a way to make all of those values land inbetween 0 and 1.
One function originally used for this purpose is the sigmoid function. It create a curved line where values on the x axis (multiplication or summation results) can be read from the y axis between 0 and 1 as the line flattens at 0 and at 1.
The sigmoid essentially equates to how positive is the result, closer to zero is more negative, closer to one is more positive, but sometimes we might determine that only values that are greater or less than a certain value in the weighted sum are actually meaningful, and so we can introduce a bias value as well.
If we wanted the pixel group to have a weighted sum at least greater than ten, then we can add a -10 bias to the sigmoid fucntion to represent this.
This is all for only one second layer neuron, in the example the combinations of all neurons and weights along with their biases adds up to 13002 combinations. This is small for neural networks but still a lot to store even for a simple problem.
So when we discuss learning, what we are actually talking about is finding the right combinations of weights and biases that produce the "correct" answer (knowing what's correct is part of the problem in more complex networks)
To simplify notation we represent each possible combination of inputs and weights as a vector, so a grid of weights, a column of inputs, plus a column of biases all wrapped in a sigmoid function. This is then simplified down to give each vector its own symbol 
\sigma(Wa^(0) + b)
It might be simpler to think of the entire network as a series of cascading functions, the network is a function that takes many inputs and spits out the output, where each neuron activation after input is a function of all of its inputs multiplied by weights through a sigmoid function etc. etc.
Final notes talked about sigmoid functions, but most networks use ReLU (rectified linear unit) instead of the sigmoid, ReLU(a) = max(0, a), sigmoid learns slower than ReLU. I think this is where in code we will see the argMax funciton being used at this point in time.

Deep Learning Chapter 2: Gradient descent, how neural networks learn.

