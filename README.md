# 🧠 Computer Vision Project Report

Welcome to my GitHub Pages website documenting progress and results for my computer vision project.

---

## 📌 Objective

This project compares object detection performance using:
- Real-world dataset
- Synthetic dataset
- Synthetic training + real testing

---

## 📁 Dataset Summary

| Dataset Type      | Images Used | Source         | Notes                  |
|-------------------|-------------|----------------|-------------------------|
| Real Images       | 500         | FlowerNow      | Real-world captures     |
| Synthetic Images  | 1000        | Generated via GANs | Uniform backgrounds     |
| Real (Test) Only  | 300         | FlowerNow      | For domain gap analysis |

---

## 📈 Results

### 1. ✅ Trained + Tested on Real Data
#### 📊 Evaluation Metrics (as Percentages)

| Metric                  | Value (%) | Notes                                                                 |
|-------------------------|-----------|-----------------------------------------------------------------------|
| **mAP@0.5**             | 49.8%     | Fair accuracy given the small dataset size                           |
| **mAP@0.5:0.95**        | 23.1%     | Low average precision; likely due to limited data diversity          |
| **Precision**           | 55.8%     | Over half of detections are correct — decent start                   |
| **Recall**              | 41.2%     | Model is missing several true positives, common in small datasets    |
| **Box Loss**            | 80.0%     | Localization error; should improve with more training data           |
| **Class Loss**          | 53.0%     | Some misclassifications; likely due to limited variation             |
| **DFL Loss (YOLOv8)**   | 98.0%     | High as expected in early training or small datasets                 |

✅ *Given the dataset size (~110 images), these results are a reasonable baseline. Performance is expected to improve with more data, better augmentations, or fine-tuning.*


### 2. ✅ Trained + Tested on Synthetic Data
#### 📊 Evaluation Metrics – Synthetic Dataset (~138 Images)

| Metric                  | Value (%) | Notes                                                                 |
|-------------------------|-----------|-----------------------------------------------------------------------|
| **mAP@0.5**             | 57.2%     | Reasonable accuracy for a small synthetic dataset                     |
| **mAP@0.5:0.95**        | 28.3%     | Limited generalization across IoU thresholds                         |
| **Precision**           | 63.0%     | Decent — majority of predictions are correct                         |
| **Recall**              | 46.0%     | Model is missing some objects; more data may help                    |
| **Box Loss**            | 72.0%     | High bounding box error — needs improvement                          |
| **Class Loss**          | 39.0%     | Acceptable classification performance                                |
| **DFL Loss (YOLOv8)**   | 87.0%     | Still high — indicates room for tuning                               |

✅ *These results are decent for a synthetic dataset of only ~138 images. Performance may improve with better synthetic variety or fine-tuning.*


### 3. ❌ Trained on Synthetic, Tested on Real
- **mAP:** 59.6%
- **Precision:** 60.2%
- **Recall:** 56.0%

---

## 🔍 Observations

- Domain shift is clearly visible when synthetic is used for training and real for testing.
- Plan to improve results:
  - Use domain adaptation techniques (style transfer or fine-tuning)
  - Improve synthetic image diversity

---

## 🛠️ Work in Progress

- [ ] Implementing image augmentation
- [ ] Training with mixed datasets
- [ ] Visualizing confusion matrix

---

## 📊 Results Visualized

### 1. Training Loss Curve


### 2. mAP Comparison
