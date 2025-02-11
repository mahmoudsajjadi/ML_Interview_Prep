# Convex Optimization

## Core Concepts and Definitions

### Lines and Line Segments
- A line passing through two distinct points \( x_1 \) and \( x_2 \) in \( \mathbb{R}^n \):  
  **\( y = \theta x_1 + (1 - \theta) x_2 \)**  
  where \( \theta \in \mathbb{R} \).  
- Line segment between \( x_1 \) and \( x_2 \) is defined when \( 0 \leq \theta \leq 1 \).

### Affine Sets
- A set \( C \) is affine if the line through any two points in \( C \) lies entirely within \( C \).  
- Affine combination:  
  **\( \theta_1 x_1 + \dots + \theta_k x_k \)**  
  with **\( \theta_1 + \dots + \theta_k = 1 \)**.

### Convex Sets
- A set \( C \) is convex if the line segment between any two points in \( C \) lies entirely in \( C \).  
- Convex combination:  
  **\( \theta_1 x_1 + \dots + \theta_k x_k \)**,  
  where **\( \theta_i \geq 0 \)** and **\( \sum \theta_i = 1 \)**.

### Cones
- A set \( C \) is a cone if **\( x \in C \)** implies **\( \theta x \in C \)** for **\( \theta \geq 0 \)**.  
- Convex cone: Both convex and a cone.

### Hyperplanes and Halfspaces
- A hyperplane:  
  **\( \{ x \mid a^T x = b \} \)**.  
- Halfspace:  
  **\( \{ x \mid a^T x \leq b \} \)**.

### Operations That Preserve Convexity
- **Intersections**: The intersection of convex sets is convex.  
- **Affine Functions**: Convex sets remain convex under affine transformations.  
- **Sums**: The sum of convex sets is convex.

---

## Affine Functions: Image and Inverse Image

An affine function is a linear function plus a constant. It can be represented as:  
**\( f(x) = Ax + b \)**  
where \( A \) is a matrix, \( x \) is a vector, and \( b \) is a constant vector.  

### Image of a Set Under an Affine Function
Given a function \( f \) and a set \( C \), the **image** of \( C \) under \( f \) is:  
**\( f(C) = \{ f(x) \mid x \in C \} \)**.

### Inverse Image of a Set Under an Affine Function
Given a function \( f \) and a set \( C \), the **inverse image** of \( C \) under \( f \) is:  
**\( f^{-1}(C) = \{ x \mid f(x) \in C \} \)**.  
Note that the inverse image does not require the function to be invertible.

### Preservation of Convexity
Both images and inverse images of convex sets are preserved under affine functions. This means:  
- If \( C \) is convex, then \( f(C) \) is also convex.  
- If \( C \) is convex, then \( f^{-1}(C) \) is also convex.

---

## Applications
- Optimization problems in machine learning (e.g., linear programming, SVM).  
- Geometric interpretations in data science.  

---

## References and Recommended Books for Convex Optimization
1. *Convex Optimization* by Stephen Boyd and Lieven Vandenberghe.
