# UAV propulsion fault detection

Python analyses of X/Y/Z accelerometer recordings for healthy propulsion, trimmed propeller blades and added-mass imbalance. The project includes FFT/PSD processing, vibration features, illustrative force models and sine-plus-Gaussian comparisons. These are descriptive analyses; a trained fault classifier and independent-flight validation remain future work.

## Folder guide

| Folder | Contents |
| --- | --- |
| graphs/ | All 20 unique scientific graphs, grouped into six analyses; plus a visual overview. |
| code/ | Documented Python scripts, local helpers and one central runner. |
| data/raw/ | Instructions and checksums; the five original workbooks are kept locally and excluded from Git. |
| results/ | Numerical spectra, features, generated model series, parameters and audit/validation JSON. |
| references/ | Source references; local PDF copies, text extracts and page previews are excluded from Git. |

## Regenerate graphs

Python 3.10 or newer:

```text
python -m pip install -r requirements.txt
python code/run_analysis.py --list
python code/run_analysis.py mass_damage_model --output-root .cache/first_run
```
