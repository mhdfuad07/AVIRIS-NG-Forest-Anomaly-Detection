# Detection of Anomalies in Hyperspectral Imagery in a Forest Environment

**A preliminary hyperspectral remote sensing study using AVIRIS-NG data and Python.**

## Project Overview

This project investigates the use of hyperspectral imagery to identify unusual spectral variations in a forest environment.

The study uses AVIRIS-NG Level-2 surface reflectance data from NASA's Arctic-Boreal Vulnerability Experiment (ABoVE). A selected region of the image is analysed to examine vegetation spectral characteristics and identify pixels whose spectral responses differ from the regional background.

The current implementation focuses on preliminary data analysis and a baseline anomaly detection approach using Euclidean spectral distance.

## Dataset

- **Sensor:** AVIRIS-NG (Airborne Visible/Infrared Imaging Spectrometer – Next Generation)
- **Project:** NASA ABoVE
- **Acquisition date:** 19 August 2022
- **Data product:** Level-2 Surface Reflectance
- **Original image dimensions:** 3974 × 670 pixels
- **Original spectral bands:** 425
- **Wavelength range:** Approximately 377–2501 nm
- **Spatial resolution:** 4.6 m

**Dataset source:** [NASA ORNL DAAC – ABoVE AVIRIS-NG Data](https://doi.org/10.3334/ORNLDAAC/2362)

The original dataset is not included in this repository because of its large file size. Please obtain it from the original data provider.

## Methodology

The preliminary workflow includes:

1. Loading the AVIRIS-NG hyperspectral dataset and examining its metadata.
2. Inspecting spectral bands and identifying unreliable bands using the provider-supplied Band Quality List (BBL).
3. Performing additional statistical and visual quality assessment.
4. Extracting a 500 × 500 pixel study region.
5. Generating RGB composites and visualising individual spectral bands.
6. Analysing pixel spectral signatures.
7. Calculating mean spectral reflectance and standard deviation.
8. Applying Euclidean spectral distance for preliminary anomaly detection.
9. Using a percentile-based threshold to identify potentially anomalous pixels.

## Preliminary Results

After spectral quality assessment, **378 spectral bands** were selected for the analysis.

The selected study region contains:

- **Spatial dimensions:** 500 × 500 pixels
- **Total pixels analysed:** 250,000
- **Selected spectral bands:** 378

The Euclidean spectral distance was calculated between each pixel spectrum and the mean spectrum of the selected region.

Using the 99th-percentile threshold:

- **Threshold:** 2.39187
- **Potentially anomalous pixels:** 2,500
- **Percentage of selected pixels:** 1%

These pixels exhibit spectral responses that differ from the regional mean.

**Important:** The detected pixels are potential spectral anomalies, not confirmed cases of vegetation stress, disease, fire damage or other forest disturbances. Further investigation is required to determine their environmental significance.

## Tools and Technologies

- Python
- Jupyter Notebook
- NumPy
- Matplotlib
- Spectral Python (SPy)
- Hyperspectral remote sensing
- AVIRIS-NG data analysis

## Repository Structure

```text
AVIRIS-NG-Forest-Anomaly-Detection/
│
├── AVIRIS_Forest_Hyperspectral.ipynb
├── README.md
└── report/
    └── project_report.pdf
```

*The repository structure will be updated as additional project files are added.*

## Future Scope

The following improvements are planned:

- Investigation of the spatial locations and spectral signatures of high-scoring pixels.
- Principal Component Analysis (PCA) for dimensionality reduction.
- Implementation of the Reed–Xiaoli (RX) anomaly detection algorithm.
- Comparison of Euclidean distance, PCA-based approaches and RX detection.
- Further investigation of hyperspectral anomaly detection for vegetation monitoring.

## References

1. Miller et al. (2019). *ABoVE: AVIRIS-NG Imaging Spectroscopy for Alaska, Canada, and Iceland, 2017–2022, V3*. ORNL DAAC. https://doi.org/10.3334/ORNLDAAC/2362
2. Reed, I. S. and Yu, X. (1990). *Adaptive Multiple-Band CFAR Detection of an Optical Pattern with Unknown Spectral Distribution.*
3. Manolakis, D. and Shaw, G. (2002). *Detection algorithms for hyperspectral imaging applications.*
4. Stein, D. W. et al. (2002). *Anomaly detection from hyperspectral imagery.*

---

**Project status:** Preliminary analysis completed; advanced anomaly detection methods planned.

**Course:** Principles of Remote Sensing and Digital Image Analysis (ES321M)  
**Institution:** Indian Institute of Space Science and Technology (IIST)
