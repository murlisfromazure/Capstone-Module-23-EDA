
# Capstone Module 23
This is the readme file describing the repository for Module 23 Capstone project Exploratary data Analysis (EDA)

Diabetic Retinopathy: Exploratory Data Analysis & Modeling

**Author:** Murli Satagopan  


## Project Overview

This project analyzes the APTOS 2019 Blindness Detection dataset, which contains 3,662 fundus images labeled by medical experts into five diabetic retinopathy (DR) categories. The goal is to explore the data, engineer features, and build models to classify DR severity, with a focus on minimizing clinically critical false negatives.

## Dataset

- **Source:** [APTOS 2019 Blindness Detection](https://www.kaggle.com/datasets/mariaherrerot/aptos2019/data)

## Setup

1. Download the dataset from Kaggle and extract it into the project directory.
2. Ensure the following structure:
    ```
    ./Data/train_images/train_images/
    ./Data/test_images/test_images/
    ./Data/val_images/val_images/
    ./Data/train_1.csv
    ./Data/test.csv
    ./Data/valid.csv
    ```
3. Install required Python packages:
    - pandas, numpy, matplotlib, seaborn, scikit-learn, Pillow, opencv-python, tensorflow, keras

**Structure:**
  - `train_images/`, `test_images/`, `val_images/`: Image directories
  - `train_1.csv`, `test.csv`, `valid.csv`: CSV files with image IDs and diagnosis labels (0: No DR, 1: Mild, 2: Moderate, 3: Severe, 4: Proliferative)


## Analysis Workflow

### 1. Data Loading & Inspection

- Load CSV files and inspect dataset shape, columns, and sample rows.
- Check for missing values.
- Visualize class distribution to assess imbalance.

### 2. Image Quality & Dimension Analysis

- Display sample images and their dimensions.
- Plot the distribution of image sizes to guide preprocessing.

### 3. Image Preprocessing

- Resize images to 224x224 pixels.
- Normalize pixel values.
- Apply CLAHE (Contrast Limited Adaptive Histogram Equalization) for enhanced local contrast.
- Save preprocessed images for reuse.

### 4. Feature Engineering & Baseline Models

- Extract classical features: color histograms, texture metrics, edge maps.
- Train logistic regression and decision tree models.
- Evaluate using accuracy, precision, recall, F1-score.
- Emphasize reduction of false negatives (missed DR cases).

### 5. Deep Feature Extraction

- Use pre-trained ResNet50 to extract CNN features.
- Train and evaluate models on deep features.

### 6. Model Evaluation & Visualization

- Print classification reports with descriptive labels.
- Visualize confusion matrices with enhanced color shading.
- Plot bar charts of false negatives by class and model.

## Key Findings

- The dataset is imbalanced, with most samples labeled as 'No DR'.
- Image resizing and CLAHE improve feature consistency and visibility.
- Classical feature extraction with decision tree and logistic regression models  performed similary. There was notable misclassification of DR cases as 'No DR'.
- CNN features (ResNet50) significantly reduce false negatives for logistic regression.
- Decision trees overfit on CNN features, leading to poorer performance.
- Logistic regression with CNN features offers the best balance for clinical relevance.

## Conclusion

This project demonstrates the importance of careful model selection in medical image classification. Deep features extracted from pre-trained CNNs can substantially improve detection of diabetic retinopathy, especially in minimizing missed diagnoses.

## References

- [APTOS 2019 Blindness Detection Dataset](https://www.kaggle.com/datasets/mariaherrerot/aptos2019/data)
- [TensorFlow Keras Applications](https://keras.io/api/applications/)
