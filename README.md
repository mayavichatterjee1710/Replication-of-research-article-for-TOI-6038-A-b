# Analysis & Demographic Context of the Dense Sub-Saturn TOI-6038 A b

An independent, open-science replication pipeline targeting the parameters of the close-in exoplanet **TOI-6038 A b** using space-based photometry and global catalogue data. 

Directly replicating core methodology and demographic findings from *Baliwal et al., 2025, AJ, 169, 147*.

## Project Objective
This pipeline independently extracts time-series photometry from NASA's TESS mission to discover, phase-fold, and analyse the geometric properties of the sub-Saturn exoplanet TOI-6038 A b. Additionally, it queries the live NASA Exoplanet Archive to contextualise the planet's anomalously high bulk density within the broader "Exo-Neptunian Landscape."

## Core Features & Methodology
* **Archival Mining:** Programmatic target resolution across multi-wavelength catalogs (TIC, 2MASS, Gaia DR3) using `astroquery`.
* **Signal Processing:** Implemented 5-sigma standard deviation outlier rejection to shield the time series from cosmic ray spikes while preserving planetary transit depths.
* **Period Detection:** Blind signal discovery utilising a Box Least Squares (BLS) algorithm to isolate the regular orbital clock of the planet.
* **Demographic Filtering:** Automated data wrangling via `pandas` to isolate highly characterised sub-Saturn systems (mass/radius uncertainties < 20%).

## Key Visualizations & Replication Proofs

### 1. Phase-Folded Transit Architecture
Stacking four distinct transit events from TESS Sector 18 reveals the clean, flat-bottomed U-shape characteristic of a gas giant occultation. 
* *Measured Transit Depth:* ~0.00144 (Perfect alignment with the published literature value of 0.001442).

<!-- PRO-TIP: You can download your Colab plots as PNGs, upload them to your repo, and display them here! -->
![Phase Folded Transit](notebooks/plots/phase_folded_transit.png)

### 2. The Density-Period Demographic Landscape
Contextualising our target among 70 elite, precisely characterised sub-Saturns reveals that TOI-6038 A b hovers above the typical 1.0 g cm⁻³ density ceiling of the Neptunian Savanna, sitting right on the razor-thin transition line of the high-density Neptunian Ridge.

![Demographic Landscape](notebooks/plots/density_period_landscape.png)

## Dependencies & Installation
To run the analysis notebook locally or in a virtual environment, install the required packages:
```bash
pip install -r requirements.txt
