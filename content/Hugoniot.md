---
Created: 2024-04-04
tags:
  - shock
  - Hugoniot
  - Visar
Status: In progress
type: learning log
---

---
last modified: 2024-04-04

---
# [[Hugoniot]] 


 - ### what is #shockwave? 
	 -  A disturbance is propagated through the fluid somewhat faster than the [speed of sound](https://en.wikipedia.org/wiki/Speed_of_sound "Speed of sound"). Because the disturbance propagates [supersonically](https://en.wikipedia.org/wiki/Supersonic_speed "Supersonic speed"), it is a [shock wave](https://en.wikipedia.org/wiki/Shock_(fluid_dynamics) "Shock (fluid dynamics)")
	 - The bulk transfer of kinetic energy heats the post-shock flow. Because the mean free path length is assumed to be negligible in comparison to all other length scales in a hydrodynamic treatment, the shock front is essentially a hydrodynamic #discontinuity.
	 - In the context provided, the term "**discontinuity**" refers to a **sudden change or break in the physical properties of the fluid flow**. Specifically, it refers to the abrupt transition or discontinuous variation in certain parameters (such as density, pressure, velocity, temperature, etc.) across the shock front.
	 - In hydrodynamics,   _shocks are characterized by rapid changes in these parameters over very short distances_. When a shock wave passes through a medium, it compresses and heats the material, leading to abrupt changes in its physical properties.
 - ### #shock-compression process
	 - Consider a uniform pressure P1 suddenly applied at one face of a plate made of compressible material. Assume that the lateral dimensions of the plate are so large in comparison to the dimension in which the disturbance travels that, for all practical purposes, we may consider them to be semi-infinite. Another way of putting it is that we will learn all that we need to learn about material behavior before the arrival of lateral release waves destroys our condition of uniaxial strain.
	 - Assume that the material is initially at a pressure **Po**. The pressure pulse propagates at a velocity **Us**. Application of **P1** compresses the material to a new density **$\rho_1$** and at the same time accelerates the compressed material to a velocity **Up**. Now consider a segment of the material (with unit cross-sectional area) normal to the direction of travel.
	 - The position of the shock front at some instant of time is indicated in Fig below  by the line AA. Some short interval of time (dt) later, the shock front has advanced to BB while the matter initially at AA has moved to CC. **Across the shock front, mass, momentum and energy are conserved.**
 
	![screenshot](assets/Screen%20Shot%202024-04-04%20at%206.04.21%20PM.png)
	- #### conversation of mass
		- conversation of mass across the shock front may be expressed by noting that the mass of material encompassed by the shock wave $\rho_0U_sdt$ now occupies the volume $(U_s - u_p)dt$ at a density $\rho_1$
		- $$\rho_0U_s = \rho_1(U_s - u_p)$$
		- Alternatively, in terms of the specific volume $V = 1/\rho$
		- $$V_1U_s = V_0(U_s- u_p)$$
	- #### conversation of momentum
		- is expressed by noting that the rate of change of momentum of a mass of material $\rho_0U_sdt$ in time $dt$ accelerated to a velocity $u_p$ by a net force $P_1 - P_0$ is given by
		- $$P_1 - P_0 = \rho_0U_su_p$$
		- how to reduce the equation above?
			- $$F = ma$$
			$$P_1-P0 = \rho_0V_0\times u_p/dt$$
			Where the cross-section area is unit. the accelerated part is $u_p$ instead of $U_s-up$ 
			$$P_1-P_0 = \rho_0U_sdt \times u_p/dt$$
			$$P_1 - P_0 = \rho_0U_su_p$$
	  - #### conversation of energy
		- across the shock front is obtained by equating the work done by the shock wave with the sum of the increase of both kinetic and internal energy of the system. Thus
		- $$P_1u_p = 1/2\rho_0U_su^2_p + \rho_0U_s(E_1 - E_0)$$
		- Eliminating $U_s$ and $u_p$ results in the conversation of energy in the popular form known in the literature as the Rankie-Hugoniot relation
		- $$E_1 - E_0 = \frac{1}{2}(V_0 - V_1)(P_1 + P_0) = \frac{1}{2}(\frac{1}{\rho_0}- \frac{1}{\rho_1})(P_1 + P_0)$$
		- The three conversations equations contain a total of 8 parameters-$\rho_0, \rho_1, P_0, P_1, U_s, u_p, E_1, E_0$. If it is assumed that the quantities with zero subscripts are known(i.e., the state of the material ahead of the shock), then three equations with five unknown remain. In order to solve shock problems, we need two more relationships. 
		