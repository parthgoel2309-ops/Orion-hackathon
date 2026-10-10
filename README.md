# UAV propulsion fault detection

Python analyses of X/Y/Z accelerometer recordings for healthy propulsion, trimmed propeller blades and added-mass imbalance. The project includes FFT/PSD processing, vibration features, illustrative force models and sine-plus-Gaussian comparisons. These are descriptive analyses; a trained fault classifier and independent-flight validation remain future work.

Start with the [graph gallery](docs/graph_gallery.html) for thumbnails, or the [graph index](docs/GRAPH_INDEX.md) for a searchable list. The latest three-way FFT comparison is in [graphs/06_mass_damage_sine_gaussian](graphs/06_mass_damage_sine_gaussian/). All five measured conditions are in [graphs/04_all_five_conditions](graphs/04_all_five_conditions/).

## Folder guide

| Folder | Contents |
| --- | --- |
| graphs/ | All 20 unique scientific graphs, grouped into six analyses; plus a visual overview. |
| code/ | Documented Python scripts, local helpers and one central runner. |
| data/raw/ | Instructions and checksums; the five original workbooks are kept locally and excluded from Git. |
| data/extracted/ | Read-only measurement excerpts, grouped by the analysis that consumes them. |
| results/ | Numerical spectra, features, generated model series, parameters and audit/validation JSON. |
| docs/ | Graph gallery, graph index, methods, reproduction guide and original analysis notes. |
| references/ | Source references; local PDF copies, text extracts and page previews are excluded from Git. |
| archive/ | Local previous-workspace snapshots, excluded from Git. |
| .cache/ | Local temporary run staging, excluded from Git. |

## Regenerate graphs

Python 3.10 or newer:

```text
python -m pip install -r requirements.txt
python code/run_analysis.py --list
python code/run_analysis.py mass_damage_model --output-root .cache/first_run
```

The first-run command uses the committed CSV extracts and saves a separate result tree, preserving the delivered figures. The runner verifies analyses that have dedicated verification scripts, then separates graphs, measurement excerpts, numerical results and generated notes into their folders.

To rerun all six analyses, place the five original Excel workbooks in `data/raw/` and run `python code/run_analysis.py all`. Alternatively use `--raw-dir "path/to/workbooks"`. The `healthy_damage` and `all_five` analyses require full workbooks; the other four work from included extracts or simulation settings. Running without `--output-root` updates the corresponding generated files in the project.

See **docs/REPRODUCE.md** for individual commands, **docs/CODE_GUIDE.md** for script roles and controls, and **docs/METHODS.md** for assumptions and units. No classifier has been trained in these analyses. Window comparisons are descriptive and do not establish accuracy on independent flights.

## Working as a team

See [CONTRIBUTING.md](CONTRIBUTING.md) for setup and branch workflow. [docs/GIT_SETUP.md](docs/GIT_SETUP.md) describes the local repository and how to connect a remote. Source publications are listed in [references/SOURCES.md](references/SOURCES.md).

## Organisation audit

The reorganisation preserved source file contents. The original local workspace also retains organisation manifests, validation logs and an archive. These machine-specific files are excluded from Git. The scientific validation reports in `results/` are included.

Prior local chat links referring to `outputs/` now correspond to `archive/legacy_workspace/outputs/`. Prefer the new graphs and documentation folders for current work. The one-time organisation scripts expect that local archive and are not required to reproduce analyses from a fresh clone.
