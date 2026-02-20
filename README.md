# GEOL0069_Assignments
# Sentinel-3 Altimetry Classification: Sea Ice vs. Leads

**Author**: Gareth Jiang  
**Student ID**: 23004877  
**Module**: GEOL0069 | Artificial Intelligence for Earth Observation  

---

## 1. Introduction
[cite_start]Monitoring the Arctic environment is crucial for understanding global climate change.  A key challenge in polar remote sensing is the accurate discrimination between **Sea Ice** and **Leads** (open water channels). This project utilizes high-resolution **Sentinel-3 altimetry data** to automate this classification process. [cite_start]By analyzing the physical properties of radar waveforms, we provide a robust method for large-scale surface type identification without the need for manual labeling. [cite: 43]

## 2. Methodology
[cite_start]Our approach employs unsupervised machine learning to group data based on its physical characteristics. [cite: 44, 46]

### 2.1 Feature Engineering
[cite_start]We extracted three primary features from the Sentinel-3 radar echoes to characterize the surface: [cite: 98]
* [cite_start]**Sigma0 ($\sigma^0$)**: Represents the backscattered power. [cite: 68]
* **Peakiness (PP)**: Measures the sharpness of the return. [cite_start]Leads typically act as specular reflectors, resulting in high peakiness. [cite: 68]
* **Stack Standard Deviation (SSD)**: Quantifies the variation of the return across multiple look angles.

### 2.2 Unsupervised Learning (GMM)
[cite_start]We implemented a **Gaussian Mixture Model (GMM)** to perform the clustering. [cite: 44, 66] [cite_start]Unlike traditional K-means, GMM is a probabilistic model that accounts for the covariance and shape of the data distribution, allowing for more flexible and accurate classification of complex altimetry signals. [cite: 67, 72]
![Clustered Results](clustered_mean_waveforms_class0-4.png)
*Figure 1: Mean waveforms generated from the unsupervised clustering process.*

## 3. Results
[cite_start]The model demonstrated exceptional performance, successfully capturing the distinct physical signatures of the Arctic surface. [cite: 83]

### 3.1 Physical Validation (Mean Waveforms)
[cite_start]The averaged waveforms for each class confirm the physical validity of our clustering. [cite: 85] The Lead class exhibits a sharp specular peak, while Sea Ice shows a broader, diffuse return.
![Mean Waveforms Comparison](mean_waveforms_lead_vs_ice.png)
*Figure 2: Direct comparison between Lead (specular) and Sea Ice (diffuse) mean waveforms.*

### 3.2 Individual Sample Stability
To ensure the model's consistency across the dataset, we inspected sub-sampled individual waveforms from both classes.
![Sea Ice Samples](sea_ice_individual_waveforms_subsampled.png)
![Lead Samples](leads_individual_waveforms_subsampled.png)
*Figure 3 & 4: Sub-sampled normalized individual waveforms for Sea Ice and Leads, demonstrating classification stability.*

### 3.3 Quantitative Performance
[cite_start]When validated against official ESA ground truth flags, the unsupervised approach achieved a remarkable classification accuracy. [cite: 43]
![Confusion Matrix](confusion_matrix_99.62pct.png)
*Figure 5: Confusion matrix showing a final validation accuracy of **99.62%**.*

## 4. Conclusion
[cite_start]This project successfully demonstrates that **Gaussian Mixture Models** are highly effective for identifying leads within sea ice using radar altimetry. [cite: 83] By focusing on physical feature extraction and probabilistic clustering, we achieved a **99.62% accuracy** rate. [cite_start]This automated workflow is essential for improving sea ice freeboard estimates and monitoring the evolving Arctic environment. 

---
**GitHub Repository**: [GEOL0069_Assignments](https://github.com/maisonjiang3-wq/GEOL0069_Assignments)
