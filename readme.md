# Brain Tumor MRI Classification

This project implements a Deep Learning model to classify Brain MRI images into four categories: **Glioma, Meningioma, Pituitary Tumor, and Healthy**. The goal was to build a robust classifier capable of handling various points of view (POV) in medical imaging.

## 📊 Dataset
The dataset used in this project is the **Brain Tumor MRI Dataset** sourced from Kaggle. 
- **Source**: [Kaggle - Brain Tumor MRI Dataset](https://www.kaggle.com/datasets/miadul/brain-tumor-mri-dataset)
- **Content**: 7,000+ MRI images (Glioma, Meningioma, Pituitary, and Healthy).
- **Format**: JPG images organized by tumor type.

## 📁 Project Structure
To run this notebook, organize your local directory as follows:
```
.
├── brain_tumor_classification.ipynb
└── dataset/
    └── brain_tumor_dataset/
        ├── glioma/
        ├── healthy/
        ├── meningioma/
        └── pituitary/
```

## 🛠️ Methodology
I performed an **Ablation Study** to find the best model architecture, comparing a shallow CNN against a deeper one to see how they handle the complexity of MRI features.

### Preprocessing
- **Resizing**: All images standardized to 224x224 pixels.
- **Normalization**: Pixel values scaled to [0, 1].
- **Data Loading**: Used `ImageDataGenerator` for memory-efficient batch processing to avoid OOM (Out of Memory) errors.

### Model Architectures
1. **Baseline (2-Layer CNN)**: Two Convolutional layers with Max Pooling and a Dense hidden layer.
2. **Optimized (3-Layer CNN)**: Added a third Convolutional layer (128 filters) to better capture complex patterns across different anatomical planes.

## 📈 Results
The 3-layer model showed superior generalization. While the 2-layer model reached high training accuracy quickly, the 3-layer model achieved a higher validation accuracy and lower loss.

| Model | Training Accuracy | Validation Accuracy |
| :--- | :--- | :--- |
| 2-Layer CNN | 100% | 95.09% |
| **3-Layer CNN** | **99.98%** | **96.01%** |

### Performance Comparison
![Model Comparison](Comparison%202%20layers%20vs%203%20layers.png)
*Figure 1: Comparison of Validation Accuracy between the 2-layer and 3-layer architectures.*

## 🚀 How to Use
1. Clone the repository.
2. Ensure you have the dependencies installed: `pip install tensorflow opencv-python matplotlib`.
3. Run the notebook to train or load the saved model `brain_tumor_v2_3layers.keras`.

## 👤 Author
- **Wikan Priambudi**
- Biomedical Engineering Graduate, ITB
