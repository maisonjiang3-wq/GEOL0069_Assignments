# GEOL0069_Assignments
# Sentinel-3 Altimetry Classification: Sea Ice vs. Leads

## Project Overview
This project focuses on the automated discrimination between **Sea Ice** and **Leads** (open water channels) in the Arctic using **Sentinel-3 altimetry data**. By leveraging unsupervised machine learning, we categorize radar waveforms based on their physical return characteristics.

## Key Methodology
* **Feature Extraction**: Extracted key physical parameters from the radar echoes, including **Sigma0**, **Peakiness (PP)**, and **Stack Standard Deviation (SSD)**.
* [cite_start]**Machine Learning**: Implemented a **Gaussian Mixture Model (GMM)** to perform unsupervised clustering into two primary classes[cite: 597, 688].
* [cite_start]**Data Pre-processing**: Conducted rigorous data cleaning, including NaN removal and feature standardization using `StandardScaler`[cite: 494, 580].

## Major Results
* **High Precision**: The model achieved a final classification accuracy of **99.62%** when validated against official ESA surface type flags.
* **Waveform Validation**: 
    * [cite_start]**Leads**: Identified by sharp, specular peaks with high peakiness values[cite: 670].
    * [cite_start]**Sea Ice**: Characterized by diffuse, lower-amplitude returns[cite: 670].

## How to Run
The analysis is contained within `Chapter1_Unsupervised_Learning_Methods_Michel.ipynb`. You can open this directly in Google Colab using the link provided at the top of the notebook file.

## Acknowledgments
This research was conducted as part of the **GEOL0069** module at University College London (UCL).
