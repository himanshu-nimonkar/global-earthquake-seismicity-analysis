# Statistical and Probabilistic Characterization of Global Earthquakes (2000–2025)

![Methodology Flowchart](methodology_flowchart.png)

## Project Overview
This repository contains a single Jupyter Notebook that performs a complete statistical and probabilistic analysis of global earthquake seismicity from 2000 to 2025. The study analyzes approximately 2.8 million seismic events to identify fundamental patterns governing earthquake occurrence at a global scale.

The primary objective is to quantitatively separate independent background tectonic activity from dependent, triggered aftershock sequences. This separation is essential for accurate seismic hazard assessment and earthquake forecasting.

The analysis combines classical seismological laws with modern statistical point process models and spatio-temporal clustering techniques, implemented end-to-end within one notebook.

## Motivation
Earthquakes are a major natural hazard with significant societal and economic consequences. Modern seismic catalogs are large but statistically complex mixtures of independent and clustered events. Treating all earthquakes as independent leads to biased estimates of seismic risk.

This project addresses three core research questions:
1. At what magnitude is the global earthquake catalog complete and reliable?
2. What fraction of seismicity is true background activity versus triggered activity?
3. How do earthquakes cluster in space and time, and how does aftershock productivity scale with mainshock magnitude?

## Dataset
The analysis uses the USGS Global Earthquake Catalog accessed via Kaggle, spanning January 2000 through October 2025.

After cleaning and validation, the final dataset contains:
- 2,805,526 earthquake events
- Variables include event time, geographic location, depth, and magnitude (primarily Mw)

All data preprocessing is performed directly inside the notebook.

###Dataset Citation
If you use this dataset, please cite it as:
BwandoWando. Earthquakes around the world from 1900–2025. Kaggle, 2025. Available online: https://www.kaggle.com/datasets/bwandowando/earthquakes-around-the-world-from-1900-2025

## Methodology
The workflow follows the pipeline illustrated in the flowchart above and includes:

### Data Preparation and Exploratory Analysis
- Removal of incomplete or invalid records
- Filtering to physically plausible magnitudes and depths
- Exploratory analysis of magnitude distributions, spatial patterns, and temporal trends
- Verification of tectonic clustering and absence of seasonal effects

### Magnitude-Frequency Analysis
- Estimation of magnitude of completeness (Mc)
- Application of the Gutenberg-Richter law
- Visual and statistical validation of power-law behavior

### Statistical Modeling of Seismic Triggering
- Hawkes process modeling (temporal, magnitude-agnostic)
- ETAS-like modeling (temporal, magnitude-dependent)
- Omori law analysis of aftershock decay
- Comparative evaluation of physically realistic versus unrealistic triggering behavior

### Declustering and Clustering
- Separation of background and triggered events
- Spatio-temporal clustering using DBSCAN
- Identification of major global earthquake sequences

### Diagnostics and Uncertainty
- Parameter stability checks
- Model comparison diagnostics
- Interpretation of uncertainties and model limitations

## Key Results
- Magnitude of completeness: Mc ≈ 1.1  
- Gutenberg-Richter b-value: b ≈ 0.86  
- Background versus triggered seismicity:
  - Approximately 30% background events
  - Approximately 70% triggered events
- Strong spatio-temporal clustering consistent with Omori’s law and magnitude-dependent aftershock productivity

Magnitude-dependent ETAS-like models yield physically realistic results, while magnitude-agnostic Hawkes models substantially overestimate triggering at the global scale.

## How to Run
Download the dataset manually from Kaggle using the link above.
Place the downloaded CSV file in the project directory or update the path inside the notebook.
Open the notebook `stat.ipynb` in Jupyter and **run all cells from top to bottom**.
All preprocessing, modeling, plots, and results are generated entirely within the notebook.

## Reproducibility
This project is intentionally minimal. All logic, analysis, figures, and interpretation are contained in a single Jupyter Notebook to make the methodology easy to inspect, reproduce, and extend.

## Citation
If you use or build upon this work, please cite the accompanying academic report:

**Statistical and Probabilistic Characterization of Global Earthquakes (2000–2025)**  
Dhairye Gala and Himanshu Nimonkar  
University of California, Davis

## License
MIT License

## Authors
Dhairye Gala  
Himanshu Nimonkar
