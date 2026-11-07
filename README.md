# Mathematical Modelling Group Project (MAC F314)

**FitzHugh–Nagumo model of neuronal firing and excitability**

The [core notebook](fhn_project.ipynb) starts with the model equations and three voltage experiments. It then explains nullclines, phase portraits, local stability, the applied-current sweep, and sensitivity to the recovery parameter. Color-coded algorithm blocks introduce each set of commented Python cells.

## Run on a Mac

From the project folder, use Python 3.12.

```bash
python3.12 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
python -m jupyter lab fhn_project.ipynb
```

Select the environment's Python 3 kernel and run the cells in order. SciPy integrates the model and Matplotlib draws the figures. The notebook includes the executed results for reference.

Set `EXPORT_FIGURES = True` in the final code cell to save report figures as PDF for Overleaf and EPS for submission. The optional PINN will use a separate notebook in Google Colab.
