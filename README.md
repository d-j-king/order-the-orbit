# Order the Orbit

An interactive explorer for $d^n x/dt^n = -kx$ — what happens when you tie the $n$th derivative of position to (negative) displacement, for $n = 1$ through $5$?

**Live demo:** https://d-j-king.github.io/order-the-orbit

---

## Two modes

**Derivative tower** — vary which derivative gets the restoring term:
- $n=1$: velocity $\propto -x$ → exponential decay to anchor
- $n=2$: acceleration $\propto -x$ → simple harmonic motion, stable orbits
- $n \geq 3$: jerk/snap/crackle → some eigenvalues drift into $\text{Re} > 0$, orbits escape

**Power law spring** — fix second-order but vary force nonlinearity:
- $F = -kx\,|x/R|^{n-1}$
- $n=1$: standard SHM (closed orbits)
- $n>1$: amplitude-dependent frequency → orbits precess into rosettes

## Controls

- **Drag** on the canvas: anchor = click point, drag = initial displacement, release velocity = initial kick
- **Spin slider** (used by + add body): 0 = radial SHM, 1 = circular orbit
- Eigenvalue diagram or potential well shape updates live with n and k

## Implementation

~350 lines of vanilla JS. RK4 integration, 6 substeps per frame. No libraries.
