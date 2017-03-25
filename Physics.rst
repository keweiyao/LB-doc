Phyiscs
=============================================


Boltzmann and Linear Boltzmann Equation
---------------------------------------------

This code solves the linear Boltzmann equation of heavy quarks, 
whose destribution function is :math:`f_Q(t, x, p)`.
The evolution of heavy quarks are governed by the linear Boltzmann equation,

.. math::

  \frac{\partial}{\partial t}f_Q(t, \vec{x}, \vec{p}) - \frac{\vec{p}}{E}\cdot\nabla f_Q(t, \vec{x}, \vec{p}) = C_i^{2\rightleftharpoons 2}[f_Q](t, \vec{x}, \vec{p}) + C_i^{2\rightleftharpoons 3}[f_Q](t, \vec{x}, \vec{p})

On the left hand side is the total time deriative of f, which is determined by the collison terms on the right hand side. The collison terms consistent on multiple channels labeled by :math:`i`. Here we have included :math:`2\rightleftharpoons 2` and :math:`2\rightleftharpoons 3` process.

.. math::
  C_i^{2 \rightleftharpoons 2}[f](t, \vec{x}, \vec{p_1}) &=& \frac{1}{2E_1}\frac{1}{\nu_i} \int \frac{d^3 \vec{p_2}}{{(2\pi)}^3 2E_2} \frac{d^3 \vec{p_3}}{{(2\pi)}^3 2E_3}  \frac{d^3 \vec{p_4}}{{(2\pi)}^3 2E_4} 
  \\&& \{f_Q(t, \vec{x}, p_3)f_i(t, \vec{x}, p_4)-f_Q(t, \vec{x}, p_1)f_i(t, \vec{x}, p_2)\}  
  \\&& {(2\pi)}^4\delta^{(4)}(p_1 + p_2 - p_3 - p_4)  |M_{Q+i \rightleftharpoons Q+i}|^2 
  \\
  C_i^{2 \rightleftharpoons 3}[f](t, \vec{x}, \vec{p_1}) &=& \frac{1}{2E_1}\frac{1}{\nu_i} \int \frac{d^3 \vec{p_2}}{{(2\pi)}^3 2E_2} \frac{d^3 \vec{p_3}}{{(2\pi)}^3 2E_3} \frac{d^3 \vec{p_4}}{{(2\pi)}^3 2E_4} \frac{d^3 \vec{k}}{{(2\pi)}^3 2\omega_k} 
  \\&& \{f_Q(t, \vec{x}, p_3)f_i(t, \vec{x}, p_4)f_g(t, \vec{x}, k)-f_Q(t, \vec{x}, p_1)f_i(t, \vec{x}, p_2)\} 
  \\&& {(2\pi)}^4\delta^{(4)}(p_1 + p_2 - p_3 - p_4 - k)|M_{Q+i \rightleftharpoons Q+i+g}|^2.

The distribution function of light partons :math:`f_i, i=q, \bar{q}, g` are obtained from hydrodynamic calculation. 
It neglecting off-equilibrium correction of the hydrodynamic evolution, the light parton distribution function within a fluid cell of temperature :math:`T(t, \vec{x})` and cell four-velocity :math:`u_\mu(t, \vec{x})` is,

.. math::
  f_{0,i}(t, \vec{x}, \vec{p}) = g_i \exp\left(-\frac{p\cdot u}{T}\right)

Including shear-viscous tensor :math:`\pi_{\mu\nu}(t, \vec{x})` correction to the distribution function,

.. math::
  f_i(t, \vec{x}, \vec{p}) = f_{0,i} + f_{0,i} \frac{\pi_{\mu\nu}p^\mu p^\nu}{2(e+P)(p\cdot u)^2}
  \left( \frac{|\vec{p}|}{T}\right)^\alpha

Elastic and Inelastic Cross-section
----------------------------------------------

Scattering Rates
----------------------------------------------

Detailed Balance
----------------------------------------------

LPM Effects
----------------------------------------------
