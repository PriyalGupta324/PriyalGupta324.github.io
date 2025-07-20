---
title: Results Overview
---

#  Results Overview

A summary of evaluation metrics for each training/testing setup.

##  Real Dataset
| Metric              | Value     |
|---------------------|-----------|
| mAP@0.5             | 49.8%     |
| mAP@0.5:0.95        | 23.1%     |
| Precision           | 55.8%     |
| Recall              | 41.2%     |
| Box Loss            | 0.80      |
| Classification Loss | 0.53      |
| DFL Loss            | 0.98      |
>  Notes: Acceptable results for a small dataset (~110 images). Further tuning and a stronger model may help.

##  Synthetic Dataset
| Metric              | Value     |
|---------------------|-----------|
| mAP@0.5             | 57.2%     |
| mAP@0.5:0.95        | 28.3%     |
| Precision           | 63.0%     |
| Recall              | 46.0%     |
| Box Loss            | 0.72      |
| Classification Loss | 0.39      |
| DFL Loss            | 0.87      |
>  Notes: Best performance. Synthetic data proved diverse and well-labeled (~138 images).

##  Transfer: Synthetic → Real
| Metric              | Value     |
|---------------------|-----------|
| mAP@0.5             | 13.4%     |
| mAP@0.5:0.95        | 4.48%     |
| Precision           | 27.4%     |
| Recall              | 18.8%     |
>  Notes: Highlights domain gap. Low generalization. Can be improved by fine-tuning on real data.

[Back to Home](index.md)
