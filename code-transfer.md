---
title: Code - Transfer Learning
---
work in Progress



#  Transfer Learning: Synthetic → Real

In this setup, we train on the synthetic flower dataset and test on the real flower dataset.

##  Goal
To check generalization from synthetic images to real-world images.

##  Code
```python
from ultralytics import YOLO

model = YOLO('yolov8n.pt')  # Pretrained on synthetic
metrics = model.val(data='flower-real/data.yaml')
```

##  Observations
- Accuracy dropped due to domain shift.
- Fine-tuning the model on real data might help bridge the gap.

##  Next Steps
- Try training longer or using YOLOv8s.
- Include some real samples in training for better generalization.

[Back to Home](index.md)
