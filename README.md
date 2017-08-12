# Latent-Semantic-Analysis-Book-Titles

Latent Semantic Analysis 
- Synonymy: Mutliple words with the same meaning
- Polysemy: one word with multiple meanings

Synonyms:
- "buy" and "purchase" 
- "big" and "large"
- "quick" and "speedy"

Polysemes: 
"Man" (Human oppose to animal, vs. male vs. female, or "hey, man", 
"Milk" (verb, noun)

Latent variables:
combine words with similar meaning
z = 0.7 * computer + 0.5 * PC + 0.6 * laptop 
(hidden variable to represent all of them) 

Job of latent semantic analysis (LSA) is to find these variables and transform original data into these new variables and hopefully the dimensionality of these data is much smaller than the original. Allow us to speed up computation. 

Does this help with Polysemy?
Conflicting viewpoints on whether it helps with Polysemy. 

### Math behind LSA

LSA is really Singular Value Decomposition (SVD) on the term-document matrix. 

* singular value decomposition (SVD) is a factorization of a real or complex matrix. It is the generalization of the eigendecomposition of a positive semidefinite normal matrix (for example, a symmetric matrix with positive eigenvalues) to any {\displaystyle m\times n} m\times n matrix via an extension of the polar decomposition. It has many useful applications in signal processing and statistics.

PCA is a simpler form of SVD.

Principle Components Analysis (PCA)
 - does a transformation on our input vector
 - z = Qx 
 - Q is a matrix
 - scalar * vector = another vector, same direction
 - matrix * vector = another vector, possibly different direction
 - PCA rotates our original input vectors, same vector different coordinate system.
 
 PCA does 3 things for us:
 1) Decorrelates input data: data new coordinate system has zero correlation
 2) Transformed data is ordered by information content: decreasing ordered, less information etc.
 3) Dimensionality reduction: allows to reduce dimensionality (e.g. 1000 words => latent distnct terms might be 100)
 
 - removing information != decreasing predictive ability 
 - denoising/smoothing/improving generalization 
 
Covariance 
more variance is synonymous with more information, 
non-matrix form:

Eigenvalues & Eigenvectors
- A = diagonal matrix of eigenvalues (there are D of them -> D x D matrix)
- Q = matrix of stacked eigenvectors (there are D of them -> D x D matrix)
- we sort A so the eigenvalues are in descending order
- remember that z = Qx, or in matrix form Z = XQ
- turns out A is the covariance matrix of Z therefore:
  - variance, aka information in Z is sorted in descending order
  - none of the dimension in Z are correlated

Extending PCA - PCA helps us combine input features (words/terms, columns of input matrix)
"Term document matrices" - each term as input, document as sample
Combine and decorrelated by docuemtn? Just do PCA on the tranpose ... which leads to weird results. 

SVD (singular value decomposition) 
SVD does both of these at the same time. PSA same time (lots of fun math)
