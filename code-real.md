---
title: Code - Real Images Dataset Training
---

#  Code for Real Dataset Training

This page contains the setup for training YOLOv8 on a real flower dataset (~110 images).

##  Environment Setup
```bash
pip install ultralytics
```

##  Dataset Structure
```
flower-real/
├── train/
│   ├── images/
│   └── labels/
├── valid/
│   ├── images/
│   └── labels/
└── data.yaml
```

##  Training  and Evalution Code
```python
PriyalGupta324/PriyalGupta324.github.io/Yolo_Training_synthetic_dataset (1).ipynb
```


##  Notes
- Real data yielded reasonable metrics.
- Could be enhanced with a larger dataset or model like `yolov8s`.

## Run 1 Results:
### Trained + Tested on Real Images Dataset

- **Train on**: Real Images (~110 images)
- **Test on**: Rea Images

| Metric                  | Value (%) | Notes                                                                 |
|-------------------------|-----------|-----------------------------------------------------------------------|
| **mAP@0.5**             | 49.8%     | Fair accuracy given the small dataset size                           |
| **mAP@0.5:0.95**        | 23.1%     | Low average precision; likely due to limited data diversity          |
| **Precision**           | 55.8%     | Over half of detections are correct — decent start                   |
| **Recall**              | 41.2%     | Model is missing several true positives, common in small datasets    |
| **Box Loss**            | 80.0%     | Localization error; should improve with more training data           |
| **Class Loss**          | 53.0%     | Some misclassifications; likely due to limited variation             |
| **DFL Loss (YOLOv8)**   | 98.0%     | High as expected in early training or small datasets                 |

 *Given the dataset size (~110 images), these results are a reasonable baseline. Performance is expected to improve with more data, better augmentations, or fine-tuning.*


[Back to Home](index.md)
