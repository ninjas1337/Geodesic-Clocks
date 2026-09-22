# Geodesic Clocks

An interactive 3D visualization of **time curvature** in the weak-field limit of general relativity.

A light ray and two clocks cross the gravitational field of a mass. The field is shown as a 3D lattice where every node is a static clock ticking at √(1 + 2Φ/c²).

- **Light** follows a null geodesic: dτ = 0.
- **Fast clock**: same impact parameter as the light. As v → c its path merges with the light ray and its proper time goes to zero.
- **Slow clock**: a different path. Its deflection is dominated by the time part of the metric (g₀₀).
- **Lattice nodes**: static clocks. The nodes near the mass visibly fall behind in phase.

Open `index.html` in any modern browser. It's a single file with no build step, and it works on iPad Safari. Three.js r128 loads from cdnjs.

## Physics

Weak-field metric (γ = 1, units G = c = 1):

```
ds² = −(1 + 2Φ) dt² + (1 − 2Φ) |dx|²
```

Geodesic equation to first order in Φ, in coordinate time:

```
a = −∇Φ (1 + v²) + 4 v (v · ∇Φ)
```

Proper time along each worldline:

```
dτ = dt √[(1 + 2Φ) − (1 − 2Φ) v²]
```

Deflection of a particle with speed v and impact parameter b:

```
α(v) = (2M / b v²)(1 + v²)   →   4M/b  at v = 1
```

The **1** comes from time curvature (g₀₀) and the **v²** from spatial curvature (gᵢⱼ). For light the two contribute equally, which gives the factor 4 compared with the Newtonian 2M/(bv²).

Shapiro delay for a straight path from x = −L to x = L:

```
Δt = 2M ln[(√(L² + b²) + L) / (√(L² + b²) − L)]
```

Φ = −M/r outside the body and a uniform-density interior inside it. Integration uses RK4 with dt = 0.01.

### Limits of the model

- It is **first order** in GM/(c²b). As the mass slider increases, the measured deflection pulls away from the first-order formula. That is where the weak-field approximation breaks down.
- The **lattice warp** is a stated map, not a literal picture: points are drawn at radius r(1 + 1.5Φ). A curved 3D space cannot be embedded in flat 3D space.
- Masses are exaggerated relative to body size so the effects are visible.

## References

- S. Weinberg, *Gravitation and Cosmology* (Wiley, 1972), ch. 8–9.
- C. M. Will, *Theory and Experiment in Gravitational Physics*, 2nd ed. (Cambridge, 2018).
- C. W. Misner, K. S. Thorne, J. A. Wheeler, *Gravitation* (Freeman, 1973), §40.3.
- A. Accioly, S. Ragusa, *Class. Quantum Grav.* 19, 5429 (2002).
- R. Epstein, I. I. Shapiro, *Phys. Rev. D* 22, 2947 (1980).
- I. I. Shapiro, *Phys. Rev. Lett.* 13, 789 (1964).
- J. B. Hartle, *Gravity: An Introduction to Einstein's General Relativity* (Addison-Wesley, 2003).

## Author

Sanjin Redzic ([ORCID 0009-0006-7034-6869](https://orcid.org/0009-0006-7034-6869))

## License

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Reuse and adapt freely with attribution to Sanjin Redzic.
