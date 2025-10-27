# 👟 Image Classification: ResNet152V2 vs. InceptionV3 for Footwear

This project compares the performance of two state-of-the-art deep learning architectures, **ResNet152V2** and **InceptionV3**, for classifying footwear images (shoes, sandals, and boots). Model optimization was achieved using the **Keras Hyper Tuner** with Grid Search and Hyperband methods.

## 👤 Author
* **Bhargava Rajeswaran Palepu**

---

## 🎯 Objective

The goal is to develop an **effective and highly optimized classification solution** for distinguishing between shoes, sandals, and boots. These classification models are essential for E-Commerce applications.

---

## 🛠️ Methodology

### Dataset
* **Total Images:** 15,000 images of shoes, boots, and sandals.  
* **Classes:** 3 (Shoe, Sandal, Boot), with **5,000 images each**.  
* **Data Split:**
  * **Train:** 70% (10,500 images)
  * **Validation:** 15% (2,250 images)
  * **Test:** 15% (2,250 images)

### Architectures
| Model | Rationale | Key Detail |
| :--- | :--- | :--- |
| **ResNet152V2** | Chosen for its deep architecture. | 152 layers, Version V2. |
| **InceptionV3** | Offers high accuracy with efficient computation. | Uses multiple filter sizes in each layer, Version V3. |

### Hyperparameter Tuning (Keras Hyper Tuner)

Keras Hyper Tuner automates the process of finding the best set of hyperparameters.

| Tuner Method | Best For | Key Parameters Tuned (Selected) |
| :--- | :--- | :--- |
| **Grid Search Tuner** | Thorough search of a **small hyperparameter space**. | Dense Units (128–512), Dropout Rate (0.1–0.5), Optimizers (**Adam, RMSprop**). |
| **Hyperband Tuner** | Efficiently tuning **large hyperparameter spaces**. | Activation Functions ('relu', 'swish', etc.), Regularization (L1, L2, L1_L2), Learning Rates (0.0001 to 0.01). |

---

## 📈 Results

### 1. Best Hyperparameters (Grid Search Tuner)

| Model | Layer 1 Units | Layer 1 Dropout | Layer 2 Units | Layer 2 Dropout | Optimizer |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **ResNet152V2** | 512 | 0.3 | 256 | 0.4 | Adam |
| **InceptionV3** | 256 | 0.4 | 128 | 0.3 | RMSprop |

### 2. Final Performance Metrics (Hyperband Tuner - Test Set)

| Model | Accuracy | Precision | Recall | AUC |
| :--- | :--- | :--- | :--- | :--- |
| **ResNet152V2** | **0.982222** | **0.982214** | **0.981778** | **0.996498** |
| **InceptionV3** | 0.966667 | 0.967886 | 0.964400 | 0.9940 |

### 3. Grid Search Tuner Accuracy

| Model | Test Accuracy | Validation Accuracy |
| :--- | :--- | :--- |
| **ResNet152V2** | 95.6% | 95.8% |
| **InceptionV3** | 94.4% | 94.7% |

---

## ✅ Conclusion

* Both ResNet152V2 and InceptionV3 are powerful model architectures for image classification.  
* The study confirms that optimizing model parameters is crucial for yielding the best results.  
* **ResNet152V2 slightly outperforms InceptionV3** in terms of precision and generalization.
