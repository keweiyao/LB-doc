Phyiscs
=============================================

Linear Boltzmann Equation
---------------------------------------------

This code solves the linear Boltzmann equation of heavy quarks
The evolution of heavy quark distribution is governed by the linear Boltzmann equation,

.. math::
  \frac{\partial}{\partial t}f_Q - \frac{\vec{p}}{E}\cdot\nabla f_Q  = C_i^{2\rightleftharpoons 2}[f_Q] + C_i^{2\rightleftharpoons 3}[f_Q]

The total time deriative of the distribution equals the collison terms. The collison terms consistent of multiple channels labeled by :math:`i`. Here we have included :math:`2\rightleftharpoons 2` and :math:`2\rightleftharpoons 3` process.

.. math::
  C_i^{2 \rightleftharpoons 2}[f] &=& \frac{1}{2E_1}\frac{1}{\nu_i !} \int d^3 \Gamma_2 d^3 \Gamma_3 d^3 \Gamma_4 
  \\&& \{f_Q(p_3)f_i(p_4)-f_Q(p_1)f_i(p_2)\}  
  \\&& {(2\pi)}^4\delta^{(4)}(p_1 + p_2 - p_3 - p_4)  |M_{Q+i \rightleftharpoons Q+i}|^2 
  \\
  C_i^{2 \rightleftharpoons 3}[f] &=& \frac{1}{2E_1}\frac{1}{\nu_i !} \int d^3 \Gamma_2 d^3 \Gamma_3 d^3 \Gamma_4 d^3 \Gamma_k 
  \\&& \{f_Q(p_3)f_i(p_4)f_g(k)-f_Q(p_1)f_i(p_2)\} 
  \\&& {(2\pi)}^4\delta^{(4)}(p_1 + p_2 - p_3 - p_4 - k)|M_{Q+i \rightleftharpoons Q+i+g}|^2.

The distribution function of light partons :math:`f_i, i=q, \bar{q}, g` are obtained from hydrodynamic calculation. 
Neglecting off-equilibrium correction, the light parton distribution function within a fluid cell of temperature :math:`T(t, \vec{x})` and cell four-velocity :math:`u_\mu(t, \vec{x})` is,

.. math::
  f_{0,i}(t, \vec{x}, \vec{p}) = g_i \exp\left(-\frac{p\cdot u}{T}\right)


Langevin equation
----------------------------------------------

The Langevin equation of heavy quark,

.. math::
  \frac{d \vec{p}_Q}{dt} &=& -\gamma(E_1, T)\vec{p}_Q + \vec{\xi}	\\
  \langle \xi_i \xi_j \rangle &=& \frac{p_i p_j}{|p|^2}B_{\|}(E_1, T) + \left(\delta{ij}-\frac{p_i p_j}{|p|^2}\right)B_{\perp}(E_1, T)
  
LPM effect and implementation
---------------------------------------------

Heavy quark experience a single or multiple scatterings may radiate gluons. 
The radiated gluon has a finite formation time :math:`\tau_k \sim k/({k^2}_\perp+x^2 M^2)`. During the formation time of the gluon, the heavy quark may expereience multiple scatterings and the destructive intereference between different scattering centers decreases the gluon radiation probablity.

An rigrous treatment of this type of interference effect is difficult for a Monte Carlo modelling. In this work, we just restict the phase space of the radiated gluon depending of its formation time and mean free-path :math:`\lambda`

.. math::
  \int d^3 k &\rightarrow& \int d^3 k f(\theta\lambda/\tau_k)	\\
  f(x) &=& \frac{x^2}{1+x^2}

Where :math:`\theta` is a parameter modulating the strength of the LPM effect. The mean free path is determined at run time based on the collision history of the heavy quark.









