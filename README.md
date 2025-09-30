# Breast-Cancer-Classification

This project focuses on early detection of breast cancer by classifying medical images into **benign** or **malignant** tumors using deep learning models.  
It compares CNN (VGG), ResNet, EfficientNet, and Vision Transformer (ViT) on three benchmark medical datasets.

📂 Datasets

We used three publicly available datasets:

1. BreakHis (Histopathology Images)  
   - Labels: 0 → Benign, 1 → Malignant  
   - Used with ResNet, ViT
   - [Download BreakHis](https://www.kaggle.com/datasets/ambarish/breakhis)

2. DDSM (Mammography Images)
   - Labels: 0 → Benign, 1 → Malignant  
   - Used with **VGG, EfficientNet, ViT 
   - [Download CBIS-DDSM](https://www.kaggle.com/datasets/awsaf49/cbis-ddsm-breast-cancer-image-dataset)

3. INbreast (Mammography Images)
   - Labels: 0 → Benign, 1 → Malignant  
   - Used with VGG, ViT
   - [Download INbreast](https://www.kaggle.com/datasets/ramanathansp20/inbreast-dataset)

Models Implemented

- ResNet-50 (Pretrained on ImageNet, fine-tuned)  
- EfficientNetB3 (Pretrained, fine-tuned)  
- Vision Transformer (ViT) (patch embedding + self-attention)  
- Custom VGG-like CNN (3 Conv layers + BatchNorm + Dropout)

Implementation Details

- Data Preprocessing:
  - Resizing images (224×224 or 300×300)  
  - Augmentation: rotation, zoom, shifting, flipping  
  - Normalization  

- Training Setup:
  - Optimizer: Adam  
  - Loss: Binary Crossentropy  
  - Epochs: 10–30 (with early stopping)  
  - Class weights for imbalanced datasets  
  - Model checkpointing  

📊 Results

- ResNet-50 → ~98% accuracy (overfitting, high train but lower validation performance)  
- EfficientNetB3 → ~95% accuracy (good training, struggled on unseen data)  
- Vision Transformer (ViT) → ~88.5% accuracy, F1 Score ~0.87 (best balance, chosen as final model)  
- Custom VGG → ~96% accuracy (strong validation results on DDSM)  

We finally went with Vision Transformer (ViT) since it gave the most reliable and consistent performance across datasets.

Key Insight:
- ViT gave the best balance between accuracy and generalization.  
- VGG performed reliably on DDSM with strong validation results.  
- ResNet and EfficientNet showed signs of overfitting without larger datasets.  


How to Run

1. Clone the repository:  
   ```bash
   git clone https://github.com/pratiksha270/Breast-Cancer-Classification/new/main
   cd breast-cancer-classification
