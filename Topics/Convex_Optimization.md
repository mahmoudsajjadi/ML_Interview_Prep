# Convex Optimization

## Core Concepts and Definitions

### Lines and Line Segments
- A line passing through two distinct points \(x_1\) and \(x_2\) in \(R^n\): \(y = \theta x_1 + (1 - \theta)x_2\), where \(\theta \in R\).
- A line passing through two distinct points \( x_1 \) and \( x_2 \) in \( \mathbb{R}^n \): \[ y = \theta x_1 + (1 - \theta)x_2, \; \text{where} \; \theta \in \mathbb{R}. \]

- Line segment between \(x_1\) and \(x_2\) defined when \(0 \leq \theta \leq 1\).

### Affine Sets
- A set \(C\) is affine if the line through any two points in \(C\) lies entirely within \(C\).
- Affine combination: \(\theta_1 x_1 + \dots + \theta_k x_k\) with \(\theta_1 + \dots + \theta_k = 1\).

### Convex Sets
- A set \(C\) is convex if the line segment between any two points in \(C\) lies entirely in \(C\).
- Convex combination: \(\theta_1 x_1 + \dots + \theta_k x_k\), where \(\theta_i \geq 0\) and \(\sum \theta_i = 1\).

### Cones
- A set \(C\) is a cone if \(x \in C\) implies \(\theta x \in C\) for \(\theta \geq 0\).
- Convex cone: Both convex and a cone.

### Hyperplanes and Halfspaces
- A hyperplane: \(\{x | a^T x = b\}\).
- Halfspace: \(\{x | a^T x \leq b\}\).

### Operations That Preserve Convexity
- **Intersections**: The intersection of convex sets is convex.
- **Affine Functions**: Convex sets remain convex under affine transformations.
- **Sums**: The sum of convex sets is convex.

## Applications
- Optimization problems in machine learning (e.g., linear programming, SVM).
- Geometric interpretations in data science.

## References, Recommended Books for Convex Optimization
1. *Convex Optimization* by Stephen Boyd and Lieven Vandenberghe

