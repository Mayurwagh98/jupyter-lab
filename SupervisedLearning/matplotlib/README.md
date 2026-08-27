# Matplotlib — Data Visualization Tutorial

A hands-on tour of **matplotlib** plotting, working through most of the common chart types and the customization options that make them readable. Examples use small themed datasets (Oscar movie revenue, blood pressure, transactions, city temperatures).

## Contents

| File | Purpose |
|------|---------|
| `matplotlib_tutorial.ipynb` | Comprehensive walkthrough of chart types and customization |
| `assignment.ipynb` | Histogram of student scores with a mean reference line |

## Chart Types Covered (matplotlib_tutorial.ipynb)
- **Line plots** — single and multiple series, with markers, colors, and line styles
- **Bar charts** — grouped/multi-bar with value labels (`plt.text`) and horizontal bars (`barh`)
- **Scatter plots** — sized/colored points, colorbars, annotations, axis limits, and multi-series
- **Pie charts** — percentages, explode, custom wedge styling, shadow, start angle
- **Histograms** — custom bins, single and overlaid multi-dataset (legit vs. fraud transactions)
- **Box plots** — single and grouped, for spotting spread and outliers
- **Stack plots** — cumulative area chart (marketing channels over a week)
- **Subplots** — both the `plt.subplot()` grid API and the `fig, ax = plt.subplots()` object API, with `flatten()`, shared titles (`suptitle`, `supxlabel`, `supylabel`), and `tight_layout`

### assignment.ipynb
A histogram of normally-distributed student scores with a dashed vertical `axvline` marking the mean.

## Concepts Covered
- Core plot types: line, bar, scatter, pie, histogram, box, stack
- Titles, axis labels, legends, grids, and text annotations
- Colors, markers, line styles, and transparency (`alpha`)
- Reference lines (`axvline`)
- Multiple series on one axes
- Subplots via both the stateful (`pyplot`) and object-oriented (`Axes`) interfaces
- Layout management with `tight_layout` and figure-level labels
- Generating sample data with NumPy (`np.random.normal`, `np.arange`)

## Requirements
```bash
pip install matplotlib numpy
```

## Usage
Open a notebook in Jupyter and run the cells top to bottom — each cell is a self-contained plotting example.
