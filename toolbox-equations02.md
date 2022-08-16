
# Table of Contents

1. [Turbulence values](#turbulence)
1. [Y-plus estimation](#yplus)
1. [Ideal gas law](#ideal)
1. [Mach number](#mach)
1. [Isentropic flow](#isentropic)

<br>

#

<a id="turbulence"></a>

## Turbulence values

<br>

In order to specify turbulent inlet boundary conditions, it is necessary to calculate the turbulence inlet values $\bf{k}$ and $\bf{\varepsilon}$ or $\bf{\omega}$, depending on which turbulence model is being used. In this approach we calculate these values based on $L_{turb}$ (turbulent length scale), $I$ (turbulent intensity, %), and $U_\infty$ (freestream velocity). 

The value $L_{turb}$ is calculated from the reference length $L_{ref}$ which is based on a characteristic length such as the hydraulic diameter (for internal flows) or the boundary layer thickness (for external flows).

$\qquad L_{turb}$ = 0.07 $L_{ref}$

As a very rough guideline, the turbulent intensity $I$ might be 1% (low), 5% (medium) or 10% (high).

$\qquad k=1.5 (U_\infty I)^2$

where $U_\infty$ is freestream velocity magnitude and $I$ is the turbulent intensity (%).

$\qquad \varepsilon = C_\mu k^{1.5} / L_{turb}$

$\qquad \omega = \varepsilon / (C_\mu k) $

The turbulent viscosity ratio is sometimes used because it gives
the turbulent viscosity as a multiple of the fluid viscosity. The turbulent viscosity ratio can be defined as either:

$\qquad \mu_t/\mu$ based on dynamic viscosity, or

$\qquad \nu_t/\nu$ based on kinematic viscosity 

The turbulent viscosity (or eddy viscosity) is defined as:

$\qquad \mu_t = \dfrac{\rho k}{\omega}\quad$ or
$\quad \nu_t = \dfrac{k}{\omega}\quad$

and so we can calculate the turbulent viscosity ratio as:

$\qquad \dfrac{\mu_t}{\mu} = \dfrac{\rho k}{\mu \omega}\quad$ or
$\quad \dfrac{\nu_t}{\nu} = \dfrac{k}{\nu \omega}\quad$ 

where $\nu$ = 1.5e-5 (for air) and $\nu$ = 1.0e-6 (for water)

<br>

#

<a id="yplus"></a>

## Y-plus estimate 

<br>

In order to get the desired y-plus values in your flow solution, it is necessary to estimate the near wall mesh size (when setting the boundary layer mesh). The near wall mesh size can be estimated as follows:

1\) calculate the Reynolds number $Re$

$\qquad Re=\rho V_\infty L_{ref} / \mu$

2\) estimate the skin friction $C_f$ based on $Re$

$\qquad C_f = [ 2log_{10}(Re) -0.65 ]^{-2.3} \qquad$ for $Re < 10^9$

3\) calculate the wall shear stress $\tau_w$ based on $C_f$

$\qquad \tau_w = C_f \frac{1}{2} \rho U_{\infty}^2$

3\) calculate the shear velocity $u_\tau$

$\qquad u_\tau = \sqrt{\dfrac{\tau_w}{\rho}}$

3\) calculate the wall distance $y$

$\qquad y = \dfrac{y^+ \mu}{\rho u_{\tau}}$

<br>

#

<a id="ideal"></a>

## Ideal gas law 

<br>

$\qquad \dfrac{P}{\rho} = RT \qquad \text{(ideal gas law)}$


where $R=287$ is the universal gas constant

&emsp; $T$ is the static temperature \
&emsp; $P$ is the static pressure \
&emsp; $\rho$ is the static density 

<br>

#

<a id="mach"></a>

## Mach number 

<br>

The Mach number $(M_{\infty})$ is a dimensionless parameter \
representing the velocity in terms of the speed of sound:

$\qquad M_\infty = \dfrac{V_\infty}{c}$

where $\bf{V_\infty}$ is the freestream velocity\
and $\bf{c}$ is the speed of sound, defined as:

$\qquad c= \sqrt{kRT_\infty}$ 

where $k$ is the ratio of specific heats $(c_p/c_v)$\
and $T_\infty$ is the freestream static temperature

<br>

#

<a id="isentropic"></a>

## Isentropic flow equations 

<br>

The isentropic flow equations are suitable for compressible flow where $M_{\infty} > 0.3$.

$\qquad \dfrac{T_0}{T} = {(1+0.2M_\infty^2)}$

$\qquad \dfrac{P_0}{P} = {(1+0.2M_\infty^2)}^{3.5}$

$\qquad \dfrac{\rho_0}{\rho} = {(1+0.2M_\infty^2)}^{2.5}$

$\bf{Note}$: For incompressible flows $(M_{\infty}<0.3)$ the Bernoulli equation should be used (instead of the isentropic flow equations):

$\qquad P_{total} = P_{static} + P_{dyn}$

where the dynamic pressure can be evaluated as

$\qquad P_{dyn} = \frac{1}{2}\rho V_{\infty}^2 \quad$
