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
An affine function is a linear function plus a constant. It can be represented as: **\( f(x) = Ax + b \)**, where *A* is a matrix, *x* is a vector, and *b* is a constant vector.
##### Image of a Set Under an Affine Function



## Applications
- Optimization problems in machine learning (e.g., linear programming, SVM).  
- Geometric interpretations in data science.  

## References, Recommended Books for Convex Optimization
1. *Convex Optimization* by Stephen Boyd and Lieven Vandenberghe
