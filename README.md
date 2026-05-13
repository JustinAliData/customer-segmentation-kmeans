# Customer Segmentation with K-Means

> Segments customers into distinct behavioral profiles using K-Means clustering, validated with silhouette scoring and benchmark models. Output: a small set of stakeholder-ready customer profiles with recommended marketing actions.

**Stack:** Python · scikit-learn · Pandas · NumPy · Matplotlib · Seaborn
**Status:** Completed
**Author:** Justin Ali · [LinkedIn](https://www.linkedin.com/in/justin-ali-data/)

---

## The problem

Mass-market campaigns treat every customer the same. Behavioral segmentation lets a marketing team tailor offers to customers most likely to respond, while leaving low-affinity segments alone. The deliverable here is a small number of well-separated customer profiles a non-technical stakeholder can act on: *who they are, how they behave, and what to send them*.

## Approach

1. **EDA** — Distribution and correlation structure of behavioral features to guide scaling and selection.
2. **Preprocessing** — StandardScaler, because K-Means distance is dominated by high-variance features otherwise.
3. **Cluster count** — Elbow method on within-cluster sum of squares, validated with silhouette score across k = 2 through 10.
4. **Clustering** — K-Means at the chosen k, with multiple random restarts to avoid bad initialization.
5. **Benchmarking** — Compared against hierarchical clustering and DBSCAN to confirm segment stability and that K-Means was not picking up noise.
6. **Interpretation** — PCA projection for visualization; mean feature values per cluster translated into plain-English personas in the deliverable.

## Results

Delivered a small set of clearly distinguishable customer segments, each with a one-paragraph profile and a recommended marketing action. The PCA scatter shows clean separation, and silhouette analysis confirmed the cluster count was a defensible choice rather than a guess.

## What I would do next

- Move from static profiles to a scoring function: given a new customer, which segment do they fall into?
- A/B test the per-segment recommendations against a control to measure lift.
- Add a recency dimension (RFM-style) so segments capture lifecycle, not just current behavior.
- Re-fit on a rolling window to track how segments shift over time.

## Repo contents

```
.
├── notebooks/
├── data/
└── README.md
```

## How to run

```bash
git clone https://github.com/JustinAliData/customer-segmentation-kmeans.git
cd customer-segmentation-kmeans
python -m venv .venv && source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter lab
```

## Acknowledgments

Built as part of the **Springboard Data Science Career Track**.
