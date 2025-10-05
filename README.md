# DA5401 A5: Visualizing Data Veracity Challenges in Multi-Label Classification

**Name:** Tanmay Gawande  
**Roll Number:** DA25M030

---

## Overview

This project investigates the structure and classification challenges of the Yeast gene expression dataset using manifold learning and data veracity inspection. Dimensionality reduction techniques (t-SNE, Isomap,) are applied to visualize class spread and overlap, and specialized methods are used to identify noisy labels, outliers, and hard-to-learn samples.

---

## Dataset

- Source: Mulan Yeast Dataset ([Dataset link](http://mulan.sourceforge.net/datasets-mlc.html))
- 2,417 samples, 103 features, 14 functional gene classes (multi-label).

---

## Workflow

1. **Preprocessing & Label Simplification**
    - Convert ARFF to CSV, extract features and multi-labels.
    - Simplify labels for visualization (most frequent single/multi-labels + "Other").

2. **Scaling**
    - Standardize features using Z-score normalization for fair distance calculations.

3. **Dimensionality Reduction**
    - **t-SNE:** Reveals local cluster structure; multiple perplexity values tested.
    - **Isomap:** Preserves global manifold geometry.

4. **Data Veracity Inspection**
    - **Noisy/Ambiguous Labels:** Points embedded in clusters of other classes.
    - **Outliers:** Isolated points detected using Local Outlier Factor (LOF).
    - **Hard-to-Learn Samples:** Points with mixed local neighborhoods.

5. **Visualization**
    - Scatter plots for all projections.
    - Subplots for individual class spreads.
    - Comparative plots for t-SNE vs Isomap.

---

## Key Insights

- t-SNE excels at revealing local clusters but does not preserve global arrangement.
- Isomap provides a continuous view of the data manifold, showing global relationships.
- Outliers and noisy labels are identified and visualized, highlighting classification challenges.
- Significant class overlap is the main challenge for classification; moderate manifold curvature adds slightly to this difficulty.

---

## Project Structure

```
DA5401-assignment-5/
├── da25m030-assignment-5-solution.ipynb    # Main Jupyter Notebook
├── requirements.txt                        # Project requirements
├── yeast.csv                               # Preprocessed dataset
└── README.md                               # Project documentation
```

---

## Conclusion

The manifold learning results indicate that the data manifold itself is relatively simple—there are no disconnected regions or sharp folds in the visualizations. Instead, the primary classification difficulty arises from the substantial overlap between classes on this smooth manifold, making class separation difficult even though the underlying geometry is not highly complex. Thus, effective models must be able to disambiguate these intermixed groups, as manifold curvature is only a minor obstacle compared to the extent of class overlap.

---

## References

- Yeast dataset: [Mulan Yeast Dataset](http://mulan.sourceforge.net/datasets-mlc.html)
- scikit-learn documentation: [Scikit learn](https://scikit-learn.org/stable/)

---
