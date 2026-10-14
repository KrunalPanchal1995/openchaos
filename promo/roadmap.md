# Roadmap: the path to the openchaos Target

This is the path, not the code. Each milestone says what you learn, what you build, and how you know it works. Pick one and open a pull request. See [CONTRIBUTING.md](../CONTRIBUTING.md).

## Session 4: A fourth-order symplectic solver

**You will learn:** Composition methods: building a higher-order symplectic step from the second-order midpoint rule.

**You will build:** A solver whose energy error stays bounded and small at a coarse step.

**Checkpoint (not met by the shipped code):** Energy error at most 1e-2 of E_ref over 1000 s at h = 0.02 s for the 120 degree release (the shipped midpoint rule gives 0.019 and RK4 gives 0.17).

**Difficulty:** intermediate

## Session 5: The full Lyapunov spectrum

**You will learn:** Tangent vectors, QR re-orthogonalisation and why the exponents of a mechanical system add up to zero.

**You will build:** All four exponents of the 120 degree release instead of the largest one only.

**Checkpoint (not met by the shipped code):** The four exponents sum to within 0.05 per second of zero, and the largest agrees with the shipped value within 0.15 per second (the shipped code estimates only the largest).

**Difficulty:** advanced

## Session 6: Ensemble forecasts

**You will learn:** Replacing one forecast by a cloud of forecasts, and probabilities instead of paths.

**You will build:** 1000 forecasts from a Gaussian cloud of start errors of 1e-6 rad.

**Checkpoint (not met by the shipped code):** Report the time when the spread of theta2 first exceeds 0.5 rad and the probability that the outer rod has flipped by 20 s; two seeds must agree on the time within 0.5 s (the shipped code gives only a single-run horizon for a 0.1 rad tolerance).

**Difficulty:** intermediate

## Session 7: A damped, real pendulum

**You will learn:** Adding friction to the model and fitting it to measured decay.

**You will build:** A damped model and a fit routine run on a synthetic measurement.

**Checkpoint (not met by the shipped code):** From noisy synthetic data generated with a damping of 0.05 per second and 1e-3 rad noise, recover the damping within 5 percent (the shipped model has no damping at all).

**Difficulty:** intermediate

## Session 8: Chaos for unequal masses

**You will learn:** How the chaotic region changes with the mass ratio, and generalising the energy argument.

**You will build:** Flip-time maps for general masses and rods.

**Checkpoint (not met by the shipped code):** On 80 x 80 maps report the fraction of starts that never flip within 10 s at m2 / m1 = 0.25 and 4, and show that no start flips inside your generalised energy-forbidden region (the shipped map covers equal masses only and gives 43 percent).

**Difficulty:** advanced

## The final step

Combine the milestones: an animation of two double pendulums released a tiny angle apart with fading trails, a flip-time map beside it that marks the start, and an honest forecast horizon on the screen. If your result looks like the Target animation, open a pull request and tell us how you did it.
