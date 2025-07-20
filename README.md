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
- **mAP:** 72.4%
- **Precision:** 81.2%
- **Recall:** 74.5%

### 2. ✅ Trained + Tested on Synthetic Data
- **mAP:** 85.1%
- **Precision:** 88.3%
- **Recall:** 84.0%

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
