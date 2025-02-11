# Convex Optimization

## Core Concepts and Definitions

### Lines and Line Segments
- A line passing through two distinct points (x₁ and x₂) in ℝⁿ:   **y = θx₁ + (1 - θ)x₂**    where θ ∈ ℝ.  
- Line segment between x₁ and x₂ is defined when 0 ≤ θ ≤ 1.

### Affine Sets
- A set C is affine if the line through any two points in C lies entirely within C.  
- Affine combination: **θ₁x₁ + ... + θₖxₖ** with **θ₁ + ... + θₖ = 1**.

### Convex Sets
- A set C is convex if the line segment between any two points in C lies entirely in C.  
- Convex combination: **θ₁x₁ + ... + θₖxₖ**, where **θᵢ ≥ 0** and **∑θᵢ = 1**.

### Cones
- A set C is a cone if **x ∈ C** implies **θx ∈ C** for **θ ≥ 0**.  
- Convex cone: Both convex and a cone.

### Hyperplanes and Halfspaces
- A hyperplane: **{x | aᵀx = b}**.  
- Halfspace: **{x | aᵀx ≤ b}**.

### Operations That Preserve Convexity
- **Intersections**: The intersection of convex sets is convex.  
- **Affine Functions**: Convex sets remain convex under affine transformations.  
- **Sums**: The sum of convex sets is convex.

#### Affine Functions: Image and Inverse Image
- An affine function is a linear function plus a constant. It can be represented as: **\( f(x) = Ax + b \)**, where *A* is a matrix, *x* is a vector, and *b* is a constant vector.
##### Image of a Set Under an Affine Function
- Given a function *f* and a set *C*, the **image** of *C* under *f* is the set of all outputs when *f* is applied to every element in *C*: $$f(C) = \left\{ f(x) \,|\, x \in C \right\}$$
#### Inverse Image of a Set Under an Affine Function
- Given a function *f* and a set *C*, the **inverse image** of *C* under *f* is the set of all inputs that get mapped to elements in *C*: **\( f^{-1}(C) = \{ x \mid f(x) \in C \} \)**
- Note that the inverse image does not require the function to be invertible.
#### Preservation of Convexity
Both images and inverse images of convex sets are preserved under affine functions. This means:  
- If \( C \) is convex, then \( f(C) \) is also convex.  
- If \( C \) is convex, then \( f^{-1}(C) \) is also convex.




## Applications
- Optimization problems in machine learning (e.g., linear programming, SVM).  
- Geometric interpretations in data science.  

## References, Recommended Books for Convex Optimization
1. *Convex Optimization* by Stephen Boyd and Lieven Vandenberghe
