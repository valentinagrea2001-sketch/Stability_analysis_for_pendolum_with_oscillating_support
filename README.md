# Lyapunov stability analysis for a pendolum with periodically oscillating suspension point

This repository contains a Mathematica-based computational project investigating the Lyapunov stability and instability regions of a pendulum with a periodically oscillating suspension point. You will find, in the pdf, the plots of instability regions in the space of coordinates $(\alpha, k)$.


## The mathematical model:

The equation of motion, after time rescaling, is given by

$$x'' = -(\alpha^2 - k \cos(t)) \sin(x)$$

where $k = a/l \leq 2$, $a$ is the amplitude of oscillations, $l$ is the length of pendolum, and $(x,t)\in S^{1} \times \mathbb{R}$.

In the Quotient Extended Phase Space $S^1 \times \mathbb{R} \times S^1$, the system is formulated as a system of ODEs:

$$
\begin{cases}
x' = v \\
v' = -(\alpha^2 - k \cos(t)) \sin(x) \\
t' = 1 \pmod{2\pi}
\end{cases} .
$$

There, orbits correspond to fixed points of the Period Shift Map (Pointcaré Map) $\Psi_{\alpha,k} = \phi_{2\pi,\theta}$.

Because the system preserves the volume, stability is determined efficiently via the trace criterion:

- *Lyapunov Stable* iff $\vert{}\text{Tr}(\Psi_{\alpha,k}')\vert{} \leq 2$ .

- *Lyapunov Unstable* iff $\vert{}\text{Tr}(\Psi_{\alpha,k}')\vert{} > 2$ .


## Implementation details:

- Numerical integration of equations: utilizes a second-order Runge-Kutta (RK2) scheme implemented in Wolfram Mathematica.

- Random sampling: parameter space exploration is performed by generating large random distributions of $(\alpha, k)$ pairs and evaluating the trace of the Pointcaré Map.


## Key results from plots of unstability regions near the equilibria:

- $(0, 0)$, the stable equilibria: the global portrait reveals characteristic "instability tongues" originating from cusp points on the $\alpha$-axis, where $\alpha = n/2$ for integers $n$. As $\alpha$ increases, these instability tongues become thinner.

- $(\pi,0)$, the unstable equilibria: inverted pendulum configuration is predominantly unstable, with a small stability region of strip-shape.
  

## Why did I use Wolfram Mathematica for this analysis?

1) Wolfram Mathematica is a $symbolic language$, which means that everything in the language — mathematical formulas, data, code, and graphics — is represented as a symbolic expression. This allows to easily transition from analytical math to heavy numerical simulations. ( Example: setting up differential equations and variational systems and solving them) .

2) Wolfram Mathematica has built-in tools like $Compile$ that can dramatically speed up intensive iterative algorithms ( Example: running thousands of Runge-Kutta integration steps ).


## Usage:

- In the pdf file, you will find additional informations and the plots.

- Open Stability_analysis_pendolum_oscillating_support.nb in Wolfram Mathematica and execute the cells sequentially. Note that high-accuracy global portraits using large sampling sizes (e.g., $50,000+$ points) may require up to a minute of computation time depending on your hardware.


## A personal note:

This notebook was part of the final exam project of the course in "Dynamical Systems", that I took during my Master's degree at the University of Padova. 

