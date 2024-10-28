# Description

Shape descriptor is is define as local geometric feature expresses as the angular coordinate of the polar representation of the principal curvature vector.

The method is introduced by Kenderink denoted $I_d$ and given by:
$$I_p = 0.5 - \frac{1}{\pi} arctg (\frac{k_1+k_2}{k_1-k_2})$$
the I_p is computed for all points and the spectrum is analyzed.
# what is the principal curvature?

The **principal curvature vector** is a concept from differential geometry, particularly in the study of surfaces. It refers to the direction and magnitude of the principal curvatures at a point on a surface.

### To understand the **principal curvature vector**, it helps to break down some key ideas:

1. **Surface Curvature**: When you have a surface, like the skin of a sphere or a saddle, the surface bends or curves differently at different points. At any given point on the surface, the curvature can vary in different directions.
    
2. **Normal Vector**: At each point on a surface, you can define a **normal vector**, which is a vector perpendicular to the surface at that point.
    
3. **Principal Curvatures**:
    
    - At a specific point on a surface, the curvature varies depending on the direction in which you look.
    - The **principal curvatures** are the maximum and minimum values of this curvature at a point, and they occur in perpendicular directions.
    - These are denoted by $k_1$ and $k2$, where $k_1$​ is the maximum curvature and $k_2$ is the minimum curvature.
4. **Principal Directions**:
    
    - The directions corresponding to the maximum and minimum curvatures are called **principal directions**. They are orthogonal (perpendicular) to each other and lie in the tangent plane of the surface at the point.
### **Principal Curvature Vector**:

Now, the **principal curvature vector** refers to the vector that points in the direction of one of the principal curvatures and has a magnitude equal to that curvature. There are two principal curvature vectors at each point on a surface, corresponding to the two principal curvatures.

- **Mathematically**, for each principal curvature $k$, the principal curvature vector is given by:

$$
v_k = k e_k
$$
where:
- $k$ is the principal curvature either $k_1$ or $k_2$
- $e_k$ is the unit vector pointing to the principal direction associated with that curvature.

# Example code

```python

import numpy as np

# Define a surface function
def surface_function(x, y):
    return x**2 + y**2  # A simple paraboloid surface for demonstration

# Compute the gradient (first derivatives) of the surface at point (x, y)
def gradient(x, y):
    df_dx = 2 * x
    df_dy = 2 * y
    return np.array([df_dx, df_dy])

# Compute the Hessian matrix (second derivatives) at point (x, y)
def hessian(x, y):
    d2f_dx2 = 2  # Second derivative w.r.t. x
    d2f_dy2 = 2  # Second derivative w.r.t. y
    d2f_dxdy = 0  # Mixed partial derivative
    return np.array([[d2f_dx2, d2f_dxdy], [d2f_dxdy, d2f_dy2]])

# Compute the principal curvatures and directions
def principal_curvatures(x, y):
    H = hessian(x, y)  # Hessian matrix
    eigenvalues, eigenvectors = np.linalg.eigh(H)  # Compute eigenvalues and eigenvectors
    
    # Eigenvalues represent the principal curvatures
    k1, k2 = eigenvalues  # Principal curvatures
    
    # Eigenvectors represent the principal directions
    v1, v2 = eigenvectors[:, 0], eigenvectors[:, 1]  # Principal curvature vectors
    
    return k1, k2, v1, v2

# Example usage at a point (x, y)
x, y = 1.0, 1.0
k1, k2, v1, v2 = principal_curvatures(x, y)

print(f"Principal Curvatures at point ({x}, {y}): k1 = {k1}, k2 = {k2}")
print(f"Principal Direction Vector 1: {v1}")
print(f"Principal Direction Vector 2: {v2}")

```

the output:
```python
>>> print(f"Principal Curvatures at point ({x}, {y}): k1 = {k1}, k2 = {k2}")
Principal Curvatures at point (1.0, 1.0): k1 = 2.0, k2 = 2.0
>>> print(f"Principal Direction Vector 1: {v1}")
Principal Direction Vector 1: [1. 0.]
>>> print(f"Principal Direction Vector 2: {v2}")
Principal Direction Vector 2: [0. 1.]
```
#3dshape 
#classicMethod 
#shape

# Related To
[[Adaptive View Clustering]]