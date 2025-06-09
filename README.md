### Final Project - Big Data

## Set Up

```bash

pip install pandas
pip install np
```

## Submission Format

Provide a zip file with this structure:

```
812K0001C/
|- main.ipynb              # my code for clustering
|- 812K0001C_public.csv  # for evaluation on the public dataset
|- 812K0001C_private.csv # for evaluation on the private dataset
|- 812K0001C_report.pdf
```

Each file should follow the format below:

```
id,label
0,1
1,2
2,3
...
```

#### id should follow the original sample order. label is my predicted value.

## Validation

Use eval.py to check my performance on the public dataset:
```bash
python eval.py
```

## Clustering Results

| Clustering Method                     | FMI Score | Description                                                        |
|--------------------------------------|-----------|--------------------------------------------------------------------|
| GMM (covariance_type='full')         | 0.8548    | Best model; handles elliptical clusters well; highly flexible     |
| Agglomerative (KNN connectivity)     | 0.8391    | Good for hierarchical structure; memory-efficient with KNN graph  |
| Spectral Cluster (nearest_neighbors) | 0.8261    | Works well for non-linear separable clusters; stable performance  |
| GMM (default diag covariance)        | 0.7976    | Handles simple elliptical shapes; less flexible than full         |
| KMeans with log1p                    | 0.7813    | Standard baseline; spherical cluster assumption                   |
| PCA (4D) + KMeans                    | 0.7813    | Feature rotated only; no dimensionality reduction                 |
| PCA (2D) + KMeans                    | 0.7704    | Visual clarity only; minor info loss                              |

