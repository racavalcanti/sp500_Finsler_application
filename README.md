# sp500_Finsler_application

# Topological Data Analysis of Financial Markets using a Finsler Metric

This repository contains experiments applying **Topological Data Analysis (TDA)** to financial market data.
The goal is to study the **topological structure of stock correlations** using a **Finsler-type metric** and persistent homology.

The implementation explores how the geometry of financial data can reveal structural patterns through **simplicial complexes and Betti numbers**.

---

# Overview

Financial markets can be represented as a network where:

* **Nodes** represent stocks
* **Edges** represent similarity or distance between stocks
* **Topology** reveals structural properties of the market

Instead of using traditional Euclidean or correlation distances, this project introduces a **custom Finsler-type metric** to measure distances between time series.

The resulting distance matrix is used to build **simplicial complexes**, allowing the computation of topological invariants such as:

* Betti numbers
* Euler characteristic
* Persistent homology

---

# Finsler Metric

## Finsler-Type Metric

Given two vectors $p,q \in \mathbb{R}^n$, we define the distance

$$
M(p,q) =
\left(
\sum_{i=1}^{n}
f_{\mathrm{ref}}(p_i), |q_i - p_i|^{\alpha}
\right)^{\frac{1}{\alpha}}
+
\sum_{i=1}^{n}
g_{\mathrm{ref}}(\alpha, p_i),
f_{\mathrm{ref}}(p_i)^{\frac{1}{\alpha}}
(q_i - p_i)
$$

where

* $f_{\mathrm{ref}}$ is a weighting function associated with the reference vector
* $g_{\mathrm{ref}}$ is a correction function introducing directional asymmetry
* $\alpha > 0$ controls the generalized norm behavior

The first term represents a **weighted $L^\alpha$-type distance**, while the second term introduces a **directional correction**, giving the metric a **Finsler-type geometric structure**.


This produces a **Finsler-type geometry**, allowing more flexible modeling of financial data than standard metrics.

---

# Workflow

The notebook follows these steps:

1. **Load stock data**
2. **Compute pairwise Finsler distances**
3. **Construct a distance matrix**
4. **Build a simplicial complex (Vietoris–Rips)**
5. **Compute topological invariants**
6. **Analyze Betti numbers and topology**

Main libraries used:

* `pandas`
* `numpy`
* `networkx`
* `gudhi`
* `scipy`
* `matplotlib`
* `seaborn`
* `scikit-learn`

---

# Example Pipeline

1. Import stock time series
2. Compute pairwise Finsler distances
3. Build a Vietoris–Rips complex
4. Compute persistent homology
5. Study topological features of the market

This approach allows detection of:

* structural changes in market behavior
* clustering patterns among stocks
* topological signatures of financial systems

---

# Repository Structure

```
.
├── stock_tda.ipynb        # Main notebook with experiments
├── data/                  # (Optional) stock price datasets
├── figures/               # Generated plots
└── README.md
```

---

# Installation

Clone the repository:

```bash
git clone https://github.com/yourusername/stock-tda.git
cd stock-tda
```

Install dependencies:

```bash
pip install numpy pandas matplotlib seaborn networkx scipy scikit-learn gudhi
```

---

# Running the Notebook

Start Jupyter:

```bash
jupyter notebook
```

Then open:

```
stock_tda.ipynb
```

---

# Applications

This framework can be used for:

* Financial network analysis
* Market regime detection
* Correlation structure analysis
* Topological signatures of complex systems

---

# Future Work

Possible extensions include:

* persistent diagrams
* sliding window topology
* regime detection in financial crises
* comparison with correlation-based filtrations
* integration with machine learning models

---

# References

Key areas related to this project:

* Topological Data Analysis
* Persistent Homology
* Financial Networks
* Finsler Geometry

---

# Author

Rafael Cavalcanti

Research interests include:

* Topological Data Analysis
* Finsler Geometry
* Financial Mathematics
* Complex Systems

---

# License

This project is open-source and available under the MIT License.
