# Data Driven Structural Health Monitoring

## Background

Engineering infrastructure such as chemical plants, aircraft, or nuclear power stations are very expensive and safety-critical. To ensure safe operation, they are periodically inspected using non-destructive testing techniques such as ultrasound inspection. This process, while vital, is costly and carried out relatively infrequently. An alternative is to monitor the state of a structure at all times using permanently installed sensors.

One highly promising technology for this is to make **ultrasonic guided wave measurements** using such a network of attached sensors. High-frequency sound from installed sensors propagates in all directions to monitor components from a small number of locations. If multiple pairs of sensors are used, then the state of a structure may be imaged using standard focusing algorithms.

In theory, this is straightforward; however, the sound reflects from all features in the structure. The resulting recorded time responses are therefore complicated by echoes from all geometry. 

In an ideal scenario, the complexity of the signals may be suppressed by subtracting reference data captured earlier when the structure is in a known condition. If the structure remains unchanged, subtraction will show no difference. If damage has appeared, it will remain after subtraction of the reference data, as illustrated in **Figure 1b**.

In real conditions, factors such as temperature, load, and humidity can have dramatic effects on this subtraction process, reducing the ability to suppress background features and reveal damage. This mini-project aims to address this challenge using **data-driven approaches** to improve the performance of subtraction-based methods.

---

## Project Description

A **water tank** behind the Queens Building was instrumented with a network of **9 ultrasonic sensors** in 2012. An automated data acquisition system recorded signals roughly every 15 minutes for 10 years. Although there were interruptions due to equipment failures and refurbishments, this produced a large dataset.

The overall aim is to use this data to **develop data-driven methods** to improve the subtraction process in ultrasonic guided wave SHM. Several approaches are proposed, as outlined below.

### Potential Approaches

1. **Sensor Pair Basis:**  
   Analyze data on a per-sensor-pair basis to suppress structural features in ultrasonic responses.  
   Each pair is treated independently.

2. **Image Basis:**  
   Convert data from each sensor pair into structural images and develop processing methods to improve reference subtraction and suppress non-defect features.

3. **Hybrid Approach:**  
   Combine the above two methods to leverage their respective advantages.

Each method can offer efficient solutions with specific trade-offs. A brute-force approach based on baseline fitting is discussed in [2], while more recent **machine learning methods** ([3], [4]) have shown promising results in improving subtraction robustness.

---

## Data

Data is provided for **four sensor pairs** from this structure over the full experiment duration, including measurements with induced damage. A setup description file (sensor locations, conditions, etc.) is also provided.  

This dataset is sufficient to:
- Produce **images of the structure**, or
- Demonstrate the **robustness** of developed subtraction/improvement techniques across multiple sensor pairs.

---
## Repository Contents
This repository contains scripts, notebooks, and reports for data analysis, spectral modeling, classification, and forecasting tasks.

### Reports
- **Group_report.pdf** – Collaborative group submission outlining overall methodology and findings.  
- **Individual_report.pdf** – Personal report documenting independent contributions and technical analyses.  

### Core Notebooks
| Notebook | Description |
|-----------|--------------|
| **data1_analysis.ipynb** | Extracts and visualizes sensor pair configurations, transmitter/receiver geometry, and defect positions from the raw `.mat` dataset. Includes sensor network mapping and structural layout visualization. |
| **pair3_analysis.ipynb** | Performs detailed signal inspection for sensor pair 3, including time-series visualization, signal subtraction, and defect-related comparisons. Also handles date conversion and defect event plotting. |
| **Spectral_analysis.ipynb** | Converts time-domain waveforms into the frequency domain using FFT. Applies Random Forest classification to detect defects based on spectral differences between pristine and defective signals.|
| **Spectral_analysis_decisiontree.ipynb** | Extends spectral analysis with a Decision Tree approach for multi-class defect type identification. Visualizes FFT spectra for multiple damage states. |
| **classifier.ipynb** | Implements LSTM classifiers to distinguish pristine vs defect states. |
| **lstm_pair3.ipynb** | LSTM model for sequential prediction on time-series data from sensor pair 3. The model reconstructs normal signals and detects anomalies through increased prediction errors (MSE spikes indicate damage). |
| **weather.ipynb** | Analyzes environmental factors such as temperature and humidity to study their influence on ultrasonic signal variations. Provides insight into noise and drift reduction strategies. |

---
