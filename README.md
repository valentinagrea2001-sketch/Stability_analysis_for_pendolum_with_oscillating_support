# Lyapunov stability analysis for a pendolum with periodically oscillating suspension point

This repository contains a Mathematica-based computational project investigating the Lyapunov stability and instability regions of a pendulum with a periodically oscillating suspension point. 

**Mathematical Model**:

The equation of motion, after time rescaling, is given by

$x'' = -(\alpha^2 - k \cos(t)) \sin(x)$

where $k = a/l \leq 2$, $a$ is the amplitude of oscillations, $l$ is the length of pendolum, and $(x,t)\in S^{1} \times \mathbb{R}$.

In the Quotient Extended Phase Space $S^1 \times \mathbb{R} \times S^1$, the system is formulated as a system of ODEs:

\begin{cases}
$x' = v$ \\

$v' = -(\alpha^2 - k \cos(t)) \sin(x)$ \\

$t' = 1 \pmod{2\pi}$ \\
\end{cases}

There, orbits correspond to fixed points of the Period Shift Map $\Psi_{\alpha,k} = \phi_{2\pi,\theta}$.

Because the system preserves the volume, stability is determined efficiently via the trace criterion:

- *Lyapunov Stable*: $\vert{}\text{Tr}(\Psi_{\alpha,k}')\vert{} \leq 2$

- *Lyapunov Unstable*: $\vert{}\text{Tr}(\Psi_{\alpha,k}')\vert{} > 2$


Implementation DetailsNumerical Integration: Utilizes a custom second-order Runge-Kutta (RK2) scheme implemented with Wolfram Mathematica's Compile feature for optimized performance.Variational Equations: Separate vector fields and solvers are defined for tracking the lower equilibrium $(0,0)$ and upper equilibrium $(\pi,0)$.Random Sampling: Parameter space exploration is performed by generating large random distributions of $(\alpha, k)$ pairs and evaluating the trace of the monodromy matrix.

## Key Results & Plots Instability Tongues for $(0,0)$: 

The global portrait reveals characteristic "instability tongues" originating from cusp points on the $\alpha$-axis where $\alpha = n/2$ for integers $n$.Stability Boundary: At $k=0$, instability occurs exclusively at the boundaries where $\alpha = n/2$.

## Upper Equilibrium $(\pi,0)$:

Demonstrates that the inverted pendulum configuration is predominantly unstable, with narrow stability regions that thin out as $\alpha$ increases.

## Usage

Open Stability_analysis_pendolum_oscillating_support.nb in Wolfram Mathematica and execute the cells sequentially. Note that high-accuracy global portraits using large sampling sizes (e.g., $50,000+$ points) may require up to a minute of computation time depending on your hardware.
