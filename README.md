# UAV Propulsion Fault Detection

A hackathon project combining vibration-based fault detection and CAD models for UAV propulsion condition monitoring. The project brings together propeller blade damage detection and bearing fault detection.

## Repository contents

- **[Propeller damage detection](propeller_damage_detection.zip):** Python code, configuration files and supporting project files. The pipeline uses X/Y accelerometer recordings, FFT-based power spectra, automatic peak features and logistic regression to classify propeller condition as undamaged or damaged.
- **Bearing fault detection:** A separate module for analysing vibration signatures associated with bearing faults.
- **CAD models:** Design files supporting the propulsion monitoring project.

## Getting started

1. Download and extract the ZIP for the module you want to use.
2. Follow its documentation to install dependencies and prepare the input data.
3. Run training or load a saved model to analyse a recording.
4. Review the predictions, validation results and graphs.

For propeller setup, commands and the signal-processing workflow, see the [propeller documentation](README_PROPELLER.md).

Performance depends on the dataset, sensor placement and operating conditions. Results should be validated on representative flights before use on a different UAV.
