---
title: Experiment Logs
---

# 📘 Experiment Logs

A chronological log of training, validation, and tuning for all three dataset scenarios.

## 1. Trained + Tested on Real Images Dataset

- **Train on**: Synthetic (~138 images)
- **Test on**: Synthetic

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

## 2. Trained + Tested on Synthetic Dataset
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


##  3. Synthetic → Real (Transfer Scenario)
- **Train on**: Synthetic (~138 images)
- **Test on**: Real validation set (~24 images)
| Metric                  | Value (%) | Notes                                                                 |
|-------------------------|-----------|-----------------------------------------------------------------------|
| **mAP@0.5**             | 13.4%     | Very low — model struggles to localize objects on real data          |
| **mAP@0.5:0.95**        | 4.5%      | Poor generalization across IoU thresholds                            |
| **Precision (All)**     | 27.4%     | Many false positives; model confused by real-world variability       |
| **Recall (All)**        | 18.8%     | Most objects are missed — low detection sensitivity                  |
| **Box Loss / Class Loss / DFL Loss** | – | Not computed during validation phase                                 |

---

####  Class-wise Performance Breakdown

| Class         | Precision | Recall | mAP@0.5 | mAP@0.5:0.95 | Interpretation                                              |
|---------------|-----------|--------|---------|--------------|-------------------------------------------------------------|
| **bud**       | 7.3%      | 5.0%   | 1.3%    | 0.4%         | Poor results — model didn’t generalize this class well       |
| **full_bloom**| 9.2%      | 43.8%  | 15.8%   | 5.8%         | Recall is better, but confidence is low                      |
| **semi_bloom**| 65.7%     | 7.7%   | 23.1%   | 7.3%         | Good precision, but poor coverage of actual instances        |


**Conclusion:**  
These low results are expected in domain transfer problems. But with small-scale fine-tuning, mixed data, or domain adaptation methods, performance on real-world data can improve significantly — even with small real datasets.

#### Interpretation

These results indicate a **clear domain gap** between synthetic training data and real-world testing data. Even though the model performs well on synthetic data, it fails to generalize to real-world scenarios. This is typical in computer vision when the **distribution of synthetic images is too different** from real ones (in lighting, textures, noise, background, etc.)

##  Next Steps
- Try training `yolov8s.yaml`
- Mix synthetic and real images
- Explore augmentation and transfer learning

[Back to Home](index.md)
