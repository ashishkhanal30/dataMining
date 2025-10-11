## Baton Rouge Traffic Crash Clustering

This repository contains an exploratory data analysis and clustering study of traffic crash incidents in Baton Rouge. The analysis uses hierarchical clustering and DBSCAN to discover spatial and temporal groupings of crash events and highlight areas and times with concentrated crash activity.

### Contents

-   `Baton_Rouge_Traffic_Crash_Incidents_20250920.csv` — raw crash incident dataset (CSV)
-   `preprocessing-1.csv` — example preprocessed output used in the notebooks
-   `main.ipynb` — primary analysis notebook that runs clustering experiments and summarizes findings
-   `preprocess.ipynb` — notebook used to clean and prepare the raw dataset for clustering
-   `visualization.ipynb` — notebook with maps and plots for cluster visualizations
-   `requirements.txt` — Python dependencies used for the analysis

---

### Goal

Use clustering algorithms to identify patterns in traffic crash incidents in Baton Rouge, focusing on:

-   Spatial clusters (locations with repeated incidents)
-   Temporal patterns (time-of-day / day-of-week concentrations)
-   Comparing hierarchical clustering (agglomerative) vs density-based clustering (DBSCAN)

These insights can help prioritize safety interventions and further investigation.

---

### Methods

-   Hierarchical clustering (agglomerative): useful for creating cluster dendrograms and exploring multi-scale groupings.
-   DBSCAN: density-based algorithm that finds arbitrarily shaped clusters and labels noise (sparse incidents) — well-suited to spatial incident clustering.

Typical features used in the notebooks:

-   Latitude / Longitude (spatial clustering)
-   Timestamp-derived features (hour of day, day of week)
-   Optional attributes such as crash severity, number of vehicles, or contributing factors (when available)

Assumption: the dataset contains location and time columns (latitude, longitude, and a datetime field). If your schema differs, adjust the preprocessing notebook accordingly.

---

### How to run

1. Create and activate a Python virtual environment (recommended):

```bash
# macOS / zsh
python3 -m venv .venv
source .venv/bin/activate
pip install --upgrade pip
pip install -r requirements.txt
```

2. Start Jupyter Lab / Notebook and open the notebooks:

```bash
jupyter lab
# or
jupyter notebook
```

3. Run `preprocess.ipynb` first to create a cleaned dataset (`preprocessing-1.csv`) then open `main.ipynb` to reproduce clustering experiments. Use `visualization.ipynb` for interactive maps and plots.

---

### Reproducibility notes

-   The notebooks are sequential and include explanatory text. Run cells in order after installing dependencies.
-   If results differ, check random seeds in clustering cells (some algorithms depend on initialization).
-   If the dataset is updated, rerun preprocessing before the main analysis.

---

### Results (summary)

The notebooks produce cluster assignments, dendrograms (for hierarchical clustering), DBSCAN cluster maps, and summary statistics per cluster (counts, time distributions). Key deliverables include:

-   Maps of DBSCAN clusters over Baton Rouge
-   Dendrogram and cluster cut analysis for hierarchical clustering
-   Tables listing high-incident locations and their temporal profiles

---

### Next steps / suggestions

-   Tune DBSCAN parameters (eps, min_samples) with a silhouette or domain-guided approach.
-   Incorporate road network or traffic volume data to refine clusters.
-   Produce static/exportable figures and a short report summarizing findings for stakeholders.

---

### Contributors

-   Sunil Thapa
-   Ashish Chandra Khanal

---

### License

This repository is provided for educational purposes. Add a license file if you want to share it publicly under a specific license.
