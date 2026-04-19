# GenRTR — Generic Riemannian Trust-Region Package

## Overview

GenRTR stands for the **Generic Riemannian Trust-Region** package. It is a MATLAB toolkit designed to optimize functions across Riemannian manifolds. The package implements two principal algorithms:

- The Riemannian Trust-Region (RTR) method
- The Implicit Riemannian Trust-Region (IRTR) method

While trust-region approaches currently receive primary attention, the architecture accommodates any retraction-based optimization technique. Developers anticipate expanding the framework to additional optimization strategies.


## Framework

The package leverages MATLAB function handles to invoke user-defined routines for objective functions, gradients, Hessians, and retractions. This design allows solvers to remain "generic" and applicable across diverse problems on arbitrary manifolds. Users can consolidate applications into standalone driver files rather than managing multiple separate components.

The software operates under a modified BSD open-source license.

## Applications

Current distributions include drivers for:

- Full symmetric eigenvalue decomposition over the orthogonal group (`rtreig`, `rtreig2`)
- Dominant singular value decomposition over the Stiefel manifold (`rtrdsvd`, `irtrdsvd`)
- Extreme eigenspaces of symmetric definite matrix pencils over the Grassmann manifold (`rtresgev`, `irtresgev`, `tmesgev`)

## Authors

- [Chris Baker](https://cgbaker.net), NVIDIA
- [Pierre-Antoine Absil](https://sites.uclouvain.be/absil/), Université catholique de Louvain
- [Kyle Gallivan](https://math.fsu.edu/~gallivan), Florida State University

## Funding

Support derived from NSF Awards 032944 and 9912415, focused on dynamical systems research.

## Related Software

- [RTR-ESGEV](https://github.com/cgbaker/rtresgev) — Implementations of Riemannian Trust-Region methods for the computation of Extreme Generalized Symmetric Eigenvalues

## Related Work

The following lists are intended to be a jumping off point for those looking for resources on Riemannian optimization. However, they are grossly incomplete. Feel free to contribute if you find neglected works.

### Other Riemannian Optimization Software

- **SG_Min** — Stiefel/Grassmann optimization with dog-leg, Polak-Ribière CG, Fletcher-Reeves CG, and Newton iterations. Applications include nearest degenerate eigenproblems, Procrustes problems, and electronic structures. **Language:** MATLAB. **Author:** Ross Lippert.

- **[Manopt](https://www.manopt.org/)** — Toolbox for optimization on manifolds and linear spaces, handling structural constraints (orthonormality, low rank, positivity) as geometric objects rather than algebraic constraints. **Languages:** MATLAB (primary), with Python and Julia ports. **Author:** Nicolas Boumal.

- **[Pymanopt](https://pymanopt.org/)** — Python toolbox for optimization on Riemannian manifolds with automatic differentiation support. **Language:** Python. **Maintainer:** pymanopt/pymanopt.

- **[geoopt](https://geoopt.readthedocs.io/en/latest/)** — Manifold-aware extension of PyTorch's optimizer interface, providing Riemannian adaptive optimization methods for neural network training on non-Euclidean spaces. **Language:** Python. **Authors:** Max Kochurov, Rasul Karimov, and Serge Kozlukov.

- **[Geomstats](https://geomstats.github.io/)** — Open-source toolkit for computations, statistics, and machine learning on nonlinear manifolds, supporting geometric structures such as rotation matrices and shape spaces. **Language:** Python. **Maintainer:** Geomstats, Inc.

- **[tensorflow-riemopt](https://github.com/master/tensorflow-riemopt)** — TensorFlow library for manifold-constrained optimization, providing Riemannian metrics, exponential/logarithmic maps, geodesics, retractions, and parallel transports. **Language:** Python. **Author:** Oleg Smirnov.

### Riemannian Optimization Books

1. *[Optimization and Dynamical Systems](https://link.springer.com/book/10.1007/978-1-4471-3467-1)* — U. Helmke and J. Moore. Springer-Verlag, 1994.

2. *[Optimization Algorithms on Matrix Manifolds](https://press.princeton.edu/absil)* — P.-A. Absil, R. Mahony, and R. Sepulchre. Princeton University Press, 2008.

3. *[Convex Functions and Optimization Methods on Riemannian Manifolds](https://link.springer.com/book/10.1007/978-94-015-8390-9)* — C. Udriste. Kluwer Academic Publishers, 1994.

### Riemannian Optimization Articles

#### Foundational Work

- M. Shub. "[Some remarks on dynamical systems and numerical analysis](https://www.academia.edu/29567424/Some_remarks_on_dynamical_systems_and_numerical_analysis)." *VII ELAM* (1986) 69–92.

- S. T. Smith. "[Geometric optimization methods for adaptive filtering](https://arxiv.org/abs/1305.1886)." Ph.D. thesis (1993), Division of Applied Sciences, Harvard University.

- S. T. Smith. "[Optimization techniques on Riemannian manifolds](https://arxiv.org/abs/1407.5965)." *Hamiltonian and Gradient Flows, Algorithms and Control.* Fields Inst. Commun. 3 (1994) 113–136.

- A. Edelman, T. A. Arias, and S. T. Smith. "[The geometry of algorithms with orthogonality constraints](https://doi.org/10.1137/S0895479895290954)." *SIAM J. Matrix Anal. Appl.* 20(2) (1998) 303–353.

#### Core Trust-Region and Computational Methods

- P.-A. Absil, C. G. Baker, and K. A. Gallivan. "[Trust-region methods on Riemannian manifolds](https://doi.org/10.1007/s10208-005-0179-9)." *Foundations of Computational Mathematics* 7(3) (2007) 303–330.

- C. G. Baker, P.-A. Absil, and K. A. Gallivan. "Implicit Trust-Region Methods on Riemannian Manifolds." *IMA Journal of Numerical Analysis.* [[Published](https://doi.org/10.1093/imanum/drn029)] [[Preprint](http://www.csm.ornl.gov/~cbaker/Publi/IRTR.htm)]

#### Grassmann Manifolds and Eigenvalue Problems

- P.-A. Absil, C. G. Baker, and K. A. Gallivan. "[A truncated-CG style method for symmetric generalized eigenvalue problems](https://doi.org/10.1016/j.cam.2005.10.006)." *J. Comput. Appl. Math.* 189(1-2) (2006) 274–285.

- P.-A. Absil, R. Mahony, R. Sepulchre, and P. Van Dooren. "[A Grassmann-Rayleigh quotient iteration for computing invariant subspaces](https://doi.org/10.1137/S0036144500378648)." *SIAM Rev.* 44(1) 57–73 (2002).

- P.-A. Absil, R. Mahony, and R. Sepulchre. "[Riemannian geometry of Grassmann manifolds with a view on algorithmic computation](https://doi.org/10.1023/B:ACAP.0000013855.14971.91)." *Acta Appl. Math.* 80(2) (2004) 199–220.

- C. G. Baker, P.-A. Absil, and K. A. Gallivan. "[An implicit Riemannian trust-region method for the symmetric generalized eigenproblem](https://doi.org/10.1007/11758501_32)." *Computational Science — ICCS 2006.* Lecture Notes in Computer Science 3991 (2006) 210–217.

- E. Lundström and L. Eldén. "[Adaptive eigenvalue computations using Newton's method on the Grassmann manifold](https://doi.org/10.1137/S0895479899354688)." *SIAM J. Matrix Anal. Appl.* 23(3) (2002) 819–839.

#### Newton's Method on Manifolds

- R. L. Adler, J.-P. Dedieu, J. Y. Margulies, M. Martens, and M. Shub. "[Newton's method on Riemannian manifolds and a geometric model for the human spine](https://doi.org/10.1093/imanum/22.3.359)." *IMA J. Numer. Anal.* 22(3) (2002) 359–390.

- K. Hüper and J. Trumpf. "[Newton-like methods for numerical optimization on manifolds](https://doi.org/10.1109/ACSSC.2004.1399106)." *Proc. 38th IEEE Asilomar Conference on Signals Systems and Computers* (2004).

- J.-P. Dedieu and D. Novitsky. "[Symplectic methods for the approximation of the exponential and the Newton sequence on Riemannian submanifolds](https://doi.org/10.1016/j.jco.2004.09.010)." *Journal of Complexity* 21 (2005) 487–501.

- J.-P. Dedieu, P. Priouret, and G. Malajovich. "[Newton's method on Riemannian manifolds: covariant alpha theory](https://doi.org/10.1093/imanum/23.3.395)." *IMA J. Numer. Anal.* 23(3) (2003) 395–419.

- R. Mahony and J. H. Manton. "[The geometry of the Newton method on non-compact Lie groups](https://doi.org/10.1023/A:1016586831090)." *J. Global Optim.* 23(3) (2002) 309–327.

- B. Owren and B. Welfert. "[The Newton iteration on Lie groups](https://doi.org/10.1023/A:1022322503301)." *BIT* 40(1) (2000) 121–145.

- R. Mahony. "[The constrained Newton method on a Lie group and the symmetric eigenvalue problem](https://doi.org/10.1016/0024-3795(95)00171-9)." *Linear Algebra Appl.* 248 (1996) 67–89.

#### Other

- R. Lippert and A. Edelman. "[Nonlinear eigenvalue problems with orthogonality constraints](https://www.netlib.org/utk/people/JackDongarra/etemplates/node343.html)." *Templates for the Solution of Algebraic Eigenvalue Problems.* SIAM (2000) 290–314.

- J. H. Manton. "[Optimization algorithms exploiting unitary constraints](https://doi.org/10.1109/78.984753)." *IEEE Trans. Signal Process.* 50(3) (2002) 635–650.

- M. T. Chu. "[Numerical methods for inverse singular value problems](https://doi.org/10.1137/0729054)." *SIAM Journal on Numerical Analysis* 29(3) (1992) 885.

- M. T. Chu. "[A list of matrix flows with applications](https://core.ac.uk/outputs/24492634/)." *Hamiltonian and Gradient Flows, Algorithms and Control.* Fields Inst. Commun. 3 (1994) 87–97.

- D. Gabay. "[Minimizing a differentiable function over a differential manifold](https://doi.org/10.1007/BF00934767)." *Journal of Optimization Theory and Applications* 37(2) (1982) 177–219.

- D. G. Luenberger. "[The gradient projection method along geodesics](https://doi.org/10.1287/mnsc.18.11.620)." *Management Sci.* 18 (1972) 620–631.

- H. R. Rutishauser. "[Simultaneous iteration method for symmetric matrices](https://doi.org/10.1007/BF02219773)." *Numerische Mathematik* 16 (1970) 205–223.

- M. Beko, J. Xavier, and V.A.N. Barroso. "[Noncoherent Communication in Multiple-Antenna Systems: Receiver Design and Codebook Construction](https://doi.org/10.1109/TSP.2007.901151)." *IEEE Trans. on Signal Processing* 55(12) (2007) 5703–5715.

- J. Dehaene and J. Vandewalle. "[New Lyapunov functions for the continuous-time QR algorithm](https://www.researchgate.net/publication/2898702_New_Lyapunov_functions_for_the_continuous-time_QR_algorithm)." *Proceedings of the 14th International Symposium on the Mathematical Theory of Networks and Systems* (2000).

- Y. Yang. "[Optimization on Riemannian manifold](https://doi.org/10.1109/CDC.1999.832905)." *Proceedings of the 38th Conference on Decision and Control* (1999).

- Y. Yang. "[Globally convergent optimization algorithms on Riemannian manifolds: Uniform framework for unconstrained and constrained optimization](https://doi.org/10.1007/s10957-006-9081-0)." *Journal of Optimization Theory and Applications* 132(2) (2007) 245–265.
