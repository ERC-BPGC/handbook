# POSITION AND ORIENATION REPRESENTATION

### Position and translation

The minimum number of coordinates required to locate a body in Euclidean space is six. A coordinate frame i consists of an origin, denoted $O_{i}$ and a triad of mutually orthogonal basis vectors, denoted $(\hat x_{i} \hat y_{i } \hat z_{i})$, that are all fixed within a particular body. The pose of a body will always be expressed relative to some other body, so it can be expressed as the pose of one coordinate frame relative to another. Similarly, rigid-body displacements can be expressed as displacements between two coordinate frames, one of which may be referred to as moving, while the other may be referred to as fixed.

The position of the origin of coordinate frame i relative to coordinate frame j can be denoted by the 3 X 1 vector 

$$ ^{j} \textbf {p} _{i} =  \begin{pmatrix} ^{j} p^{x} _{i} \\ ^{j} p^{y} _{i} \\ ^{j} p^{z} _{i}   \end{pmatrix}$$

The components of this vector are the Cartesian coordinates of $O_{i}$ in the j frame, which are the projections of the vector  $^{j} \textbf {p} _{i}$  onto the corresponding axes.

### Orientation and Rotation

A rotation is a displacement in which at least one point in the rigid body remains in its initial position and not all lines in the body remain parallel to their initial orientations. The orientation of coordinate frame i relative to coordinate frame j can be denoted by expressing the basis vectors .$( \hat x_{i} \hat y_{i} \hat z_{i})$ in terms of the basis vectors ,$( \hat x_{j} \hat y_{j} \hat z_{j})$.This yields, $( ^{j}\hat x_{i} ^{j}\hat y_{i} ^{j}\hat z_{i})$  which when written together as a  3X3 matrix is known as the rotation matrix. The components of $^{j}R_{i}$ are the dot products of the basis vectors of the two coordinate frames.

$^{j}R_{i}$ = $\begin{pmatrix} \hat x _{i}.\hat x _{j} &  \hat y _{i}.\hat x _{j} &  \hat z _{i}.\hat x _{j} \\  \hat x _{i}.\hat y _{j} &  \hat y _{i}.\hat y _{j} &  \hat z _{i}.\hat y _{j}  \\  \hat x _{i}.\hat z _{j} &  \hat y _{i}.\hat z _{j} &  \hat z _{i}.\hat z _{j} \end{pmatrix}$

Because the basis vectors are unit vectors and the dot product of any two unit vectors is the cosine of the angle
between them, the components are commonly referred to as direction cosines. An elementary rotation of frame i about the $z_{j}$ axis through an angle $\theta$ is

$R_{z}(\theta) = \begin{pmatrix} \cos(\theta) & -\sin(\theta) & 0\\ \sin(\theta) & \cos(\theta) & 0\\ 0 & 0 & 1\end{pmatrix}$

while the same rotation about $\hat y_{j}$ axis is

$R_{Y}(\theta) = \begin{pmatrix} \cos(\theta) & 0 & \sin(\theta)\\ 0 & 1 & 0\\ -\sin(\theta) & 0 & \cos(\theta)\end{pmatrix}$

and about the  axis $\hat x_{j}$ is

$R_{X}(\theta) = \begin{pmatrix} 1 & 0 & 0\\ 0 & \cos(\theta) & -\sin(\theta)\\ 0 & \sin(\theta) & \cos(\theta)\end{pmatrix}$

Rotation matrices are combined through simple matrix multiplication such that the orientation of frame i relative to frame k can be expressed as

$^{k}R_{i} = ^{k}R_{j} ^{j}R_{i}$

### Euler Angles

For a minimal representation, the orientation of coordinate frame i relative to coordinate frame j can be denoted as a vector of three angles $(\alpha , \beta , \gamma)^{T}$. These angles are known as Euler angles when each represents a rotation about an axis of a moving coordinate frame. In this way, the location of the axis of each successive rotation depends upon the preceding rotation(s), so
the order of the rotations must accompany the three angles to define the orientation.

There are many other representations for orientation such as [Fixed-Angles](https://www.youtube.com/watch?v=uG0P9RX65Ek), [Quaternions](https://robotacademy.net.au/lesson/quaternions-representation-of-rotation-in-3d/) and [Angle-Axis](https://www.youtube.com/watch?v=-TUTqVOGSa8).

### Homogeneous Transformations

With homogeneous transformations, position vectors and rotation matrices are combined together in a compact notation.
Any vector $^{i}r$ expressed relative to the i coordinate frame can be expressed relative to the j coordinate frame if the position and orientation of the i frame are known relative to the j frame.

$^{j}r = ^{j}R_{i} ^{i}r +  ^{j}p_{i}$

where $^{j}p_{i}$ is the position of the origin of coordinate frame i relative to coordinate frame j and  $^{j}R_{i}$ is the orientation of frame i relative to frame j .

The above equation can be written as

$\begin{pmatrix} ^{j}r \\ 1 \end{pmatrix}$ = $\begin{pmatrix}  ^{j}R_{i}  &  ^{j}p_{i}\\ 0^{T} & 1 \end{pmatrix}\begin{pmatrix} ^{i}r \\ 1 \end{pmatrix}$

where

$^{j}T_{i} = \begin{pmatrix}  ^{j}R_{i}  &  ^{j}p_{i}\\ 0^{T} & 1 \end{pmatrix}$

is the 4X4 homogeneous transformation matrix . Just like Rotation matrices, homogeneous transformation matrices can also be transformed using matrix cross-multiplication.

$^{k}T_{i} = ^{k}T_{j} ^{j}T_{i}$