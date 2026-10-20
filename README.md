# Electric Vehicle Specifications Analysis | Python & Machine Learning

**Exploratory Data Analysis | Hypothesis Testing | Correlation Analysis | K-Means Clustering**

## Project Overview

This project analyzes electric vehicle specifications to investigate performance, efficiency, driving range, and similarities between vehicle models.

Using Python, statistical analysis, and unsupervised machine learning, the analysis explores how EV specifications relate to one another and identifies groups of vehicles with similar technical characteristics.

## Business Questions

The project addresses several analytical questions:

1. Which electric vehicle models have the highest top speeds and driving ranges?
2. Which brands and models demonstrate the greatest energy efficiency?
3. Is battery capacity significantly correlated with driving range?
4. Do vehicles with higher top speeds generally accelerate faster?
5. Can electric vehicles be grouped into meaningful segments using their specifications?

## Dataset

**Source:** [Electric Vehicle Specifications Dataset 2025 — Kaggle](https://www.kaggle.com/datasets/urvishahir/electric-vehicle-specifications-dataset-2025)

The dataset contains technical specifications of EV models, including:

| Category | Features |
|---|---|
| Vehicle details | Brand, model, body type, segment |
| Battery and efficiency | Battery capacity (kWh), efficiency (Wh/km), range (km) |
| Performance | Top speed (km/h), acceleration (0–100 km/h), torque (Nm) |
| Charging | DC fast-charging power, charging port |
| Practical specifications | Seats, towing capacity, cargo volume |
| Physical dimensions | Length, width, height |
| Drivetrain | AWD, RWD, FWD |

The dataset is available in the repository as `ev_sales.csv`.

## Tools and Technologies

| Technology | Purpose |
|---|---|
| Python | Data analysis |
| pandas, NumPy | Data exploration and manipulation |
| Matplotlib, Seaborn | Statistical visualization |
| SciPy | Pearson correlation and statistical hypothesis testing |
| scikit-learn | Standardization, K-Means clustering, silhouette evaluation, PCA |
| Jupyter Notebook | Analysis and documentation |

## Methodology

### 1. Exploratory Data Analysis

Explored vehicle specifications by brand, body type, top speed, efficiency, battery capacity, and driving range.

Selected observations include:

- The Maserati GranTurismo Folgore has the highest recorded top speed at 325 km/h.
- The Dacia Spring Electric 45 has the lowest reported consumption at 109 Wh/km.
- The Mercedes-Benz EQS 450+ has the highest recorded driving range at 685 km.
- Mercedes-Benz has 42 models represented in the dataset.

### 2. Statistical Hypothesis Testing

**Research question:** Is battery capacity positively associated with driving range?

- **Null hypothesis (H₀):** Battery capacity and driving range are not correlated.
- **Alternative hypothesis (H₁):** Battery capacity and driving range have a positive correlation.

Pearson correlation analysis indicated a strong positive relationship. The notebook reports a p-value below 0.05, supporting rejection of the null hypothesis.

**Interpretation:** Vehicles with larger batteries tend to have longer driving ranges, although other factors such as efficiency, vehicle weight, and design can also influence range.

### 3. Correlation Analysis

Investigated the relationship between vehicle top speed and acceleration time.

**Reported Pearson correlation:** `r = -0.82`

This strong negative correlation indicates that models with higher top speeds tend to require less time to accelerate from 0 to 100 km/h.

The relationship is correlational rather than causal.

### 4. K-Means Clustering

Applied unsupervised machine learning to group EV models with similar specifications.

**Clustering features:**

- Driving range
- Battery capacity
- Energy efficiency
- Acceleration time
- Top speed
- Torque

**Process:**

1. Selected numerical features and removed incomplete observations for the clustering analysis.
2. Standardized features using `StandardScaler`.
3. Evaluated K-Means solutions for 2–10 clusters using silhouette scores.
4. Selected the model with the highest silhouette score.
5. Applied PCA for two-dimensional visualization.
6. Compared cluster-level feature averages.

**Selected number of clusters:** 2

**Reported silhouette score:** approximately 0.40

The clustering suggests two broad groups with different performance and efficiency characteristics. These groups can support further investigation into EV specification-based market segments.

## Key Findings

| Analysis | Finding |
|---|---|
| Maximum top speed | Maserati GranTurismo Folgore — 325 km/h |
| Highest reported driving range | Mercedes-Benz EQS 450+ — 685 km |
| Lowest reported energy consumption | Dacia Spring Electric 45 — 109 Wh/km |
| Battery capacity vs. range | Strong positive correlation |
| Top speed vs. acceleration time | Pearson r = −0.82 |
| K-Means clustering | 2 clusters selected; silhouette score approximately 0.40 |

## Visualizations

The Jupyter notebook includes:

- Top-speed distribution
- Brand-level comparisons
- Vehicle body-type distribution
- Battery capacity and range relationships
- PCA visualization of K-Means clusters
- Cluster feature-average heatmap

For charts and detailed analysis, see the [Jupyter Notebook](ev-specs-dataset.ipynb).

## How to Run the Project

Clone the repository:

```bash
git clone https://github.com/nithyaak7/ev-specs-data-analytics.git
cd ev-specs-data-analytics
```

Install the principal dependencies:

```bash
pip install pandas numpy matplotlib seaborn scipy scikit-learn jupyter
```

Launch Jupyter Notebook:

```bash
jupyter notebook ev-specs-dataset.ipynb
```

Run the notebook cells in order. The analysis reads `ev_sales.csv` from the project directory.

## Repository Structure

```text
ev-specs-data-analytics/
├── README.md
├── ev-specs-dataset.ipynb
├── ev_sales.csv
└── ev-vehicle-dataset.rtf
```

## Limitations

- The dataset describes EV technical specifications, not actual vehicle sales or purchase behavior.
- Some technical specifications contain missing values.
- Driving-range values depend on the data source's testing assumptions.
- Correlations do not establish causality.
- K-Means clusters describe similarities in technical features and do not directly establish pricing or consumer preferences.

## Future Improvements

- Add numerical hypothesis-test results and confidence intervals to the README.
- Document the average values and model counts for each selected cluster.
- Add clear visualization captions and a reproducible `requirements.txt`.
- Investigate additional clustering methods and evaluate cluster stability.
- Incorporate vehicle pricing data for a future affordability analysis.

## Author

**Nithyaa Kesavamurthy**

Data & BI Analytics | Python | SQL | Statistical Analysis | Machine Learning

[GitHub](https://github.com/nithyaak7) · [Portfolio](https://nithyaak7.github.io/Data-Analyst-Portfolio/) · [LinkedIn](https://www.linkedin.com/in/nithyaa-k/)
