# GEOL0069_Assignments
# Sentinel-3 Altimetry Classification: Sea Ice vs. Leads

**Name**: Gareth Jiang  
**Student ID**: 23004877  
**Module**: GEOL0069 | UCL Earth Sciences  

## 1. Project Overview
[cite_start]This project focuses on the automated discrimination between **Sea Ice** and **Leads** (open water channels) in the Arctic using **Sentinel-3 altimetry data**[cite: 10, 281]. [cite_start]By leveraging unsupervised machine learning, we categorize radar waveforms based on their physical return characteristics to better understand sea ice distribution[cite: 6, 7].

## 2. Key Results & Visualizations

### A. Raw Feature Distribution
We analyzed the relationship between **Sigma0** (backscatter coefficient) and **Peakiness**. [cite_start]These features are critical for identifying surface roughness[cite: 284, 491].
![Feature Distribution](替换为你的文件名1.png)
*Figure 1: Scatter plot of Sigma0 vs. Peakiness showing the initial separation of data points.*

### B. Gaussian Mixture Model (GMM) Clustering
[cite_start]Using an unsupervised GMM approach, the data was partitioned into two distinct clusters representing different surface types[cite: 68, 69].
![GMM Clustering](替换为你的文件名2.png)
*Figure 2: Results of GMM clustering in the feature space.*

### C. Mean Waveform Comparison (Physical Validation)
[cite_start]The most significant result is the distinct difference in the average echo shapes[cite: 670].
![Mean Waveforms](替换为你的文件名3.png)
*Figure 3: Average waveforms for Lead vs. Sea Ice. [cite_start]Leads exhibit a sharp specular peak, while Sea Ice shows a diffuse, lower-amplitude return[cite: 670].*

### D. Sub-sampled Waveform Variations
[cite_start]To ensure consistency, we visualized individual normalized samples from each class[cite: 320, 529].
![Waveform Samples](替换为你的文件名4.png)
*Figure 4: Normalized individual waveforms showing the stability of the classification across multiple samples.*

### E. Model Validation (Confusion Matrix)
[cite_start]The performance of our unsupervised model was validated against the official ESA surface type flags[cite: 598, 599].
![Confusion Matrix](替换为你的文件名5.png)
*Figure 5: The confusion matrix reveals a high classification accuracy of **99.62%**.*

## 3. Methodology
* [cite_start]**Data Source**: Sentinel-3 Altimetry Dataset[cite: 132].
* [cite_start]**Features**: Sigma0, Peakiness (PP), and Stack Standard Deviation (SSD)[cite: 491].
* [cite_start]**Algorithm**: Gaussian Mixture Model (GMM) with $n=2$ components[cite: 597].
* [cite_start]**Pre-processing**: NaN removal, dimension synchronization, and standardization[cite: 492, 494, 585].
