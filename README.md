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

## AI acknowledgment

ChatGPT assisted with topic planning and the design of the bonus experiment. OpenAI Codex assisted with drafting and organizing both notebooks, commenting the code, checking numerical results and notebook execution, drafting the LaTeX report, and verifying its compilation.
