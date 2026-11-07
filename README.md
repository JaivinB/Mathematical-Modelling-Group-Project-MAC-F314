# Mathematical Modelling Group Project (MAC F314)

**FitzHugh–Nagumo model of neuronal firing and excitability**

The [starter notebook](fhn_project.ipynb) introduces the equations, finds the resting state and compares a small nudge, a single spike and sustained firing. Each section explains the algorithm before its runnable Python cell.

## Run on a Mac

From the project folder, use Python 3.12.

```bash
python3.12 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
python -m jupyter lab fhn_project.ipynb
```

Select the environment's Python 3 kernel and run the cells in order. SciPy integrates the model and Matplotlib draws the figures. The notebook includes the first run's outputs for reference.

The next milestone is phase-plane and stability analysis. The optional PINN will train in Google Colab, and the report will compile in Overleaf.
