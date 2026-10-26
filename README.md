# Signal Cleaning and Filtering

## 1. Project Overview

This project investigates EEG signal cleaning and filtering across four workload conditions: Rest, Low, Medium, and High. The analysis combines EEGLAB-based preprocessing with Python-based signal processing, spectral analysis, filter comparison, and scalp topography visualization.

## 2. Dataset

- Data format: EDF
- Conditions: Rest, Low, Medium, High
- Sampling frequency: 512 Hz
- Number of channels after channel-label cleaning: 26
- Recording duration: varies by condition

The original recordings were retained separately from the derived analysis outputs.

## 3. Software and Libraries

- MATLAB: R2020a[insert version]
- EEGLAB: 2026.1.0[insert version]
- Python: 3.13.16[insert version]
- MNE-Python: 1.13.2[insert version]
- NumPy: 2.1.3[insert version]
- SciPy: 1.16.3[insert version]
- pandas: 3.0.6[insert version]
- Matplotlib: 3.10.0[insert version]
- Jupyter / Google Colab: Google Colab environment

## 4. Preprocessing and Filtering

The workflow included inspection of the raw EEG recordings, power spectral density (PSD) analysis, notch filtering, band-pass filtering, and comparison of filtered signals.

The notch filter was configured to suppress power-line interference around 50 Hz, using a 49–51 Hz rejection band.

The Python filter comparison included:

- FIR causal filter
- FIR zero-phase filter
- IIR causal filter
- IIR zero-phase filter

Python band-pass filtering used a 1–45 Hz passband. The FIR filter used a Hamming window with order 330. The IIR filter used a fourth-order Butterworth design.

The four filter implementations were compared using time-domain signals, frequency responses, estimated delay, and edge-region RMS measurements.

## 5. Spectral Analysis

Welch's method was used to estimate PSDs. Absolute band power was calculated for the following frequency ranges:

- Delta: 1–4 Hz
- Theta: 4–8 Hz
- Alpha: 8–13 Hz
- Beta: 13–30 Hz
- Gamma: 30–45 Hz

Band-power summaries and scalp maps were generated for the four conditions.

## 6. Output Files

- `Copy of EEG-Assignment02.ipynb`: Python notebook
- `Copy of EEG-Assignment02.py`: exported Python script
- `Copy of EEG-Assignment02.html`: HTML export of the notebook
- `report.pdf`: final report
- `figures/`: Python-generated figures
- `EEGLAB_screens/`: screenshots documenting the EEGLAB workflow
- CSV files: band-power results, percentage changes, filter-delay estimates, and edge-effect measurements

## 7. Reproducibility Notes

The notebook should be run in an environment with the required Python libraries installed and access to the four EDF recordings. File paths may need to be updated when running outside the original Google Colab environment.

The band-power comparisons are descriptive and do not establish statistical significance. Filter-delay estimates depend on the selected signal segment and the estimation method.

## 8. Limitations

Results may be affected by artifacts, filtering choices, edge effects, channel selection, and the characteristics of the individual recordings. The analysis should not be interpreted as evidence of statistically significant workload-related differences without appropriate statistical testing.
