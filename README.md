Darcy theory : 

```math
\vec{u} = - \frac{K}{\mu} \nabla P
```
Continuity: $$ \nabla \cdot \vec{u} = 0 $$
B.C.: $$ P = 0 \; \text{at flow front}$$ $$ \vec{u} \cdot \vec{n} = 0 \; \text{at mould wall}$$
Cure is exotermic. Analysis must be 3D. 

The partial differential equations then read

$$ \vec{u} +\frac{K}{\mu} \nabla P = 0 $$
$$ \nabla \cdot \vec{u} = 0 $$

After multiplying by test functions $\tau$ and $\upsilon$, integrating over the domain, and integrating the gradient term by parts, one obtains the following variational formulation: find $\sigma \in \Sigma$ and $v \in V$ satisfying

$$ \int_{\Omega} (u \cdot \tau + \frac{K}{\mu} \cdot \nabla \cdot \tau \cdot P) \ {\rm d} x = \int_{\Gamma} \tau \cdot n \cdot P \ {\rm d} s \quad \forall \ \tau \in \Sigma $$

$$ \int_{\Omega} (\nabla \cdot u \cdot v )\ {\rm d} x = 0 $$ 

Here $n$ denotes the outward pointing normal vector on the boundary. Looking at the variational form, we see that the boundary condition for the flux $\sigma \cdot n = g$ is now an essential boundary condition (which should be enforced in the function space), while the other boundary condition $u = u_0$ is a natural boundary condition (which should be applied to the variational form). Inserting the boundary conditions, this variational problem can be phrased in the general form: find $(\sigma, u) \in \Sigma_g \times V$ such that

$$ a((\sigma, u), (\tau, v)) = L((\tau, v)) \quad \forall \ (\tau, v) \in \Sigma_0 \times V $$

where the variational forms \(a\) and \(L\) are defined as

$$ a((u, P), (\tau, v)) = \int_{\Omega} u \cdot \tau + \frac{K}{\mu} \cdot \nabla \cdot \tau \cdot P + \nabla \cdot u \cdot v \ {\rm d} x \\ $$

$$ L((\tau, v)) = - \int_{\Omega} f v \ {\rm d} x + \int_{\Gamma_D} u_0 \tau \cdot n \ {\rm d} s $$


$f=0$ and $u_0=0$:

$$ L((\tau, v)) = 0  $$

and 

$\Sigma_g = \{ \tau \in H({\rm div})$ such that  $\tau \cdot n|_{\Gamma_N} = g \}$ and $V = L^2(\Omega)$.




Heat equillibrium between resin and mould is valid in slow process (RTM), not in fast process (SRIM). 
Shell (thin) geometry -> in-plane conduction and transverse convection are negligible. 
Peclet number low -> heat dispersion due to porosity is negligible.

Energy: 
$$\left[\phi (\rho \cdot c_p)_f + (1-\phi)(\rho \cdot c_p)_s \right] \frac{\partial T}{\partial t} (\rho \cdot c_p)_f \cdot \vec{u} \cdot \nabla T = k \frac{\partial^2 T}{\partial z^2} + \phi \dot{s}$$

$ \phi = 1 - V_f $ is porosity 
$ V_f $ is fibre volume fraction 
$ \dot{s} $ is source, due to cure
$$ \kappa = \kappa_f \frac{(\kappa_f + \kappa_r) + (\kappa_f - \kappa_r)(1-\phi)}{(\kappa_f + \kappa_r) - (\kappa_f - \kappa_r)(1-\phi)}$$
B.C.: look (7), (8)
Numerical simulation
FE/CV:
rough approximation of domain shape
mass conservation
no remeshing
Pressure
Bilinear shape functions, Galerkin method (interpolation functions are weighting functions)
$$ [S^e] [P] = 0 $$
B.C. at injection: $$ [S^e] [P_i] = Q_{bc} $$
