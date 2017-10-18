# cut pursuit: a working-set strategy to compute piecewise constant functions on graphs
C/C++ implementation fot the cut pursuit algorithms with Matlab interfaces.

Cut pursuit is a graph-cut-based working-set strategy to minimize functions regularized by graph-structured regularizers.
For _G_ = (_V_, _E_, _w_) a graph with edges weighted by _w_, the problem writes:  

    min<sub>_x_ ∈ _Ω_<sup>_V_</sup></sub>    _f_(_x_) + 
    ∑<sub>(_u_,_v_) ∈ _E_</sub> _w_<sub>(_u_,_v_)</sub>
    _φ_(_x_<sub>_u_</sub> - _x_<sub>_v_</sub>)  

where _Ω_ is the space in which lie the values associated with each node.  

We distinguish two different cases for _φ_, corresponding to different implementations:  
- _φ_: _t_ ↦ _δ_(_t_ ≠ 0) = 1 - _δ_<sub>0</sub>(t): the nonconvex case, the regularizer is the weight of the cut between the adjacent constant components.
Can be used for regularization or segmentation. See folder `L0_cut_pursuit`. Code by Loic Landrieu.  
- _φ_: _t_ ↦ |_t_|: the convex case, the regularizer is the __graph total variation__.
Implemented for many different functionals _f_, such as quadratic, ℓ<sub>1</sub>-norm, box constraints, simplex constraints, linear, smoothed Kullback–Leibler.
See repository [CP_PFDR_graph_d1](https://github.com/1a7r0ch3/CP_PFDR_graph_d1), by Hugo Raguet.  

### References:
Cut Pursuit: fast algorithms to learn piecewise constant functions on general weighted graphs,
L. Landrieu and G. Obozinski, 2016.

Cut-pursuit algorithm for nonsmooth functionals regularized by graph total variation, H. Raguet and L. Landrieu, in preparation. 
