# Stata Statistical Analyst

Conduct rigorous statistical analysis in Stata suitable for publication in top-tier social science journals. This skill performs analysis—not just advice—using best practices in econometrics, causal inference, and quantitative methods.

## When to Use

Invoke when:
- Conducting statistical analysis in Stata
- Implementing causal inference designs (DiD, RD, IV, synthetic control)
- Running and interpreting regression models
- Producing publication-ready tables and figures
- Ensuring methodological rigor and robustness

## Tutorial Guides

Read the relevant guide before writing code. Guides are in `stata-statistical-techniques/` (relative to this file):

| Guide | Topics |
|-------|--------|
| `00_data_prep.md` | Import, merge, missing data, transforms, panel setup |
| `01_core_econometrics.md` | TWFE, DiD, Event Studies, IV, Matching, Mediation, Reporting Checklists |
| `02_survey_resampling.md` | Survey weights, Bootstrap, Oaxaca, Randomization Inference |
| `03_synthetic_control.md` | synth for comparative case studies |
| `04_visualization.md` | esttab, coefplot, graphs, summary statistics |
| `05_best_practices.md` | Master scripts, path management, code organization |
| `06_modeling_basics.md` | OLS, logit/probit, Poisson, margins, interactions |
| `07_postestimation_reporting.md` | Estimates workflow, Table 1, predicted values, diagnostics |
| `99_default_journal_pipeline.md` | Complete project template, submission checklist |

**Start with `00_index.md`** for a quick lookup by method and the recommended workflow sequence.

## Running Stata Code

### Execution Method

Run `.do` files in batch mode:

```bash
# -e flag: batch mode, ASCII log, exit when done
stata -e do filename.do
```

This executes `filename.do` and creates `filename.log` with all output.

**Options:**
- `-e` — Batch mode, ASCII log, **exits automatically** when done (recommended)
- `-b` — Batch mode, ASCII log, waits for user to close Stata
- `-s` — Batch mode, SMCL log format
- `-q` — Suppress initialization messages

### Check if Stata is Available

```bash
which stata || which StataMP || which StataSE || echo "Stata not found"
```

### Platform-Specific Paths

**macOS:** The executable is inside the app bundle:
- Stata/MP: `/Applications/Stata/StataMP.app/Contents/MacOS/StataMP`
- Stata/SE: `/Applications/Stata/StataSE.app/Contents/MacOS/StataSE`
- Stata: `/Applications/Stata/Stata.app/Contents/MacOS/Stata`

Add to PATH in `~/.zshrc` or `~/.bash_profile`:
```bash
export PATH="/Applications/Stata/StataMP.app/Contents/MacOS:$PATH"
```

Then run with:
```bash
StataMP -e do filename.do
```

**Linux:** `/usr/local/stata/stata` (or `stata-mp`, `stata-se`)

**Windows:** `C:\Program Files\Stata\Stata.exe` (or `StataMP.exe`, `StataSE.exe`)

### If Stata Is Not Found

1. **Ask the user** for their Stata installation path and version (MP, SE, or IC)
2. **If not installed:** Inform the user that Stata is required and provide the code as `.do` files they can run when Stata is available

### Alternative: Write Code Only

If Stata cannot be executed, write complete `.do` files with clear comments. The user can run them later in Stata's GUI or after installing the software.

## Instructions

1. **Read the relevant guide(s)** before writing any code
2. **Use exact code patterns** from the guides—they are tested and working
3. **Use built-in datasets** for examples; adapt patterns to user's data
4. **Follow publication standards**: clustered SEs, robustness checks, sensitivity analysis
5. **Produce complete analysis**: tables, figures, and interpretation
6. **Cite assumptions and limitations** appropriate to the method
