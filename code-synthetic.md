---
title: Code - Synthetic Dataset Training
---

#  Code for Synthetic Dataset Training

This section contains the code and structure for training YOLOv8 on a **synthetic flower dataset**.

## Environment Setup
```bash
pip install ultralytics
```

## 📁 Dataset Structure
Exported using Roboflow in YOLOv8 format:

```
flower-synthetic/
├── train/
│   ├── images/
│   └── labels/
├── valid/
│   ├── images/
│   └── labels/
└── data.yaml
```

##  Training and Evauation Code
```python
Yolo_Traning_real_world_images_dataset (1).ipynb
```

## 💡 Tips to Improve Results
- Try using `yolov8s.yaml` or `yolov8m.yaml`
- Generate more varied synthetic images (lighting, angles, blur)
- Include backgrounds and clutter for realism

## Run 1 Results:
### Trained + Tested on Synthetic Dataset
- **Train on**: Synthetic (~138 images)
- **Test on**: Synthetic
| Metric                  | Value (%) | Notes                                                                 |
|-------------------------|-----------|-----------------------------------------------------------------------|
| **mAP@0.5**             | 57.2%     | Reasonable accuracy for a small synthetic dataset                     |
| **mAP@0.5:0.95**        | 28.3%     | Limited generalization across IoU thresholds                         |
| **Precision**           | 63.0%     | Decent — majority of predictions are correct                         |
| **Recall**              | 46.0%     | Model is missing some objects; more data may help                    |
| **Box Loss**            | 72.0%     | High bounding box error — needs improvement                          |
| **Class Loss**          | 39.0%     | Acceptable classification performance                                |
| **DFL Loss (YOLOv8)**   | 87.0%     | Still high — indicates room for tuning                               |

 *These results are decent for a synthetic dataset of only ~138 images. Performance may improve with better synthetic variety or fine-tuning.*



[Back to Home](index.md)
