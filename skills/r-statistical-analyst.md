# R Statistical Analyst

Conduct rigorous statistical analysis in R suitable for publication in top-tier social science journals. This skill performs analysis—not just advice—using best practices in econometrics, causal inference, and quantitative methods.

## When to Use

Invoke when:
- Conducting statistical analysis in R
- Implementing causal inference designs (DiD, RD, IV, synthetic control)
- Running and interpreting regression models
- Producing publication-ready tables and figures
- Ensuring methodological rigor and robustness

## Tutorial Guides

Read the relevant guide before writing code. Guides are in `r-statistical-techniques/` (relative to this file):

| Guide | Topics |
|-------|--------|
| `01_core_econometrics.md` | TWFE, DiD, Event Studies, RD, IV, Matching, Mediation |
| `02_survey_resampling.md` | Survey weights, Bootstrap, Oaxaca, List Experiments |
| `03_text_ml.md` | LDA, STM, Sentiment, Causal Forests, GAMs, EFA/CFA/IRT |
| `04_synthetic_control.md` | Synth, gsynth, Matrix Completion, Synthetic DiD |
| `05_bayesian_sensitivity.md` | brms, sensemakr, OVB Bounds |
| `06_visualization.md` | ggplot2, coefplot, etable, patchwork |
| `07_best_practices.md` | Reproducibility, Project Structure, Code Style |
| `08_nonlinear_models.md` | LPM vs Logit, Poisson/PPML, Marginal Effects |

## Running R Code

### Execution Method

Run `.R` scripts from the command line:

```bash
Rscript filename.R
```

Or for interactive output with plots:

```bash
R --vanilla < filename.R
```

### Check if R is Available

Before running analysis, verify R is installed:

```bash
which R || which Rscript || echo "R not found"
```

Check version and key packages:

```bash
Rscript -e "sessionInfo()"
```

### If R Is Not Found

1. **Check common locations:**
   - macOS: `/usr/local/bin/R` or via Homebrew
   - Linux: `/usr/bin/R`
   - Windows: `C:\Program Files\R\`

2. **Ask the user** for their R installation path

3. **If not installed:** Inform the user that R is required and provide the code as `.R` files they can run when R is available. Point them to https://cran.r-project.org/ for installation.

### Installing Missing Packages

If packages are missing, install them:

```r
# Check and install missing packages
required_packages <- c("tidyverse", "fixest", "modelsummary", "did")
missing <- required_packages[!required_packages %in% installed.packages()[,"Package"]]
if (length(missing) > 0) install.packages(missing)
```

### Alternative: Write Code Only

If R cannot be executed, write complete `.R` scripts with clear comments. The user can run them later in RStudio or after installing R.

## Instructions

1. **Read the relevant guide(s)** before writing any code
2. **Use exact code patterns** from the guides—they are tested and working
3. **Use built-in datasets** for examples; adapt patterns to user's data
4. **Follow publication standards**: clustered SEs, robustness checks, sensitivity analysis
5. **Produce complete analysis**: tables, figures, and interpretation
6. **Cite assumptions and limitations** appropriate to the method
