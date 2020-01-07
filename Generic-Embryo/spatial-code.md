### Spatial Differentiation Code   

[0,1] ---> two-cell (A-P or L-R)

Polarity in terms of size differential, orientation (e.g. anterior is always 0).

* polarity for each fold spatial axis (e.g. ventral is 0, dorsal is 1).

[00, 01, 10, 11] ---> four-fold symmetry (A-P, L-R)

[01, 110, 101, 110] ---> fold symmetry, D-V location, L-R location, A-P location.


How to build a 512-cell embryo (in space):

* design differentiation scheme (using code).

* simulate timing information (from lineage trees).

* calculate distance between binary folds (from nearest-neighbors, from centroid of embryo).

### Calculating a sphere:
Code executed in SciLab   

r = -15:0.02387:15; (for a spheroid 30 units long/wide/tall)  
t = -%pi:0.005:%pi;  
s = -2*(%pi):0.01:2*(%pi);  
// for sparse sampling, interval will have to be changed proportionally for _r_, _t_, and _s_  
    
x = r .* cos(s) .* sin(t)  
y = r .* sin(s) .* sin(t)  
z = r .* cos(t)  
    
where _r_ = radius (diamater of spheroid/2), _t_ = height of angle (-pi to 0 to pi), and _s_ = angle around z-axis (-2$\pi$ to 0 to 2$\pi$). t is also known as $\phi$, and _s_ is also known as $\theta$. With this code, you end up with positions for 629 cells. Sample according to code.

plot3D(x,y,z,'o');   
// this produced a curved manifold. Not quite what we want.  

