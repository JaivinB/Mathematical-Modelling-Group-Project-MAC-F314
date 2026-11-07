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

## LaTeX report

The [editable report](report/main.tex) uses [BibTeX references](report/references.bib) and [four figures](report/figures). The [compiled PDF](report/report.pdf) contains the core analysis and numerical results.

To compile in Overleaf, upload the contents of the report folder and select `main.tex` as the main document with pdfLaTeX. The report includes PDF copies of the figures. Keep the matching EPS files for submission.

Set `EXPORT_FIGURES = True` in the final notebook cell to regenerate the figure pairs. The optional PINN uses a separate notebook in Google Colab.
