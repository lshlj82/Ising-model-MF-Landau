# Mean-field and Landau theory of the Ising model

An interactive, single-file web demo of the mean-field treatment of the Ising model and of Landau theory. It is based on lecture notes by Sang Hoon Lee for Chapter 2, which follow K. Christensen and N. R. Moloney, *Complexity and Criticality* (2005). It is a companion to the Ising and percolation demos.

Everything runs in the browser. There is no build step, no server and no dependencies beyond an optional web font. Units are k<sub>B</sub> = 1 and J = 1, so T<sub>c</sub> = z in mean-field theory.

## Running it

Open `index.html` in any modern browser (Chrome, Edge, Firefox or Safari).

To publish it with GitHub Pages, push this repository, then go to **Settings → Pages**, choose **Deploy from a branch**, and select the branch and the root folder. The page will be served at `https://<user>.github.io/<repository>/`.

## What the page contains

**The idea, first.** A conceptual illustration on a patch of lattice (a chain, square, triangular or square-with-diagonals lattice for z = 2, 4, 6 or 8). Three panels show the center spin with its actual fluctuating neighbors, each spin split into its average m and a fluctuation, and the mean-field picture with every spin replaced by m. A chart shows the field on the center spin fluctuating around the constant mean-field value Jzm + H, and a cobweb plot steps around the self-consistency loop (m → effective field → ⟨s⟩ = tanh(βh) → m).

**Interactive solution.**

- Controls: T/T<sub>c</sub> with presets, the field H, and the coordination number z.
- A graphical solution of the self-consistency equation m = tanh[(T<sub>c</sub>m + H)/T], with stable and unstable solutions marked.
- The mean-field free energy f(m) with its Landau approximation, and a ball that either rolls to the nearest minimum or jumps to the lowest one.
- A button that sweeps H from +1 to −1 and back, tracing a hysteresis loop through metastable states below T<sub>c</sub>.

**The mean-field approximation.**

- the step from neglecting fluctuations to an effective field Jzm + H, the partition function and f
- mean-field m<sub>0</sub>(T) for z = 2 and z = 4 against Onsager's exact 2D result
- a clickable phase diagram of m(T, H) with the line of first-order transitions ending at (T<sub>c</sub>, 0)
- a table of mean-field and exact critical temperatures

**Order parameter and response.**

- m<sub>0</sub>(T) with its unstable branch, and β = 1/2 on log–log axes
- m(T, H) against H (including metastable branches) and against T
- m(T<sub>c</sub>, H) with δ = 3, and f(T, H) with its cusp
- χ(T, 0) with γ = 1 and the amplitude ratio Γ<sup>+</sup>/Γ<sup>−</sup> = 2
- ε(T, 0) and the specific-heat jump to 3k<sub>B</sub>/2 (α = 0)

**Landau theory.**

- the expansion f ≈ f<sub>0</sub> − Hm + a<sub>2</sub>(T − T<sub>c</sub>)m² + a<sub>4</sub>m⁴ with a<sub>2</sub> = k<sub>B</sub>/2 and a<sub>4</sub> = k<sub>B</sub>T/12
- comparisons with the full mean-field free energy and m<sub>0</sub>(T)
- the 3 × 3 sketch of f − f<sub>0</sub> for H &lt; 0, = 0, &gt; 0 and T &lt; T<sub>c</sub>, = T<sub>c</sub>, &gt; T<sub>c</sub>, showing the first-order jump and the continuous transition

**General Landau (φ⁴) theory.** The symmetry argument for even powers, the leading-order coefficients, and sliders for r = α̃<sub>2</sub>(T − T<sub>c</sub>), H and u = α̃<sub>4</sub>, showing the extrema of f(φ).

**Successes and limits.** What mean-field theory gets right and wrong, with a table comparing its exponents to the exact 2D and numerical 3D Ising values.

## Methods

| Topic | Approach |
| --- | --- |
| Self-consistency equation | All roots found by scanning and bisection; stability from 1 − (T<sub>c</sub>/T) sech²(…) &gt; 0 |
| Equilibrium m | Fixed-point iteration from m = sign(H), which converges to the global minimum |
| Ball | Gradient descent on f(m) (nearest minimum) or the global minimum |
| Response functions | Closed forms in m<sub>0</sub>(T); c by differentiating ε(T, 0) numerically |

## Files

```
index.html   the complete demo (HTML, CSS and JavaScript in one file)
README.md    this file
```

## References

**Key reference.** K. Christensen and N. R. Moloney, *Complexity and Criticality*, Imperial College Press, London (2005), Chapter 2.

1. P. Weiss, "L'hypothèse du champ moléculaire et la propriété ferromagnétique," *J. Phys. Theor. Appl.* **6**, 661 (1907).
2. L. D. Landau, "On the theory of phase transitions," *Zh. Eksp. Teor. Fiz.* **7**, 19 (1937).
3. L. Onsager, "Crystal statistics. I. A two-dimensional model with an order-disorder transition," *Phys. Rev.* **65**, 117 (1944).
4. N. Goldenfeld, *Lectures on Phase Transitions and the Renormalization Group*, Addison-Wesley (1992).
5. A. Pelissetto and E. Vicari, "Critical phenomena and renormalization-group theory," *Phys. Rep.* **368**, 549 (2002).

## Credits

Lecture notes: Sang Hoon Lee.

Created by Claude Opus 5.5.
