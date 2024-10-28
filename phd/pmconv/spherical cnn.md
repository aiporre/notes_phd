#pmconv

# abstract
1. motivation: data is sphreical domains are relevant if for example robotics or climate.
2. Naive implementation, planar projections of filters in sphere. fails beacuse space varying distorsions introduced. 
3. Look for spherical convolution that is rotation invariant and expresive of features on data. 
4. Sherical correlation: $$ f(x,y)(v) = \int x(p)y(p-v) dp$$ satisfises the generalized fouirier transform FFT.
5. **APPLICATIONS:** We demonstrate the computational efficiency, accuracy, and effectiveness of spherical CNNs applied to 3D model reconstruction and the optimization of energy regression.
## Introduction

convolution is done on $SO(3)$ instead of $S^2$ 

## related
[[group equivariant convolution]]
