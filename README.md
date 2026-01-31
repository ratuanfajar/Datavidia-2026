# DataVidia 2026

A data science competition project analyzing environmental and air quality data in Jakarta, Indonesia.

## Project Overview

This project involves comprehensive analysis of Jakarta's environmental data including air quality indices (ISPU), weather patterns, population demographics, river water quality, and vegetation health. The goal is to build predictive models and extract insights from multiple interconnected environmental datasets spanning from 2010 to 2025.

## Dataset Description

The project utilizes multiple data sources organized by category:

### 1. Air Quality (ISPU - Indeks Standar Pencemar Udara)
- **Location**: `data/01-raw/ISPU/`
- **Time Range**: 2010-2025
- **Contents**: Daily air pollution standard indices for DKI Jakarta
- **Files**: Yearly datasets from 2010-2025, including 2023-2025 component data

### 2. Weather Data (Cuaca Harian)
- **Location**: `data/01-raw/cuaca-harian/`
- **Contents**: Daily weather measurements from 5 stations across Jakarta:
  - DKI1: Bundaran HI
  - DKI2: Kelapa Gading
  - DKI3: Jagakarsa
  - DKI4: Lubang Buaya
  - DKI5: Kebon Jeruk

### 3. Population Data (Jumlah Penduduk)
- **Location**: `data/01-raw/jumlah-penduduk/`
- **Time Range**: 2013-2021
- **Contents**: Population demographics by age group and gender in DKI Jakarta

### 4. River Water Quality (Kualitas Air Sungai)
- **Location**: `data/01-raw/kualitas-air-sungai/`
- **Contents**: Water quality measurements for Jakarta's rivers

### 5. Vegetation Index (NDVI)
- **Location**: `data/01-raw/NDVI (vegetation index)/`
- **Contents**: Normalized Difference Vegetation Index data for Jakarta

### 6. National Holidays & Weekends
- **Location**: `data/01-raw/libur-nasional/`
- **Contents**: Calendar data for holidays and weekends

## Directory Structure

```
.
├── README.md                 # Project documentation
├── pyproject.toml           # Project configuration and dependencies
├── data/
│   ├── 01-raw/              # Original, unprocessed data
│   │   ├── cuaca-harian/    # Daily weather data
│   │   ├── ISPU/            # Air quality indices
│   │   ├── jumlah-penduduk/ # Population data
│   │   ├── kualitas-air-sungai/ # River water quality
│   │   ├── libur-nasional/  # Holiday calendar
│   │   └── NDVI/            # Vegetation indices
│   ├── 02-cleaned/          # Processed and cleaned data
│   └── sample_submission.csv # Sample submission format
└── notebooks/               # Jupyter notebooks for analysis
    ├── formating.ipynb      # Data formatting and cleaning
    └── notebook.ipynb       # Exploratory data analysis
```

## Getting Started

### Prerequisites
- Python >= 3.12
- Virtual environment (recommended)

### Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd "DataVidia 2026"
```

2. Create and activate virtual environment:
```bash
python -m venv .venv
# On Windows:
.\.venv\Scripts\Activate.ps1
# On macOS/Linux:
source .venv/bin/activate
```

3. Install dependencies:
```bash
pip install -e .
```

### Dependencies

The project uses the following key libraries:
- **pandas** & **numpy**: Data manipulation and numerical computing
- **matplotlib** & **seaborn**: Data visualization
- **ipython** & **ipywidgets**: Interactive notebooks
- **ydata-profiling**: Automated data profiling and reporting

## Data Processing Pipeline

### Stage 1: Raw Data (01-raw/)
- Original datasets as downloaded from sources
- No modifications applied

### Stage 2: Cleaned Data (02-cleaned/)
- Processed and standardized datasets
- Data quality improvements and transformations

## Analysis

The project includes Jupyter notebooks for:
- **Exploratory Data Analysis**: Initial data exploration and visualization
- **Data Formatting**: Cleaning and preprocessing steps
- Pattern identification and feature engineering

## Project Goals

1. **Data Integration**: Combine multiple environmental datasets
2. **Pattern Discovery**: Identify relationships between air quality and environmental factors
3. **Predictive Modeling**: Build models to forecast air quality and environmental metrics
4. **Visualization**: Create insights through data visualization
5. **Competition Submission**: Generate predictions in required format

## Usage

### Running Notebooks
```bash
jupyter notebook notebooks/
```

### Loading Data
```python
import pandas as pd

# Load air quality data
ispu = pd.read_csv('data/01-raw/ISPU/data-indeks-standar-pencemar-udara-(ispu)-di-provinsi-dki-jakarta-komponen-data-2024.csv')

# Load weather data
weather = pd.read_csv('data/01-raw/cuaca-harian/cuaca-harian-dki1-bundaranhi.csv')
```

## Data Sources

All data has been sourced from official Jakarta environmental and demographic databases. The raw data maintains its original format and encoding for traceability.

## Notes

- All timestamps are in Jakarta timezone (WIB - Western Indonesia Time)
- Some datasets may have gaps in historical data
- Data cleaning and preprocessing steps are documented in `notebooks/formating.ipynb`

## License

This project is part of the DataVidia 2026 competition.

## Contact & Support

For questions or issues related to this project, please refer to the competition guidelines.

---

Last Updated: January 31, 2026
