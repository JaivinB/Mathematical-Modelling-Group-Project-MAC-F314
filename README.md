# Mathematical Modelling Group Project (MAC F314)

## The problem

How can the same neuron settle to rest after a small disturbance, produce one spike after a larger disturbance, or fire repeatedly under sustained current? We use the FitzHugh–Nagumo model to study how the applied current and the neuron's starting state determine which response occurs.

## The FitzHugh–Nagumo model

The model describes one excitable cell with two coupled differential equations.

```text
dv/dt = v − v³/3 − w + I
dw/dt = ε(v + a − bw)
```

- `v` represents the membrane voltage, which changes rapidly during a spike.
- `w` represents slower recovery processes. As recovery increases, the `−w` term reduces the voltage slope.
- `I` is the applied current, held constant within each simulation.
- `a` and `b` shape recovery, while `ε` scales its rate. We start with `a = 0.7`, `b = 0.8`, and `ε = 0.08`.

The variables and time are expressed in scaled model units.

## What we investigate

1. **Rest and excitability.** At zero current, a small voltage nudge fades, while a larger nudge produces one spike before returning to the same equilibrium.
2. **Repeated firing and stability.** At sustained current `I = 0.50`, the model fires repeatedly. We use phase portraits, nullclines, and the Jacobian to explain how this relates to the stability of the equilibrium.
3. **Transitions and sensitivity.** Sweeping the current reveals two candidate Hopf points near `I = 0.331` and `I = 1.419`. At `I = 0.50`, increasing `ε` from `0.06` to `0.10` shortens the mean firing period from `49.157` to `33.525` model time units.

The [analysis notebook](fhn_project.ipynb) contains the derivations, simulations, and figures.

## Final report and bonus results

The [final Overleaf PDF](report/report.pdf) covers the model assumptions and equations, equilibrium and stability analysis, phase portraits, the current sweep, and recovery sensitivity. Its bonus section compares a physics-informed neural network (PINN) with SciPy least squares on the inverse problem of estimating the recovery parameter `a` from voltage readings alone.

The [executed PINN notebook](fhn_pinn_ml.ipynb) includes the training, validation, and final test. With sparse, noisy synthetic observations, both fits recovered the true value `a = 0.700` within 1% and predicted the correct spike count on the held-out trajectory at `I = 0.90`.

| Method | Estimated `a` | Relative parameter error | Held-out voltage RMSE |
| --- | ---: | ---: | ---: |
| PINN | 0.704093 | 0.58% | 0.015570 |
| SciPy least squares | 0.701926 | 0.28% | 0.007343 |

Least squares gave the smaller parameter and voltage errors in this synthetic experiment.

The [LaTeX source](report/main.tex) includes the [bonus section](report/bonus.tex) and [references](report/references.bib). The [figure folder](report/figures) contains six figures in both PDF and EPS formats.

## AI acknowledgment

ChatGPT assisted with topic planning and the design of the bonus experiment. OpenAI Codex assisted with drafting and organizing both notebooks, commenting the code, checking numerical results and notebook execution, drafting the LaTeX report, and verifying its compilation.
