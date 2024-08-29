# qr_decomposition


QR Decomposition is a matrix factorization technique that decomposes a matrix A into two matrices: Q (an orthogonal matrix) and R (an upper triangular matrix). The decomposition is useful in solving linear systems, eigenvalue problems, and other numerical methods in linear algebra.


Matrix A:
Let A be an m x n matrix, where m >= n. QR decomposition expresses A as:
A = Q * R
Where:
Q is an m x n orthogonal matrix (if m > n, Q is m x m and has orthonormal columns).
R is an n x n upper triangular matrix.

Orthogonal Matrix Q:
A matrix Q is orthogonal if its columns are orthonormal, meaning they are both unit vectors (of length 1) and orthogonal to each other:
Q^T * Q = I
Where Q^T is the transpose of Q, and I is the identity matrix.

Upper Triangular Matrix R:
An upper triangular matrix R is a matrix where all the elements below the main diagonal are zero:
R = [ r11 r12 r13 ... r1n ]
    [  0  r22 r23 ... r2n ]
    [  0   0  r33 ... r3n ]
    [  .   .   .   ...  .  ]
    [  0   0   0  ... rnn ]


The Gram-Schmidt process is a method to orthogonalize a set of vectors. In the context of QR decomposition, it is used to construct the matrix Q by orthogonalizing the columns of A.

Start: Let a1, a2, ..., an be the columns of A.

Orthonormalization:
Set q1 = a1 / ||a1|| (normalize the first column).
For each subsequent vector aj, subtract its projection onto the previous qi vectors, then normalize the result to get qj.
v1 = a1
q1 = v1 / ||v1||
v2 = a2 - (q1^T * a2) * q1
q2 = v2 / ||v2||
v3 = a3 - (q1^T * a3) * q1 - (q2^T * a3) * q2
q3 = v3 / ||v3||
Continue this process for all columns of A.

Constructing R:
Once the orthogonal matrix Q is formed, R can be constructed as:
R = Q^T * A

This gives an upper triangular matrix R because Q has orthonormal columns.
