# Computational Morphology — B2 Emergence Lab

A self-contained, static educational website featuring three browser simulations:

1. **Game of Life** — two-dimensional cellular automaton with editable initial states.
2. **Collective Flocking** — boids-inspired agent-based model of local alignment, cohesion and separation.
3. **Chemotactic Aggregation** — simplified signal-producing mobile agents with a diffusing/decaying field.

Each lab includes sliders, play/pause/step/reset controls, metrics, guided investigation prompts, PNG snapshots and a CSV experiment notebook. No accounts, Python, server, installation or JavaScript packages are required.

## Publish with GitHub Pages

1. Create a new GitHub repository, for example `computational-morphology-b2`.
2. Upload `index.html`, `style.css`, and `app.js` **to the repository root**, alongside this README.
3. Open **Settings → Pages** and choose **Deploy from a branch**.
4. Select `main` and `/ (root)`, then save.
5. GitHub Pages will publish to `https://YOUR-USERNAME.github.io/computational-morphology-b2/` (replace with your actual account and repo name).

To run locally, open `index.html` in a modern browser. Hosting the same files from a simple static web server is also supported.

## Suggested student protocol

For each lab, propose a hypothesis, change one parameter at a time, perform controlled comparisons, record outputs using the *Record observation* button, export a CSV, and write a short scientific interpretation. Because flocking and chemotaxis include randomness, replicate trials and report variation. The 'New initial conditions' control creates an independent random run, while 'Reset' also returns to a new randomized state; exact seed replay is not currently available.

## Scientific and implementation notes

- The Game of Life uses Moore neighborhoods, standard B3/S23 rules, synchronous updating, and periodic (wrapped) edges.
- Flocking agents use fixed-speed steering with heuristic weighted local interaction rules and periodic edges. The alignment metric is the magnitude of the mean heading vector (0 to 1).
- Chemotaxis agents deposit an abstract, dimensionless chemical. The field is updated using a four-neighbor diffusion stencil with periodic edges and decay, followed by agent movement and deposition. A cluster index is the largest occupied coarse spatial bin divided by agent count; it is a simple indicator, not a validated aggregation statistic. The diffusion slider is limited to 0.24 for explicit numerical stability.
- These are **original instructional simplifications**, not reproductions of NetLogo models and not quantitatively validated biological simulators.
- Data exist in browser memory only until the page is reloaded; use CSV export to retain notes.

## Files

- `index.html` — semantic page structure
- `style.css` — responsive presentation
- `app.js` — simulation algorithms and user interaction

No external assets or third-party dependencies are needed. You may edit and distribute this teaching implementation for your course.
