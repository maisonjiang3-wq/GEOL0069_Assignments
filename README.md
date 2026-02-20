# GEOL0069_Assignments
# Unsupervised Classification of Sea Ice and Leads (Sentinel-3 Altimetry)

**Author**: Gareth Jiang  
**Student ID**: 23004877  
**Module**: GEOL0069 | Artificial Intelligence for Earth Observation  

---

## 1. Introduction
The Arctic environment is a critical indicator of global climate change. A major challenge in polar remote sensing is accurately distinguishing between **Sea Ice** and **Leads** (open water channels). This project utilizes high-resolution **Sentinel-3 altimetry data** to automate the surface type identification process. By analyzing radar waveforms through unsupervised learning, we provide a robust methodology for monitoring ice distribution without the need for manual labeling.

## 2. Methodology
The workflow focuses on physical feature engineering and probabilistic clustering.

### 2.1 Feature Engineering
Three primary physical parameters were extracted from the Sentinel-3 radar echoes:
* **Sigma0 ($\sigma^0$)**: The backscatter coefficient representing the power of the return signal.
* **Peakiness (PP)**: A measure of the echo's sharpness. Leads act as specular reflectors, producing significantly higher peakiness than sea ice.
* **Stack Standard Deviation (SSD)**: Quantifies the variation of the return across multiple look angles.

### 2.2 Unsupervised Learning (GMM)
We implemented a **Gaussian Mixture Model (GMM)** for the clustering task. Unlike K-means, GMM accounts for the shape and covariance of data distributions, allowing for a more flexible and physically accurate classification of complex altimetry signals.
![GMM Clustering Results](clustered_mean_waveforms_class0-4.png)
*Figure 1: Initial classification results showing clustered mean waveforms.*

## 3. Results
The model successfully captured the distinct physical signatures of the Arctic surface with high precision.

### 3.1 Physical Validation (Mean Waveforms)
The comparison of mean waveforms confirms the validity of the clustering. The Lead class displays a sharp, specular peak, whereas the Sea Ice class exhibits a broader, diffuse return.
![Mean Waveforms Comparison](mean_waveforms_lead_vs_ice.png)
*Figure 2: Physical signature comparison between Lead (specular) and Sea Ice (diffuse) echoes.*

### 3.2 Individual Sample Stability
To ensure consistency, sub-sampled individual waveforms from both classes were inspected. The results demonstrate high stability in the classification across the entire dataset.
![Sea Ice Samples](sea_ice_individual_waveforms_subsampled.png)
![Lead Samples](leads_individual_waveforms_subsampled.png)
*Figure 3 & 4: Sub-sampled normalized individual waveforms for Sea Ice and Leads.*

### 3.3 Quantitative Performance
When validated against the official ESA ground truth flags, the unsupervised approach achieved an outstanding accuracy of **99.62%**.
![Confusion Matrix](confusion_matrix_99.62pct.png)
*Figure 5: Confusion matrix showing the final validation accuracy of 99.62%.*

## 4. Conclusion
This project demonstrates that **Gaussian Mixture Models** are highly effective for automated Arctic surface classification. By leveraging physical features such as Peakiness and Sigma0, we achieved near-perfect alignment (99.62%) with official data. This automated workflow is essential for improving sea ice freeboard estimates and large-scale environmental monitoring.
